# Configuração de Ambiente  

Django é um framework de alto nível voltado para Web Python. Tem como objetivo promover um desenvolvimento rápido e limpo, atingindo prazos e expectativas com qualidade.  
Como algumas aplicações são baseadas em python, é preferencial que, a instalação das dependências do Django seja feita em um ambiente virtual que será o escopo de atuação do framework e demais atualizações de dependências.  

Para configurar corretamente siga os passos abaixo direto no seu terminal:  
**OBS:** Configuração realizada em linux 64 bits.  

**Passo 1**  
Verifique se você possui uma versão do python em sua máquina.  
      ``$ python3 --version``  

**Passo 2**  
Caso não tenha essa ou nenhuma versão instalada, execute:  
**Ubuntu**  
      ``$ sudo apt-get install python3.4``  

Feito isso, vamos agora instalar o ambiente virtual (**virtualenv**).  

**Passo 3**  
Primeiro vamos verificar se possui uma versão do virtualenv através do comando:  
	``$ virtualenv --version``  
	
**Passo 4**  
Caso não possua uma versão instalada, efetue o download usando:  
	``$ sudo apt-get install python-virtualenv``  

Pronto, com o virtualenv instalado podemos continuar.  

**Passo 5**  
Inicie agora um diretório qualquer(com nome a seu gosto):  
	``$ mkdir meu_django``  
Acesse o diretório:  
	``$ cd meu_django``  
E aqui vamos criar o ambiente virutal chamado ambvirtual(nome definido a seu gosto), digite:  
	``python3 -m venv ambvirtual``  

**Passo 6**  
Feito isso, perceba que teremos um novo diretório chamado ambvirtual.  
Vamos iniciar sua execução através de:  
	``$ source ambvirtual/bin/activate``  

Para finalizar essa etapa, seu terminal deve-se parecer com algo assim:  
	``(ambvirtual) ~/meu_django $``  

   <i>  **Passo 6.1 (Opcional)**</i>  
<i>Para facilitar a ativação do ambiente virtual, também é possível instalar o virtualenvwrapper, utilizando o seguinte comando:</i>  
        ``$ sudo apt-get install virtualenvwrapper``  

<i>Após isso, é possível ativar o ambiente virtual utilizando apenas o seguinte comando:</i>  
        ``$ workon ambvirtual``  

Assim como no outro método, ao final, seu terminal deve-se parecer com algo assim:  
	``(ambvirtual) ~/meu_django $``  

**Passo 7**  
Agora dentro da virtualenv basta instalar o Django:  
	``(ambvirtual) ~$ pip install django``  

OBS.: caso não possua o pip instalado em sua máquina, execute o comando:  
        ``apt-get install python-pip``  

E para ter a versão mais recente, execute:   
        ``pip install -U pip``
ou 
        ``pip install --upgrade pip`` 
 
Pronto! Seu ambiente para desenvolvimento Django está configurado.    

**Saindo do ambiente virtual**  
Caso você precise sair do ambiente virtual (para criar um outro ambiente por exemplo), utilizando o virtualenvwrapper, você só precisa utilizar o seguinte comando:  
        ``(ambvirtual) ~$ deactivate``  

Em seguida, seu terminal terá o seguinte modelo:  
         ``~$``

***

# DOJO de linguagem (material didático)
Agora que o ambiente está instalado, antes de criar um projeto Django,
vamos discutir sobre: como o Django funciona? Qual é a sua arquitetura?
Como o código pode ser modularizado?

## Arquitetura Django
O Django trabalha com uma arquitetura semelhante a tão famosa Model, View,
Controller (MVC), já bem estabelecida do Ruby on Rails e formando base da
maioria dos projetos Java Web. Porém, o Django utiliza-se de nomenclaturas
diferentes para representar seus semelhantes nas linguagens a pouco citadas:
Model, View, Template. Carinhosamente apelidados, de forma cômica, de MTV.

### Model
As models são responsáveis pelas abstrações dos objetos da vida real no código.
Lembra-se das classes, com atributos e métodos? Pois bem, se encaixam aqui.
Elas se encarregarão de dar as caras e funcionalidades para as futuras instâncias
dos objetos. A seguir, será demostrado um exemplo de uma model. Não se atente, por
enquanto, à sintaxe. Foque nos atributos declarados e nos métodos def.

``` python
class Person(models.Model):
    first_name = models.CharField(max_length=30)
    last_name = models.CharField(max_length=30)

    def speak(self):
        print("Hello World!")
```
### View

É a camada lógica do sistema, ela contém os métodos de acesso as Models e as Templates. Funciona como uma ponte entre as outras duas camadas. As requisições são tratadas pelo próprio Django e não pela View.
 
### Template

É a camada encarregada de mostrar nossa aplicação para o usuário e a que manda as requisições para View. Em outras palavras, é a interface da aplicação e manda os dados do usuário para processamento ou mostra algo à ele.

## Criando um projeto Django
Dentro do ambiente virtual, basta executar o comando django-admin para utilizar
a interface que o Django disponibiliza. Iremos criar o projeto chamado my_twitter.

`django-admin startproject my_twitter`

Este comando irá criar uma pasta chamada my_twitter contendo vários arquivos e uma pasta.
Esta pasta representa o app principal do projeto, onde contém o arquivo de configuração
e o arquivo principal de Url's. Os principais são:

* Pasta com o nome do projeto: my_twitter
* Arquivo de configuração: settings.py 
* Arquivo de Url's: urls.py
* Arquivo de gerenciamento do projeto: manage.py

A árvore de diretórios neste momento irá ser representada da seguinte forma:<br><br>
.<br>
├── [4.0K]  my_twitter/<br>
│   ├── [   0]  __init__.py<br>
│   ├── [3.0K]  settings.py<br>
│   ├── [ 767]  urls.py<br>
│   └── [ 398]  wsgi.py<br>
└── [ 808]  manage.py*<br>

Agora vamos testar se tudo ocorreu bem. Vamos iniciar o servidor do django.

`python3 manage.py runserver `

Acesse seu navegador com o seguinte link:

localhost:8000

## Divisão em Apps
O django trabalha com sistema de vários apps que formam a aplicação. A ideia é que esses apps
sejam plugáveis e portáveis. Dessa maneira, um app pode ser desenvolvido em uma aplicação e
utilizado em outra. Cada app possui toda estrutura necessária e imposta pela arquitetura do
django para que funcione bem: Views, models, templates, etc.

Um app é composto basicamente pelos seguintes componentes:
* Models
* Views
* Templates
* Tests
* Static
* Migrations
* Forms
* Tests

Segue abaixo um exemplo de um app convencional Django, criado pelo professor Fábio Mendes.
[Code School](https://github.com/fabiommendes/codeschool/tree/master/src/cs_auth).

## Criando um aplicativo Django
Vamos primeiramente, criar um aplicativo responsável por apresentar a página inicial do nosso
projeto. Vamos chamá-lo de home. E toda vez que o nosso site for solicitado por uma url, iremos
apresentar a página inicial definida neste app. 

Desta maneira, para criar o app, é necessário apenas utilizar o commando:

`django-admin startapp home`

Será criado um app com o nome app, chamado home. Um exemplo deste app criado segue no
repositório do [Dustwitter](https://github.com/TiagoAssuncao/dustwitter/tree/master/dustwitter/home).

O primeiro ponto que vamos implementar é a apresentação de um HTML simples para a exibição
quando solicitarmos a página. 

Crie uma pasta dentro do app que acabou de ser criado, chamada templates, dentro desta pasta
serão armazenados todos os templates do aplicativo home.

`mkdir templates`

Além disso, há uma convenção de se criar uma pasta dentro da templates com o nome do aplicativo:

`cd templates; mkdir home`

Dentro desta pasta será criado o arquivo index.html, que será nosso primeiro HTML e será responsável
por receber apresentar a tela inicial do sistema. 

Crie o arquivo com a tag H1 com o título 'Hello' dentro:

`cd home`<br>
`echo "<h1>Hello</h1" > index.html`

Agora temos que fazer com que o usuário tenha este HTML renderizado quando o usuário entrar no site
com a url localhost:8000.

Primeiramente temos que mapear as urls. Existe dois tipos de arquivos urls que iremos utilizar neste
aplicativo.  O primeiro tipo é a url master, que redireciona uma url para algum app do sistema. O outro
tipo é a url interna do app, onde ela mapeia uma url em um método da view.

Primeiramente, vamos adicionar um mapeamento da urls principal para o app home. Para isso, adicione
este import no arquivo:

```Python
from django.conf.urls import url, include
```


Após, inclua o app quando a expressão regular "" for capturada:

```Python
urlpatterns = [
    url(r'^admin/', admin.site.urls),
    url(r'^', include('home.urls', namespace='home')),
]
```

Isto irá apontar a url para o aplicativo. Agora, precisamos criar o arquivo de urls dentro do app:

```Shell
touch home/urls.py
```

Copie o seguinte código para dentro do arquivo urls do app home:

```Python
from django.conf.urls import url, include
from django.contrib import admin
from . import views

app_name = 'home'
urlpatterns = [
    url(r'^', views.index, name='index'),
]
```

Isto irá redirecionar o usuário para o método index da view do app home.

Agora vamos implementar o método que irá renderizar o template no browser do usuário.

Dentro do arquivo home/views.py, crie o método index:

```Python
from django.shortcuts import render

# Create your views here.
def index(request):
    pass
```

O método está criado, porém, ainda não estamos renderizando a página para o usuário.
Iremos fazer isso utilizando o método render.

O método render recebe como parâmetro a request que o método index recebe no parâmetro
e o caminho do html que deve ser renderizado.

Desta maneira, atualize o seu método para que fique desta maneira:
```Python
from django.shortcuts import render

# Create your views here.
def index(request):
    return render(request, 'home/index.html', context)

```

Para que tudo funcione perfeitamente, só é necessário adicionar o nosso app para o
arquivo de configuração do django. Assim, abra o arquivo settings.py e adicione o app
no INSTALLED_APPS:

```Python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'home',
]
```

***


# DOJO de testes (material didático)
## Testes Unitários
Testes unitários são testes que são expressados como métodos em uma classe _Python_ que seja uma subclasse de **unittest.TestCase**. Por exemplo:

```Python
import unittest

 class CalculatorTestCase(unittest.TestCase):
    """Every test class must to have a setUp method"""
    def setUp(self):
        self.calc = src.calculator.Calculator()

     def testAdd(self):
         self.assertEquals(self.calc.add(2, 5), 7)
         self.assertEquals(self.calc.add(0, 0), 0)
```

Uma vez que os testes estão escritos, a fim de executá-los, deve-se rodar o seguinte comando:

`$ ./manage.py test`

Quando os testes estão para ser rodados, o comportamento padrão do utilitário de teste é encontrar todas as subclasses de unittest.TestCase, imediatamente montar um conjunto de testes e rodá-lo.

Porém, quando só se quer rodar os testes para uma aplicação específica, basta adicionar o nome da aplicação à linha de comando. Por exemplo, se além de _'myproject.calculator'_, possui-se _'myproject.invoice'_, é possível rodar somente os testes unitários de _'myproject.invoice'_ através de:

`$ ./manage.py test invoice`

###Asserts em Python
Existem diversos tipos de asserts que checam e reportam falhas, os quais podem ser utilizados nos testes unitários de Python. Os mais básicos são:

|Método                   |O que checa?          |
|-------------------------|----------------------|
|assertEqual(a, b)        |a == b                |
|assertNotEqual(a, b)     |a != b                |
|assertTrue(x)            |bool(x) é Verdadeiro  |
|assertFalse(x)           |bool(x) é Falso       |
|assertIs(a, b)           |a é b                 |
|assertIsNot(a, b)        |a não é b             |
|assertIsNone(x)          |x é Nulo              |
|assertIsNotNone(x)       |x não é Nulo          |
|assertIn(a, b)           |a está dentro de b    |
|assertNotIn(a, b)        |a não está dentro de b|
|assertIsInstance(a, b)   |a é instância de b    |
|assertNotIsInstance(a, b)|não é instância de b  |

Além disso, há checagens mais específicas, são elas:

|Método                      |O que checa?      |
|----------------------------|------------------|
|assertAlmostEqual(a, b)     |round(a-b, 7) == 0|
|assertNotAlmostEqual(a, b)  |round(a-b, 7) != 0|
|assertGreater(a, b)         |a > b             |
|assertGreaterEqual(a, b)    |a >= b            |
|assertLess(a, b)            |a < b             |
|assertLessEqual(a, b)       |a <= b            |


##Teste de Aceitação
Existem diversas maneiras diferentes de se realizar testes de aceitação em Django/Python. Além disso, há diversos módulos que são capazes de rodar este tipo de teste.

O tutorial [BDD com Django e Behave](http://klauslaube.com.br/2016/02/03/bdd-com-django-e-behave.html) é bastante interessante, fácil, completo e didático. Este tutorial ensina como fazer teste de aceitação em Django utilizando o `behave-django`.

# Repositórios educativos


# Material didático produzido na disciplina (times, coaches, etc)
* Dustwitter - Aplicação Web com o intuito de apresentar e introduzir os integrantes do grupo 07 - SME ao mundo do django de forma pratica e exemplificada. Produzido pelo Aluno Tiago Assuncao, possui algumas das principais funcionalidades já implementadas e funcionando. Para executar o aplicativo, ler README.md [Dustwitter](https://github.com/TiagoAssuncao/dustwitter)

# Referências

* (https://docs.djangoproject.com) Contém a documentação Django em formato de fácil compreendimento.
* Recomenda-se fortemente a leitura da documentação do Django, pois nela estão escritos os principais tópicos, e tutoriais utilizados na disciplina de MDS [Django Documentation](https://docs.djangoproject.com/pt-br/1.10/) <br><br>
* [The Django Book, Chapter 5.](http://www.djangobook.com/en/2.0/chapter05.html)
* [Unit Test Framework](https://docs.python.org/2/library/unittest.html)