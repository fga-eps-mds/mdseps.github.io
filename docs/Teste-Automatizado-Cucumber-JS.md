# BDD com o cucumber em JavaScript

## Objetivo

Este documento tem como objetivo principal criar um tutorial básico sobre o cucumberJS, ferramenta feita para desenvolvimento utilizando BDD (_Behaviour Driven Development_) em javascript.

## Introdução

<p align="justify"> Controlar se todos os critérios de aceitação de um sistema foram cumpridos nem sempre é uma tarefa fácil, e para simplificar esta tarefa, o BDD foi criado.
Neste tipo de teste o sistema é testado como um todo, sem considerar diferenças entre servidor e cliente, ou até mesmo banco de dados, garantindo assim que a funcionalidade como um todo funciona, porém nunca garantindo que ao encontrar um erro, torne mais fácil o <i>debug</i>.</p>

## Objetivo do teste

O teste de exemplo para este tutorial será a funcionalidade do google de busca por um nome, sendo o caso de teste a busca da frase GPP/MDS e verificar se o github da disciplina é apresentado

## Instalação

### Pré requisitos:
- npm

### Preparação do teste

`npm init`

Serão apresentadas várias perguntas, aperte enter em todas =D.

`npm install --save-dev cucumber cucumberjs-chromedriver selenium-webdriver`
`npm install -g gulp`

## Configuração dos testes

### Estrutura de arquivos

Os arquivos devem estar disponibilizados da seguinte forma:

raiz<br>
|- package.json
|- gulpfile.js
|- tests<br>
_____|- features <br>
___________|-<files>.feature<br>
___________|-step_definitions<br>
____________________|-\<file\>_steps_.js<br>
___________|-support<br>
____________________|-env.js<br>
____________________|-hook.js<br>
____________________|-world.js<br>


#### Gulpfile.js

    var gulp = require('gulp');
    var runSequence = require('run-sequence').use(gulp);
    var cucumber = require('gulp-cucumber');

    gulp.task('cucumber', function() {

      var file = "*";
      if (process.argv.length >= 4) {
        file = process.argv[3].replace(/-+/, "");
      }

      return gulp.src('./tests/features/' + file).pipe(cucumber({
        'steps': './tests/features/step_definitions/commom_steps.js',
        'support': './tests/features/support/*.js'
      }))
    })

### Env.js

    'use strict';

    var configure = function() {
      this.setDefaultTimeout(60 * 1000);
    };

    module.exports = configure;

### Hooks.js

    'use strict';

    var driver = require('./world.js').getDriver();
    var fs = require('fs');
    var path = require('path');
    var sanitize = require("sanitize-filename");

    var myHooks = function() {

      this.After(function(scenario) {
        if (scenario.isFailed()) {
          this.driver.takeScreenshot().then(function(data) {
            var base64Data = data.replace(/^data:image\/png;base64,/, "");
            fs.writeFile(path.join('screenshots', sanitize(scenario.getName() + ".png").replace(/ /g, "_")), base64Data, 'base64', function(err) {
              if (err) console.log(err);
            });
          });
        }
        return this.driver.manage().deleteAllCookies();
      });

      this.registerHandler('AfterFeatures', function(event) {
        return driver.quit();
      });

    };

    module.exports = myHooks;

### World.js

    'use strict';

    var fs = require('fs');
    var webdriver = require('selenium-webdriver');
    var platform = process.env.PLATFORM || "CHROME";
    var until = webdriver.until;

    var buildChromeDriver = function() {
      return new webdriver.Builder().
      withCapabilities(webdriver.Capabilities.chrome()).
      build();
    };

    var buildFirefoxDriver = function() {
      return new webdriver.Builder().
      withCapabilities(webdriver.Capabilities.firefox()).
      build();
    };

    switch (platform) {
      case 'FIREFOX':
        var driver = buildFirefoxDriver();
        break;
      default:
        var driver = buildChromeDriver();
    }

    var getDriver = function() {
      return driver;
    };

    var World = function World() {

      var defaultTimeout = 5000;
      var screenshotPath = "screenshots";

      this.webdriver = webdriver;
      this.driver = driver;

      if (!fs.existsSync(screenshotPath)) {
        fs.mkdirSync(screenshotPath);
      }

      this.waitForCss = function(cssLocator, timeout) {
        var waitTimeout = timeout || defaultTimeout;
        return driver.wait(until.elementLocated({
          css: cssLocator
        }), waitTimeout);
      };

      this.waitForXpath = function(xpath, timeout) {
        var waitTimeout = timeout || defaultTimeout;

        return driver.wait(
          until.elementLocated(
            webdriver.By.xpath(xpath)), waitTimeout
        );
      }

      this.waitForTagName = function(tagName, timeout) {
        var waitTimeout = timeout || defaultTimeout;

        return driver.wait(
          until.elementLocated(
            webdriver.By.tagName(tagName)), waitTimeout
        );
      };

      this.waitForTagNames = function(tagName, timeout) {
        var waitTimeout = timeout || defaultTimeout;

        return driver.wait(
          driver.findElements(webdriver.By.tagName(tagName), waitTimeout)
        );
      }

      this.waitForId = function(idLocator, timeout) {
        var waitTimeout = timeout || defaultTimeout;
        return driver.wait(until.elementLocated({
          id: idLocator
        }), waitTimeout);
      };

      this.type = function(id, word) {
        return driver.findElement({
            id: id
          })
          .sendKeys(word);
      }

      this.click = function(id) {
        return driver.wait(until.elementLocated({
          id: id
        }), defaultTimeout).then(function(response) {
          return response.click();
        })
      }

    };

    module.exports.World = World;
    module.exports.getDriver = getDriver;

## Testes

Finalmente com todos os testes prontos configurados, podemos começar a desenvolver os cases de testes, os quais se encontram nos arquivos .feature.

### gpp_mds.feature

    Feature: Search google feature
      In order to see if the company in github is big
      As a student
      I want be able to find it on google

    Scenario: Found it
      Given I am in googles page
      When I type gppmds
      When I click search button
      Then I should see https://github.com/fga-gpp-mds

### Commom_steps.js

Agora é necessário desenvolver os steps, para que o cucumberJS possa identificar qual a tarefa que deve ser realizada a cada linha do _Scenario_.

    var expect = require('chai').expect;
    var webdriver = require('selenium-webdriver')
    var until = webdriver.until;

    var commom_steps = function() {
      this.World = require('../support/world.js').World;

      /****************************************************************************
       ********************************* GIVEN *************************************
       ****************************************************************************/
      this.Given(/^I am in googles page$/, function() {
        return this.driver.get('https://www.google.com');
      });

      /****************************************************************************
       ********************************* WHEN **************************************
       ****************************************************************************/
      this.When(/^I type (.+)$/, function(word) {
        var type = this.type;
        return this.waitForId('lst-ib').then(function(response) {
          type('lst-ib', word);
        })
      });

      /****************************************************************************
       ********************************* THEN *************************************
       ****************************************************************************/
      this.Then(/I should see (.+)$/, function(text) {
        var driver = this.driver;

        return driver.sleep(1000).then(function() {
          return driver.findElement(webdriver.By.tagName("body")).getAttribute("innerHTML").then(function(html) {
            if (html.lastIndexOf(text) > 0) {
              // nothing to do.
            } else {
              throw (new Error("Texto " + text + " esperado porém não encontrado"));
            }
          })
        });
      });
    };

    module.exports = commom_steps;

## Executando

Finalmente poderemos executar nossos testes, e para isso é só executar o comando:

`gulp cucumber`

Então o CucumberJS irá entrar na pasta e executar todas as features marcadas =D
