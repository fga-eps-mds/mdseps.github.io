# Sumário

[1. Analiso](#1-analiso)

>[1.1 Instalação](#11-instalacao)

>[1.2 Rodando o Analizo no seu Projeto](#12-rodando-o-analizo-no-seu-projeto)

>[1.3 Entendendo as Métricas](#13-entendendo-as-métricas)

[2. Mezuro](#2-mezuro)

[3. Mezuro vs Analizo](#3-mezuro-vs-analizo)


# 1. Analizo

## 1.1 Instalação

Esta instalação está disponível em inglês na página [https://github.com/analizo/analizo/blob/master/INSTALL.md](https://github.com/analizo/analizo/blob/master/INSTALL.md).

### Pacote Debian

1) Crie um arquivo "analizo.list" na pasta /etc/apt/sources.list.d/

```
cd /etc/apt/sources.list.d/
gedit analizo.list
```

O arquivo se abrirá no editor de texto, adicione as linhas:

```
deb http://analizo.org/download/ ./
deb-src http://analizo.org/download/ ./
```

Salve e feche o editor de texto.

2) Adicione a chave de assinatura do repositório para sua lista de chaves confiáveis:

```
# wget -O - http://analizo.org/download/signing-key.asc | apt-key add -
```

3) Atualize a lista de pacotes:

```
$ apt-get update
```

4) Instale o analizo:

```
$ apt-get install analizo
```

## 1.2 Rodando o Analizo no seu Projeto


1) Vá até a pasta de código fonte do seu projeto pelo terminal

Exemplo:
```
 cd git/GPP2016/fork/2016.2-WikiLegis/app/src/main/java/
```

<p align = "justify" >Note que a pasta de código fonte pode não ser a pasta raiz da sua aplicação. Rodando as métricas na pasta raiz pode ser que algum componente da linguagem ou da IDE interfira nas suas medições.</p>

2) Rode o comando para gerar as métricas no arquivo metrics.out:

```
analizo metrics > metrics.out
```

<p align = "justify" >Pronto, as métricas do seu código já estão no arquivo metrics.out, podendo ser aberto com seu editor de texto favorito.</p>

## 1.3 Entendendo as Métricas

<p align = "justify" >Ao ver esses números, não se assuste. Faça a pesquisa sobre as métricas importantes para o seu contexto e tenha anotado as abreviações (Exemplo: accm = Avarage cyclomatic complexity = Complexidade ciclomática média). Nem tudo que está aqui você quer. Ele te dará variações da mesma métrica, mas você não precisará de todas. Algumas variações que merecem menção honrosa são:</p>

* **metric_mean**: A média dos dados dessa métrica. (Percentil 0%)
* **metric_quantile_max**: O valor máximo dessa métrica em uma classe.
* **metric_quantile_median**: A mediana dos dados dessa métrica
* **metric_quantile_min**: O valor minimo dessa métrica em uma classe.
* **metric_quantile_ninety_five**: Valor médio da métrica observando apenas os valores 5% mais altos.(Percentil 95%)
* **accm_quantile_upper**: Valor médio da métrica observando apenas os valores 25% mais altos. (Percentil 75%)

Para um melhor entendimento das métricas de Percentil veja o [artigo](https://social.stoa.usp.br/articles/0030/6046/tesePauloMeirelles.pdf).


<p align = "justify" >Além das métricas Gerais média de todo o código, mais pra baixo ele te dará o valor em cada classe, o que pode ser útil para encontrar as classes que estão abaixando os valores das suas métricas e deixando seus indicadores ruins.</p>

# 2. Mezuro

<p align = "justify" >O Mezuro é um ferramenta de análise de métricas de qualidade de código produzido pelo Centro de Competência em Software Livre (CCSL), da Universidade de São Paulo (USP). Este utiliza do Analizo para calcular as métricas e análisá-las, para posteriomente mostrar as resultantes de código em seu portal. 

<p align = "justify" >O Mezuro é uma aplicação web e por isso não necessita de instalação, sendo necessário criar uma conta e adicionar o repositório de seu projeto nele. Sua utilização é bem intuitiva e fácil, dispondo de uma interface gráfica amigável.

# 3. Mezuro vs Analizo

<p align = "justify" >Apesar do Mezuro ser mais <i>User friendly</i>, ele não te dá a liberdade de escolher as métricas como o Analizo dá. Por outro lado, ele já te dá indicadores de forma formatada e pronta para ser apresentada em uma <i>Wiki</i> por exemplo. 
<p align = "justify" >Outro ponto positivo do Analizo é ser situado em sua máquina, assim não ocorre a possível demora causada pela dependência de servidor, como temos com o Mesuro.