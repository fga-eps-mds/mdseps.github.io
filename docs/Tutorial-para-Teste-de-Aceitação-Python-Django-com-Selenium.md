# Introdução
O teste de aceitação é uma parte fundamental para projetos ágeis. Nessa metodologia os testes são escritos em linguagem natural para alinhar as expectativas do cliente e da equipe de desenvolvimento. Os teste de aceitação eram necessariamente - e devem continuar sendo - feitos pelo cliente em um ambiente próximo do de produção, porém, a equipe de desenvolvimento pode implementar esse tipo de teste em código para ser reproduzível e capaz de medir os efeitos de mudanças solicitadas pelo cliente. Algumas ferramentas foram, portanto, desenvolvidas para automatizar a criação de suítes de teste de aceitação. O projeto [Aloe](http://aloe.readthedocs.io/projects/aloe-webdriver/en/latest/#) permite aos desenvolvedores utilizar linguagem natural para escrever testes que depois são traduzidos em comandos para o selenium. O [Aloe](http://aloe.readthedocs.io/projects/aloe-webdriver/en/latest/#) permite que novos comandos - chamados steps - sejam criados para se adequar a especificidades do projeto em teste. O selenium, por sua vez, permite que diferentes browser sejam utilizados para se realizar os testes. 

O tutorial abaixo irá ensinar como configurar as ferramentas [Aloe](http://aloe.readthedocs.io/projects/aloe-webdriver/en/latest/#) e selenium para desenvolver testes de aceitação para projetos django. Iremos considerar que o usuário está utilizando um ambiente virtual para projetos python e a versão do python seja superior a 3.4. 

### Parte 1 - Criando e Instalando Dependências
**1**- Criar uma pasta para o projeto

**2**- Iniciar o ambiente virtual

**3**- Instalar o django no ambiente virtual

**4**- Criar um projeto

      django-admin startproject example

**5**- Instalar o selenium, dentro do projeto criado

      pip install selenium
**6**- Instalar o django_nose

      pip install django_nose
**7**- Instalar o aloe

      pip install aloe_django
**8**- Instalar o aloe web driver

      pip install aloe_webdriver
**9**- Editar o arquivo settings.py e acrescentar o django nose e o aloe django

      INSTALLED_APPS = [
			‘django_nose’
			‘aloe_django’
		       ]
**10**- Na pasta onde estão as configurações do projeto, criar uma pasta chamada "steps"
      
      mkdir steps
**11**- Entrar na pasta criada

      cd steps
**12**- Criar um arquivo chamado browser.py com o seguinte conteúdo

![12](https://raw.githubusercontent.com/wiki/fga-gpp-mds/00-Disciplina/img/selenium_12.png)

**13**- Para criar as suas próprias steps crie o arquivo steps.py que deve comecar da seguinte forma:

![13](https://raw.githubusercontent.com/wiki/fga-gpp-mds/00-Disciplina/img/selenium_13.png)


### Parte 2 - Desenvolvendo os Testes de Aceitação
_Obs: Para o desenvolvimento do exemplo foi criado um novo app e uma página inicial personalizada para que se possa desenvolver um teste como exemplo. Em seguida será criada uma step personalizada para o usuário se familiarizar._

**1**- Voltar para a pasta do projeto onde se encontra o arquivo de configurações

      cd ..

**2**- Criar uma pasta com o nome features, e entrar nela

      mkdir features

**3**- Editar o arquivo __init__.py para importar o browser

![3](https://raw.githubusercontent.com/wiki/fga-gpp-mds/00-Disciplina/img/selenium_3.png)

_Obs: o projeto usado como exemplo tem o nome example. Esse nome deve ser trocado pelo nome que você escolheu para o seu projeto._

**4**- Criar um arquivo views na pasta do projeto. No exemplo na pasta "example" com o seguinte conteúdo

![4](https://raw.githubusercontent.com/wiki/fga-gpp-mds/00-Disciplina/img/selenium_4.png)

_Obs: como o projeto se chama example o arquivo views.py acima será criado na mesma pasta que contém o arquivo settings._

**5**- Alterar o arquivo urls.py da pasta do projeto. Como no exemplo a seguir:

![5](https://raw.githubusercontent.com/wiki/fga-gpp-mds/00-Disciplina/img/selenium_5.png)

**6**- Por fim, criar um arquivo chamado teste.feature

![6](https://raw.githubusercontent.com/wiki/fga-gpp-mds/00-Disciplina/img/selenium_6.png)

**7**- Criar as migrações necessárias

      python manage.py makemigrations

**8**- Migrar o banco de dados

      python manage.py migrate

**9**- Rodar os testes

      python manage.py harvest

### Parte 3 - Criando seus Próprios steps

_Obs: Para esse exemplo será criado um app novo e um step que insere um texto em um determinado campo._

**1**-  Entrar na pasta onde se encontra o arquivo manage.py

**2**- Criar um novo app chamado user

      python manage.py startapp user

**3**- Criar as pastas user/templates/user

      mkdir -p user/templates/user

**4**- Criar o seguinte template como o nome de mystep.html

![3_4](https://raw.githubusercontent.com/wiki/fga-gpp-mds/00-Disciplina/img/selenium_3_4.png)

**5**- Criar a função no arquivo views do app user:
![3_5](https://raw.githubusercontent.com/wiki/fga-gpp-mds/00-Disciplina/img/selenium_3_5.png)

**6**- Alterar o arquivo urls da pasta de configuração do projeto para:
![3_6](https://raw.githubusercontent.com/wiki/fga-gpp-mds/00-Disciplina/img/selenium_3_6.png)

**7**- Editar o arquivo steps na pasta steps criada na parte 2 desse tutorial
![3_7](https://raw.githubusercontent.com/wiki/fga-gpp-mds/00-Disciplina/img/selenium_3_7.png)

**8**- Criar a pasta user/features/

      mkdir user/features
**9**- Copiar o arquivo __init__py da pasta features criada na parte 2 desse tutorial
 
**10**- Criar um teste na pastas /user/fetatures/
![3_10](https://raw.githubusercontent.com/wiki/fga-gpp-mds/00-Disciplina/img/selenium_3_10.png)

**11**- Rodar os testes

      python manage.py harvest -v 3 user/features/mystep.feature

_Obs: O comando utilizou a flag v para gerar um output mais verboso, também, foi passado o arquivo dos testes funcionais para se evitar rodar testes desnecessários._

A saída deve ser parecida com a imagem abaixo:
![3_11](https://raw.githubusercontent.com/wiki/fga-gpp-mds/00-Disciplina/img/selenium_3_11.png)
