## 1. Introdução

Este documento trata-se de um tutorial técnico que visa demonstrar o básico dos conceitos de Arquitetura de Software e Padrões Arquiteturais, além de demonstrar como esses conceitos são aplicados tanto no MVC quanto na Arquitetura de projetos desenvolvidos a partir do framework Django.

## 2. Arquitetura de Software
“Uma arquitetura de software envolve a descrição de elementos arquiteturais dos quais os sistemas serão construídos, interações entre esses elementos, padrões que guiam suas composições e restrições sobre estes padrões”. GARLAN, 1998.
Exemplo de elementos arquiteturais: bancos de dados, servidores, clientes, componentes, entre outros.

## 3. Padrões Arquiteturais
* Padrões arquiteturais expressam formas de organizar a estrutura do sistema;
* Permitem a construção de uma arquitetura aderente a certas propriedades;
* A escolha do padrão arquitetural pode ser o primeiro passo para a solução de um projeto.

Padrões arquiteturais definem o conjunto de componentes do software, suas responsabilidades e as regras de relacionamentos entre eles.

Por que utilizar uma padrão arquitetural?
* Instrumento para lidar com a complexidade do software a ser construído;
* Ajuda na redução de tempo e custo de desenvolvimento;
* Melhora a capacidade de manuntenção do software.

## 4. MVC

![arquitetura mvc](https://upload.wikimedia.org/wikipedia/commons/b/b5/ModelViewControllerDiagram2.svg)

Um Padrão Arquitetural que separa estruturalmente o projeto do software em três partes:

* Model;
* View;
* Controller.

### 4.1. MVC - Model

Responsável por:
* Representar as classes de domínio;
* Leituras e escritas de dados (interface com o banco de dados).

### 4.2. MVC - Controller

Responsável por:
* Receber requisições dos usuários;
* Processar requisições;
* Controlar as models e views a serem utilizadas.

### 4.3. MVC - View

Responsável por:
* Interface com o usuário;
* Exibição de dados (HTML).

### 4.4. MVC – Diálogo Representativo e informal das camadas

View – Fala Controller ! O usuário acabou de pedir para acessar o Facebook ! Pega os dados de login dele ai.

Controller – Blz. Já te mando a resposta. Ai model, meu parceiro, toma esses dados de login e verifica se ele loga.

Model – Os dados são válidos. Mandando a resposta de login.

Controller – Blz. View, o usuário informou os dados corretos. Vou te mandar os dados dele e você carrega a página de perfil.

View – Vlw. Mostrando ao usuário…

## 5. Arquitetura de Projetos Django

![arquitetura mvt](http://wiki.expertiza.ncsu.edu/images/0/01/Django_arch.JPG)

Segue o Padrão Arquitetural MVT, próprio do Django, aderente ao MVC.
De acordo como o Django Book, o Django segue o padrão MVC suficientemente para ser considerado um framework MVC.

### 5.1. Como Funciona o MVT
O MVT separa estruturalmente o projeto do software em três partes:
* Model;
* View;
* Template.

#### 5.1.1. Model
As Models do MVC e do MVT são equivalentes em responsabilidades.
O framework Django facilita na interface com o banco de dados. Cada classe da modelo se compara a uma tabela do banco de dados, e as instâncias destas classes, representam os registros destas tabelas. Para adicionar valores ao banco, basta definí-los nas respectivas variáveis.
Esta camada contém qualquer coisa e tudo sobre os dados: como acessá-lo , como validá-lo , quais comportamentos que tem e as relações entre os dados.
Para o mapeamento dos dados, não será necessário utilizar códigos em SQL para garantir a persistência dos dados no banco.

#### 5.1.2. View
A camada View é responsável pela implementação das regras de apresentação e negócio do nosso sistema. É nela onde iremos nos comunicar com a Model e a Template, cadastrando e tratando as informações recebidas. Retornando para o usuário uma resposta, como HTMLs, XML, ou erros encontrados.

#### 5.1.3. Template
Templates é a camada que retorna a visão para o usuário do programa. Essa camada é composta por, HTML,CSS, javascript e etc. Geralmente linguagens focadas na apresentação do site para o usuário.

#### 5.1.3. Detalhes arquiteturais de projetos Django
* As resoluções de urls, responsabilidade dada as controllers no MVC, é feita pela própria estrutura do framework;
* O Django oferece uma interface com o banco de dados que permite ao desenvolvedor não se preocupar com a conexão entre suas classes de domínio e banco.

## 6. Referencias

[MVC – Afinal, é o quê ?] (http://tableless.com.br/mvc-afinal-e-o-que/)

[Arquitetura de Software: conceitos e tendências](http://www.inf.pucrs.br/jornada.facin/jafacin_2010/palestras/ArquiteturaDeSoftware.pdf)

[The Django Book](http://gsl.mit.edu/media/programs/south-africa-summer-2015/materials/djangobook.pdf)
