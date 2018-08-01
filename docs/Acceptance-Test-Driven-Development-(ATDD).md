
# Teste de Aceitação
## Definição
<p align = "justify">Testes de aceitação são especificações para o comportamento desejado de um sistema. Esse tipo de teste consegue descrever, dada uma história de usuário, como o sistema deve se comportar de acordo com <i>inputs</i> e interações que o usuário tem com a aplicação e qual deve ser o resultado esperado. Esses testes são criados para avaliar a qualidade externa do que foi desenvolvido, ou seja, verificar se o software (ou as funcionalidades) está pronto e pode ser utilizado por usuários finais. Esse tipo de teste é idealmente implementado de acordo com a descrição do cliente/interessado no produto, que descreve situações de uso da aplicação pelo usuário que devem ser testadas.

## Boas práticas para a criação de testes de aceitação
<p align = "justify">É importante lembrar que o uso do termo *escrever o teste* não necessariamente está relacionado a implementação dele, mas sim à definição do que deve ser testado, quais são os aspectos relevantes do teste e ainda, qual deve ser o resultado esperado.

+ **Pertence ao cliente**

<p align = "justify">O propósito principal dos testes de aceitação é especificar os critérios que irão confirmar que uma história de usuário está funcionando. Logo, a pessoa mais bem posicionada para escrevê-los é o cliente, que tem a maior compreensão do que o produto deve fazer para atender o usuário final.

+ **Devem ser escritos em conjunto**


<p align = "justify">Mesmo que o maior interessado do produto esteja numa melhor posição para definir os testes de aceitação, a falta de conhecimento sobre o funcionamento da metodologia ágil, de histórias de usuário ou de testes em programação pode ser um problema se este escrever os testes sozinho. Por isso, a melhor forma de realizar essa tarefa é definir o que deve ser testado em conjunto, de maneira que toda a equipe se mantenha integrada e tenha noção do escopo de cada teste, além de aumentar a comunicação entre cliente e desenvolvedor.

+ **É sobre o _o que_, e não sobre o _como_**


<p align = "justify">É importante perceber que os testes de aceitação devem focar em </i>onde está o valor para o usuário final</i>, ao invés de em como esse valor é adquirido. Ao escrever um teste de aceitação não se deve focar na implementação, mas sim nas ações que são feitas e os detalhes desnecessários devem ser omitidos.

+ **Deve ser de maneira que o cliente possa compreender**

<p align = "justify">Como é recomendado que os testes sejam escritos em conjunto com o cliente, é fácil compreender que a descrição dos passos de cada teste deve ser feita em uma linguagem simples e fácil, de maneira que o cliente possa compreender o que será feito em cada um e quais são seus objetivos.

+ **Deve ser conciso, preciso e não ambíguo**

<p align = "justify">Uma boa prática na realização dos testes de aceitação é manter a simplicidade na descrição dos passos. Não é necessário descrever quais telas precisam ser acessadas, quais botões são utilizados e outros fatores semelhantes - estes são passos da implementação. O ideal é reforçar apenas o objetivo real do teste, de maneira que a compreensão seja imediata.



# Desenvolvimento Orientado a Teste de Aceitação (ATDD)

## O que é?
<p align = "justify"> <i>O Acceptance Test-Driven Development</i> (ATDD), ou "Desenvolvimento Orientado a Testes de Aceitação", é uma prática de obtenção de requisitos de forma colaborativa aplicada por equipes ágeis, onde exemplos concretos e testes automatizados são utilizados para especificar os requisitos, tornando-os mais claros, com o objetivo de criar especificações executáveis.Eles são gerados em sessões de criação do <i> backlog</i>  do produto, com a participação da equipe, <i> Product Owner</i> , além dos demais interessados.
<p align = "justify">O ATDD é muito similar ao TDD, diferenciando-se deste último pelo fato de termos uma colaboração maior entre o desenvolvedor, analista de qualidade (<i> tester</i> ) e negócio (cliente/partes interessadas). Enquanto o teste unitário está intrinsicamente relacionado com o código, de um ângulo do desenvolvedor (visão interna), o teste de aceitação está voltado ao ponto de vista do usuário, uma visão externa ao sistema.

## Ciclo do desenvolvimento da metodologia ATDD

<p align = "justify">A imagem abaixo representa o ciclo do desenvolvimento orientado a testes de aceitação, composto por 4 passos para aplicá-lo que serão descritos a seguir, conforme Elisabeth Hendrickson.

![](https://cdn.infoq.com/statics_s2_20161011-0321_4/resource/articles/atdd-passo-a-passo/pt/resources/image01.png)

## Aplicando o ATDD
   1. **Debater os requisitos**
<p align = "justify">As histórias de usuário (<i>user story</i>) são refinadas em um workshop ou em uma reunião de preparação do backlog do produto  <a href="https://www.scrumalliance.org/community/articles/2011/march/how-to-hold-an-effective-backlog-grooming-session"> backlog grooming</a>, antes da reunião de planejamento da iteração/sprint. Em ambos os casos, os participantes são uma equipe multifuncional, o Product Owner e, algum outro interessado que potencialmente tem mais informações sobre as histórias.  
<p align = "justify">Algumas perguntas devem ser feitas para elencar exemplos de utilização ou cenários de uso dessas histórias de usuário e, assim, entendermos melhor o que está sendo conversado, de tal forma que esses cenários possam ser escritos como testes.

   2. **Refinar os testes de aceitação**
<p align = "justify">O próximo passo é organizar os testes de aceitação em um formato requerido pelo framework de automação de testes.

   3. **Implementar o código com TDD**
<p align = "justify">O próximo passo é implementar a funcionalidade para fazer com que o teste de aceitação passe.  
<p align = "justify">E, para tanto, o desenvolvimento deve iniciar pelos testes unitários, incluindo todas as condições propostas para as expectativas existentes.  
<p align = "justify">Depois de codificados todos os testes unitários, eles são executados e passamos a uma fase para ajustar aqueles que estão falhando.

   4. **Apresentar os resultados dos testes de aceitação**
<p align = "justify"> Após os testes passarem com sucesso, a história é verificada pelo Product Owner, normalmente em uma reunião de Review/Showcase, onde ele poderá aprová-la ou não. O resultado pode levar à criação de uma nova história ou uma alteração nos testes existentes, a fim de contemplar novos cenários. Outra forma que também funciona bem, e não posterga a validação em uma reunião específica, é a validação de cada história (Review), imediatamente após ela ser desenvolvida pela equipe, de tal maneira que o Product Owner possa fazer isso com o desenvolvedor ou o par de desenvolvedores que a finalizaram.

## Diferença entre ATDD e BDD
<p align = "justify"> O <i>Behavior Driven Development</i> (BDD) ou “Desenvolvimento Guiado por Comportamento” é uma prática ágil que permite uma melhor comunicação entre desenvolvedores, analistas de qualidade, áreas de negócio e pessoas não-técnicas, durante um projeto de software, descrevendo um ciclo de iterações com saídas bem definidas e resultando na entrega de software testado e que funciona.

<p align = "justify"> O BDD dá uma compreensão mais clara sobre o que o sistema deve fazer a partir da perspectiva de todas as partes interessadas, tanto desenvolvedores e analistas quanto de clientes e outros </i>stakeholders</i>. Portanto, ATDD e BDD tem como foco a definição do comportamento esperado do sistema com a participação de todos os interessados, a diferença é que o ATDD explicita o uso dos testes de aceitação enquanto o BDD não os exige, porém na prática do BDD os testes de aceitação são comumente usados.

# Treinamento ATDD
- Incluir descrição do treinamento/DOJO - passo a passo - etapas
- Registrar os detalhes da dinâmica
- Infraestrutura Necessária para a dinâmica
- Código referência no projeto da disciplina (00-Disciplina)
- Treinamento em, pelo menos 2 linguagens

# Referências Bibliográficas
* INFOQ BRASIL.Acceptance Test-Driven Development (ATDD), passo a passo. Disponível em:
<https://www.infoq.com/br/articles/atdd-passo-a-passo>. Acesso em: 19 de out. 2016
