-----
* [Configuração de Ambiente](#configuração-de-ambiente)
  * [Instalando Ionic](#instalando-ionic)
* [Arquitetura MVC](#arquitetura-mvc)
  * [Ionic Framework](#ionic-framework)
  * [AngularJS](#angularjs)
  * [Rails como servidor](#rails-como-servidor)
* [DOJO de testes (material didático)](#dojo-de-testes-material-didático)
  * [AngularJS Teste Unitário](#angularjs-teste-unitário)
* [Repositórios educativos](#repositórios-educativos)
* [Material didático produzido na disciplina (times, coaches, etc)](#material-didático-produzido-na-disciplina-times-coaches-etc)

-----

# [[Configuração de Ambiente]]

## Instalando Ionic

Para instalar o Ionic e o Cordova utilizando NPM é necessário que já se tenha instalado o Node.js, caso não tenha, você pode instalar através deste [link](https://nodejs.org/en/).

1) Digite no terminal este comando para instalar o Ionic e o Cordova.

`npm install -g cordova ionic`

2) Caso já tenha o Cordova e o Ionic instalado, atualize para a versão mais recente.

`npm update -g cordova ionic`


# Arquitetura MVC

A proposta da arquitetura MVC é fazer uma divisão em 3 camadas sobrepostas, de uma forma que o usuário só irá interagir com uma delas, no caso a View. Cada parte tem um valor diferente.

* Modelos (models) - Armazenamento de dados, definição dos estados das camadas e interpretação de requisições.
* Visão (views) - Controle de layout e definição de design. A visão é controlada pelo Ionic e o Firebase.
* Controles (controllers) - Tráfego de informações entre todas as camadas, principalmente entre o Ruby on Rails e o Ionic Framework

A camada View é de responsabilidade do framework IONIC. Quando utiliza-se esse framework, geralmente adota-se o framework Rails. Portanto a configuração do MVC fica como apresentado na imagem a seguir.

![](http://i.imgur.com/H4qPRqa.png)
# DOJO de linguagem (material didático)

## Ionic Framework
Ionic é um framework criado em 2013 que visa a criação de aplicações híbridas para dispositivos móveis (iOS e Android). Hoje o Ionic encontra-se na versão 2.0. Porém para utilizar o Ionic e desenvolver aplicações móveis com o Cordova é necessário ter instalado as seguintes dependências:
* NodeJS;
* NPM.

O ionic nada mais é do que uma pilha de componentes e outros frameworks. Estes componentes são:
* Cordova: Integração com recursos nativos dos dispositivos;
* AngularJS: Criação da parte Web da App;
* Ionic Module e o Ionic CLI: Ferramentas e Componentes disponibilizados pelo framework.

[Curso Ionic Framework](https://www.youtube.com/watch?v=kbcWTi_QKAI&list=PLpP8rO2FXVXTJRTJ2j6rYLKQrQC1XgIra)


## AngularJS
AngularJs é um framework do JavaScript que foi criado em 2012 e atualmente se encontra na versão 2.0. É uma extensão do HTML com novos atributos e é perfeito para aplicações de página única.      
Seu objetivo é aumentar aplicativos que podem ser acessados por um navegador web, foi construído sob o padrão model-view-view-model (MVVM), em um esforço para facilitar tanto o desenvolvimento quanto o teste dos aplicativos.   
      
[Curso AngularJS](https://www.youtube.com/watch?v=_y7rKxqPoyg&list=PLQCmSnNFVYnTD5p2fR4EXmtlR6jQJMbPb)

## Rails como servidor

# DOJO de testes (material didático)
## AngularJS Teste Unitário
***
* [Tutorial - Jasmine Test Framework](http://jasmine.github.io/2.5/node.html)
* [Unit Test an AngularJS Controller](http://www.bradoncode.com/blog/2015/05/17/angularjs-testing-controller/)
* [AngularJS Unit Testing](https://docs.angularjs.org/guide/unit-testing)


# Repositórios educativos

* [Guia do Desenvolvedor Ionic](https://github.com/IonicBrazil/guia-do-desenvolvedor/blob/master/README.md)



# Material didático produzido na disciplina (times, coaches, etc)