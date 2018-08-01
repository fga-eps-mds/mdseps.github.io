# Integração Contínua

## Introdução

&quot;_Integração Contínua é uma prática de desenvolvimento de software onde os membros de um time integram seu trabalho frequentemente, geralmente cada pessoa integra pelo menos diariamente  podendo haver múltiplas integrações por dia. Cada integração é verificada por um build automatizado (incluindo testes) para detectar erros de integração o mais rápido possível. Muitos times acham que essa abordagem leva a uma significante redução nos problemas de integração e permite que um time desenvolva software coeso mais rapidamente._&quot; Martin Fowler

A visão de integração contínua do software é uma prática oriunda do metodologia ágil XP, que visa integrar o código alterado na mesma frequência com que as funcionalidades são desenvolvidas. A implementação desta prática traz o benefício de detectar erros no sistema o mais rápido possível, garantindo maior qualidade no produto final.

## Controle de Versão

O controle de versão é uma ferramenta crucial para a integração contínua, pelo simples fato de ser uma ferramenta que permite o trabalho colaborativo, onde há compartilhamento de dados entre diversos desenvolvedores que trabalham em conjunto. Para o XP, que tem como premissa o trabalho contínuo e constante, o controle de versão é essencial.

O controle de versão juntamente com um repositório online permitem ter-se sempre uma versão válida e funcional, e saber quem fez alterações no projeto, e ainda evita que desenvolvedores façam trabalho já feito. Para ferramentas de controle de versão que permitem o trabalho em conjunto temos CVS, [Subversion](http://www.devmedia.com.br/video-controle-de-versoes-com-subversion-parte-1-conceitos-de-controle-de-versoes-e-gerencia-de-configuracao/16418), [Git](http://www.devmedia.com.br/curso/curso-controle-de-versao-com-git/380), entre outros. Utilizando repositórios onlines como por exemplo github, temos juntamente com a ferramenta de versionamento o suporte online para usuários, podendo desde acessar e visualizar um sistema a gerenciá-lo.

Com o desenvolvedor sempre integrando código, benefícios como restauração de versões anteriores, comparação de código e gestão de alterações são possíveis graças à ferramenta de controle de versão e seu repositório.

## Testes Automatizados

Uma das vantagens quando se utiliza uma ferramenta de integração contínua reside nos testes automatizados. Uma vez que se conclui uma funcionalidade do sistema e deseja-se integrar estas mudanças à build principal, deve-se antes ter certeza de que essa build está devidamente testada e livre de erros. Porém, somente  este procedimento não garante a integridade do sistema como um todo. Quando se implementa uma ferramenta de integração contínua dentro do seu projeto, tem-se implicitamente a necessidade de que sua build principal esteja sempre íntegra. Isto é possível graças à integração contínua. Na máquina servidora onde está hospedada o ambiente de integração contínua pode-se, e deve-se, implementar o uso de testes automatizados. Sempre que novas alterações são fundidas ao projeto principal, a integração contínua entra em ação e gera uma nova build. Esta nova build então passa por um processo de testes, que irão fazer a análise quanto a integridade da build atual. Se os testes forem bem sucedidos(ou não), a ferramenta de integração gera as respectivas notificações . A esses testes que executam dentro da servidora de integração dão-se o nome de testes automatizados.

## Build Automatizado

O processo de build baseia-se na ideia de compilar, preparar o executável e testar uma aplicação sem a necessidade da intervenção manual de um desenvolvedor. Para tal, é necessário possuir uma estrutura bem organizada do projeto, códigos-fonte independentes de qualquer variável do ambiente de desenvolvimento, modelos para os arquivos de configuração de forma que o build possa ser executado em qualquer ambiente -  desenvolvimento, homologação, teste e produção. Assim, qualquer desenvolvedor poderá executar o script de build garantindo que o processo de validação da funcionalidade implementada será o mesmo aplicado por toda a equipe de desenvolvimento.

## Vantagens da Integração Contínua

Em equipes que adotam metodologias ágeis como eXtreme Programming, Scrum, dentre outras, a integração contínua é um dos pilares da agilidade, pois ela garante que todo o sistema funcione a cada build, não importando o tamanho da equipe e mesmo diversas partes do código estejam sendo alteradas ao mesmo tempo ela garante sua integridade.
A grande vantagem da integração contínua consiste no feedback instantâneo. Que funciona da seguinte forma: a cada commit no repositório, o build é feito automaticamente, executando todos os testes de forma automática, detectando falhas e avisando em tempo real os envolvidos no projeto. Dessa forma se algum commit não compilar ou quebrar qualquer um dos testes, a equipe toma conhecimento instantaneamente (através de e-mail, por exemplo, indicando as falhas e o commit causador das mesmas). O que possibilita uma que uma correção seja efetuada o mais rápido possível, fator esse que é fundamental para não propagar erros ao criar novas funcionalidades e refatorar o código.
De forma simplificada integração contínua é uma forma de trazer segurança em relação a mudanças, você pode fazer modificações sem medo, pois será avisado caso algo saia do esperado.

## Referencias

&lt; [http://www.devmedia.com.br/integracao-continua-uma-introducao-ao-assunto/28002](http://www.devmedia.com.br/integracao-continua-uma-introducao-ao-assunto/28002)&gt; Acesso em  23-05-2017

2. MARTIN,Fowler. Continuous Integration, 2009. Disponível em: &lt;https://martinfowler.com/articles/continuousIntegration.html&gt;. Acesso em: 23 de maio.2017.

FLÁVIO, José. _Build automático de projetos com Continuum_. Disponível em: &lt; [http://www.devmedia.com.br/build-automatico-de-projetos-com-continuum/28914](http://www.devmedia.com.br/build-automatico-de-projetos-com-continuum/28914)&gt; Acesso em 23/05/2017 às 20h.

CAUÊ, Guerra. Integração Contínua e o processo Agile. Disponível em:
<http://blog.caelum.com.br/integracao-continua/>
Acesso em 23 de maio de 2017.

## Integração Contínua com o Travis

O seguinte tutorial objetiva exemplicar de maneira clara os passos necessários para implementar o Travis-CI em repositório com o intuito de realizar a integração contínua no mesmo.

1. Acessar travis-ci.org e fazer fazer cadastro autorizando a vinculação com o GitHub

2. No página de perfil do Travis acesse o '+' para habilitar o travis em um novo repositório

3. Habilite o travis no repositório desejado

4. Na raiz do seu repositório, crie o arquivo .travis.yml

Um exemplo do conteúdo do arquivo é:

```yml
  language: ruby
  services:
  - mysql
  before_script:
  - cp 2017.1-SIGS/SIGS/config/database.yml.travis 2017.1-SIGS/SIGS/config/database.yml
  - mysql -e 'create database myapp_test;' -uroot
  script:
  - cd 2017.1-SIGS3/SIGS
  - bundle install
  - bundle exec rake db:load_config
  - bundle exec rake db:create
  - bundle exec rake db:migrate
  - rake cucumber
  - bundle exec rspec
  - rubocop
  after_sucess:
  - coveralls push
  rvm:
  - 2.3.1
  notifications:
    email:
      recipients:
      - email@example.com
  branches:
    only:
    - master
    - /.*/
```

* **language:** linguagem do projeto<br>[Lista das lingagens aceitas pelo Travis](https://docs.travis-ci.com/user/languages)
* **services:** serviços que serão utilizados pelo Travis

* **before_script:** comandos que devem ser executados antes de rodar o script

* **script:** comandos para executar os testes

* **after_sucess:** comando a ser executado após a finalização dos testes

* **notifications:** configuração de notificações que podem ser associadas ao Travis.<br>[Lista de Notificações](https://docs.travis-ci.com/user/notifications/)

* **branchs:** definição das branchs em que serão rodado os testes


----
**Equipe**
  * Bruno Matias 15/0051212
  * Carlos Aragon 15/0121148
  * Iasmin Mendes 14/0041940
  * Wallacy Braz 15/0059329
