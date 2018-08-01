# Teste Automatizado

## Introdução

<p align="justify"> O controle da qualidade em um produto de <i>software</i> não é fácil de ser controlado, visto a complexidade atribuída a certos produtos de <i>software</i>, sendo necessário sempre atender a visão do cliente ao <i>software</i>. Os testes unitários testam parte do código, normalmente testam funções separadamente. O teste automatizado ou teste aceitação realiza o teste no <i>software</i> na visão do cliente, concluindo as etapas realizadas pelo usuário.</p>
    
## O que o teste irá fazer ?

<b>Objetivo do teste:</b> Realizar busca de uma matéria em um site.   
<b>Site:</b> Wikipedia    
<b>Objetivo principal:</b> Achar o artigo relacionado à testes em geral    

Passos:
* Abrir o site.
* Colocar no campo de buscas o valor: “Testes”. 
* Pressionar o botão de pesquisa.
* Verificar os dados da página.

## Ferramenta

A ferramenta escolhida é a “Selenium IDE” que é uma ferramenta que funciona diretamente no Firefox na forma de plugin. Os motivos de escolha dessa ferramenta são:
* Facilidade de uso.
* Facilidade de exportar código de teste para outras linguagens.
* Opção de gravar o teste.
* Executado diretamente no navegador.

## Instalação

<p align="justify"> Para a instalação do Selenium IDE é necessário ter o Firefox instalado na máquina, se não já o tiver faça o download e instale-o pelo <i>link</i>: 
<a href="http://br.mozdev.org/firefox/download/"> Download do Firefox.</a></p>
 

<p align="justify"> Após ter instalado o Firefox, é necessário instalar o <i>plugin</i> do Selenium IDE pelo <i>link</i>: 
<a href="https://addons.mozilla.org/en-US/firefox/addon/selenium-ide/"> Add-on Selenium IDE</a></p>
</p>

![Add-to-firefox](http://s11.postimg.org/kkc1a8bxf/add.png)  
<i>Clique no botão Add to Firefox</i>      

Após reiniciar o navegador pressione: 
> Ctrl + Alt  + S 
Este comando irá iniciar o plugin <i>Selenium IDE</i>.

A seguinte janela deverá aparecer:   

![Selenium-IDE-Interface.png](http://s16.postimg.org/70emgau2t/Selenium_IDE_Interface.png)

## Realizando o caso de teste

<p align="justify"> No campo “URL Base” digite: <i>http://www.wikipedia.org</i>.   
Selecione o comando open com alvo barra se já não estiver na tabela do teste.</p>

![Command-open.png](http://s9.postimg.org/tgd69adqn/Command_open.png)

<p align="justify"> Pressione com o botão direito na aba de test case o primeiro teste. Clique em propriedades. Troque o nome do caso de teste por: <i>“Pesquisa no Wikipedia”</i>.

<p align="justify"> Agora que já temos o comando open de abrir a página, precisamos colocar o que queremos pesquisar no campo de busca.
Para isso na aba de comandos do <i>Selenium IDE</i> selecione o do tipo <i>type</i>. Pressione o botão <i>Select</i> e com a página do <i>Wikipedia</i> aberta clique no campo de busca. Agora vamos colocar o valor que queremos procurar, Digite no campo valor: “TESTE”. 

<p align="justify"> Por fim, precisamos pressionar o botão de pesquisa para pesquisar efetivamente. Em comando coloque clickAndWait, pressione <i>Select</i> no alvo e clique em cima do botão de pesquisa na página do <i>Wikipedia</i>.

<p align="justify"> Após isso precisamos verificar se a página carregada corresponde a página que queremos, assim teremos certeza que o teste passou. Para isso coloque em comando assertText, em alvo clique em <i>Select</i> e pressione no Título da página, e no valor coloque Teste.

<p align="justify"> A página do <i>Selenium IDE</i> fica da seguinte forma:</p>

![Selenium-IDE-Teste-Pronto.png](http://s14.postimg.org/fe6q0mn3l/Selenium_IDE_Teste_Pronto.png)

Após isso é necessário apenas apertar <i>“play”</i> para todos os casos de teste.
A página será preenchida automaticamente e o resultado será exibido e o teste concluído.

## Código do teste

Código gerado no tutorial, para usa-lo basta clicar na aba “código fonte” e colar esse código lá.

> [Código do teste](http://textuploader.com/dsc25)