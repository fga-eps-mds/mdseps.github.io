
# Teste Unitário

<a href="http://www.extremeprogramming.org/rules/unittests.html"> Extreme Programming, Unit Tests</a>

<p align="justify">Este teste é utilizado para validar as classes básicas e os componentes do sistema que são considerados os menores elementos testáveis. Consiste em verificar se o fluxo de controle e dados estão corretos. Deve ser realizado no início da iteração.</p>

* São escritos pelos desenvolvedores enquanto codificam o sistema.
* Devem ser feitos de modo que sejam fáceis de executar e e re-executar várias e várias vezes para validar o sistema.
* Devem ser criados para todas as classes do sistema.
* São implementados para todos os métodos do sistema.
* São escritos antes e ao decorrer da produção do sistema.
* Devem ser o mais simples possível.

Referência: [Desenvolvimento XP](http://xp.edugraf.ufsc.br/bin/view/XP/TesteAceitacaoXtesteUnidade)

# Teste Unitário Automatizado
# Stub

<p align="justify"> Muitas vezes, durante a implementação de testes, é possível que surja a necessidade de se testar uma classe que dependa de uma outra ainda não implementada. Isto pode ocorrer especialmente na prática de TDD (<i>Test Driven Development</i>), devido à prática conhecida como <i>babysteps</i>, os "passos de bebê" que dizem que é necessário realizar a implementação nos menores módulos possíveis. Para que seja possível implementar os testes nesses casos, são utilizados os <i>stubs</i>. <i>Stubs</i> são formas simplificadas de objetos reais, algo que se assemelha a uma versão <i>dummy</i> da classe a ser utilizada. Seu propósito é realizar as funções básicas esperadas de uma classe ainda não implementada para que uma outra que a tenha como dependência possa ser testada.</p>  

[O que é um Stub?](http://stackoverflow.com/questions/463278/what-is-a-stub)  
[Um Estudo Sobre Testes Teóricos e Práticos de Software](http://qualipso.icmc.usp.br/files/monografia.pdf)

# Mock

<p align="justify"><i>Mocks</i> são semelhantes a <i>stubs</i> porém, enquanto um <i>stub</i> serve como uma versão <i>dummy</i> de uma classe, um <i>mock</i> serve apenas como uma interface. O <i>mock</i> não possui nenhuma funcionalidade. Ele apenas intercepta as mensagens que saem da classe testada e são destinadas à classe alvo, e retorna um valor pré-estabelecido. Dentro do contexto de TDD, os <i>mocks</i> servem para garantir que as mensagens enviadas terão suas respostas esperadas de forma que os testes possam ser implementados. Além disso, eles são capazes de contar quantas vezes cada função foi chamada para que testes mais elaborados possam ser mais implementados.</p>  

[A abodagem Mock para TDD](http://www.embedded.com/design/prototyping-and-development/4398723/The-mock-object-approach-to-test-driven-development)  

# Boas práticas Testes Unitários

<a href="http://spring.io/blog/2007/01/15/unit-testing-with-stubs-and-mocks/"> Spring io, Unit Testing with Stubs and Mocks</a>

<a href="http://shipit.resultadosdigitais.com.br/blog/ruby-e-rspec-melhorando-a-legibilidade-de-seus-testes/"> Ship it, Ruby e RSpec: melhorando a legibilidade de seus testes</a>

frameworks

# Desenvolvimento Orientado a Testes (TDD)

## Definição

<p align="justify"><i>Test Driven Development</i> (TDD), ou <i>Test-first development</i>, é um conjunto de técnicas de desenvolvimento orientado a testes associadas com <i>Extreme Programming</i> (XP) e metodologia ágil. Com TDD temos um desenvolvimento incremental do código, iniciado pelos testes (Miller,2004). O programador deve ser capaz de escrever um código afim de satisfazer o teste escrito previamente. Dessa forma, possibilita-se a reflexão da modelagem antes de se escrever o código funcional. A consequência é um código fonte bem testado.</p>

<p align="justify">Uma  importante  regra  no  TDD  é:  <i>"If  you  can’t  write  a  test  for  what  you  are about to code, then you shouldn’t even be thinking about coding"</i> [Chaplin 2001]. Outra regra  no  TDD  diz  que  quando  um  defeito  de  <i>software</i> é  encontrado,  casos  de  teste  de unidade são adicionados ao pacote de teste antes de corrigir o código.

<p align="justify">Esta abordagem tende a ser mais coesa, pois o teste do código é parte íntima da codificação,  e  não  um  processo  independente.  Além  disso,  reduz  o  acoplamento  dos componentes do <i>software</i>. Com isso, torna-se possível fazer decisões de projeto em cada estágio do desenvolvimento. Assim, com o passar do tempo, o TDD tornou-se uma das práticas mais populares entre os desenvolvedores de <i>software</i>.</p>

## Ciclo de desenvolvimento orientado a Testes (TDD)

![Ciclo TDD](http://2.bp.blogspot.com/-O5F7OQeP6cY/VkYYHPNvd2I/AAAAAAAAAIw/eyuHiDRrzyM/s1600/TDD.png)

O ciclo do TDD é bem simples:

* Cria-se um teste.
* Executa-se o teste, que por sua vez irá falhar, pois a funcionalidade não foi implementada ainda.
* Codifica-se de modo a fazer o teste passar.
* Executa-se o teste novamente e, caso obtenha sucesso, prossiga para o próximo passo.
* Refatore o código.

## Pontos Positivos do Uso do Método

### Qualidade do código
<p align="justify">Um dos principais ensinamentos, senão o principal, do TDD é que se algo não é possível de ser testado então foi desenvolvido de forma errada. Parece um pouco drástico mas não é. Em pouco tempo utilizando testes o programador percebe mudanças relevantes em sua forma de programar. Em suma o uso de TDD ajuda o programador a elaborar um código com cada vez mais qualidade criando objetos concisos e com menos dependências.

### Raciocínio
<p align="justify">Para que o código torne-se mais conciso, tenha menos acoplamentos e dependências o programador deve forçar seu raciocínio a níveis elevados. É muito difícil criar algo que realmente tenha um bom design. Utilizando TDD o programador praticamente obriga-se a olhar seu código de outra forma normalmente jamais vista antes. Aí é que está a parte legal da coisa toda.</p>

### Segurança
<p align="justify">Ponto importantíssimo para qualquer software nos dias de hoje. Mas não se engane, não estou falando de segurança da informação e sim de segurança ao desenvolver. Pense em uma situação em que o programador tenha um código que desenvolvera ha cerca de um ano. Como normalmente vivemos em um mundo com inúmeros softwares desenvolvidos ao longo de cada ano, torna-se muito difícil lembrar de tudo a respeito de um que merece nossa atenção em determinado momento. Normalmente deve-se realizar um trabalho bastante cauteloso para nova implementação em um software que encontra-se em produção. Toda e qualquer alteração deve ser minunciosamente testada e garantida que não afetará demais módulos do software. Fazer isto manualmente é realmente complicado pois até então não sabe-se (ou lembra-se) ao certo quem afeta quem no sistema. Com a prática de TDD cada pequeno passo do software está devidamente testado. Ou seja, com este cenário o programador pode realizar qualquer alteração sem medo e sem culpa.

<p align="justify">Como cada pequeno passo tomado pelo sistema está testado ao qualquer módulo ou funcionalidade sofrer alteração, com poucos segundos descobre-se se houveram quebras e o melhor de tudo, onde foram essas quebras. Com isso em mãos a correção das quebras torna-se uma tarefa simples sem frustrar o cliente e o usuário.</p>

### Trabalho em equipe
<p align="justify">Por prover mais segurança o trabalho em equipe torna-se muito mais proveitoso eliminando discussões e dúvidas desnecessárias. Ao entrar no desenvolvimento do projeto o novo desenvolvedor tem apenas o trabalho de entender qual <i>task</i> deve ser realizada e ler os testes das features já desenvolvidas. Ao rodar os testes pela primeira vez o programador descobre se está no caminho de ter um entregável mais rapidamente e com segurança. Existem empresas em que um novo programador tem entregáveis logo no primeiro dia de trabalho. Sem testes normalmente haveria um período de adaptação para prévio entendimento do que há no sistema no momento de seu ingresso ao time de desenvolvimento.</p>

### Documentação
<p align="justify">Ao criar testes descritivos estes servem como uma excelente documentação para o <i>software</i>. Quando qualquer programador for rodar os testes, basta habilitar o modo verbose que uma “história” é contada eliminando o árduo trabalho de documentar um <i>software</i> onde nos meios tradicionais tende a defasar-se. O problema é que a documentação tradicional raramente segue o mesmo ritmo do desenvolvimento. Com os testes unitários a “documentação” é gerada antes mesmo da nova <i>feature</i> ser implementada e permanece fiel a qualquer alteração.</p>

## Por que muitos não praticam?

### Dificuldade em começar
<p align="justify">Apesar de uma extensa e clara documentação, iniciar o desenvolvimento orientado a testes pode ser um trabalho árduo para muitos pelo simples fato de que geralmente muitos iniciantes tentam praticá-lo em código já existente. Este definitivamente não é o caminho. A principal característica do desenvolvimento orientado a testes é que ele seja orientado a testes. Em outras palavras o código que realizará sua lógica deve ser criado somente após a criação do teste e isso torna-se algo de difícil aceitação pois ainda não se tem nada e já se faz necessário testar.</p>

### Curva de apendizado
<p align="justify">Complementando o item anterior, este é outro motivo que faz programadores desistirem do desenvolvimento orientado a testes. Como qualquer nova tecnologia, para a pratica de TDD leva-se um bom tempo dependendo disponibilidade e principalmente da vontade do programador.
Tempo
<p align="justify">Engana-se quem pensa que produzirá mais código pelo simples fato de utilizar TDD. O TDD na verdade chega a desacelerar a produção de código. Quando falo em produção de código, me refiro à quantidade de linhas escritas. Mas nisso tudo há vantagens e elas serão descritas mais a frente.</p>

### Cultura
<p align="justify">Muito fala-se de TDD no Brasil, mas ao questionarmos programadores de diversas empresas muitos apresentam os motivos citados acima para não utilizá-lo. Existem sim muitas empresas e programadores que levam a prática a sério e a evangelizam justamente por conhecerem as vantagens que o TDD nos traz.</p>

##  Devo praticar TDD 100% do tempo?

<p align="justify">A resposta para essa pergunta serve para toda e qualquer prática de engenharia de <i>software</i>. É claro que não.

<p align="justify">Como já discutido anteriormente, TDD faz com que o desenvolvedor teste melhor sua aplicação, bem como pense em um design de classes melhor e mais flexível para aquele problema. Mas não é sempre que precisamos disso. Se estamos, por exemplo, escrevendo a implementação de um DAO (classe que se comunica com o banco de dados), talvez escrever os testes antes não vá ajudar tanto, afinal não há grandes decisões de <i>design</i> a serem tomadas em classes como essa, e a funcionalidade tende a ser simples. Escrever o teste depois, portanto, não será tão diferente de escrever o teste antes.

<p align="justify">O desenvolvedor maduro leva em consideração a sua experiência, e entende bem as vantagens da prática. E, na hora certa, fazer uso dela.</p>

## Referências

[1] K. W. Miller,Test Driven Development on the Cheap:Text Files and Explicit Scaffolding. Disponível em: <http://www.ccsc.org/northwest/docarchive/2004/augustmailing2004final.doc>.
[2] GASPARETO, Otávio. Test Driven Development. Universidade Federal do Rio Grande do Sul. Disponível em: <http://www.inf.ufrgs.br/~cesantin/TDD-Otavio.pdf>.
[3] TDD: fundamentos do desenvolvimento orientado a testes. Disponível em: <http://www.devmedia.com.br/tdd-fundamentos-do-desenvolvimento-orientado-a-testes/28151>. Acesso em: 10/11/2016.  
[4] Test-Driven Development. Disponível em: http://tdd.caelum.com.br/. Acesso em: 10/11/2016  
[5] BORGES, Eduardo N. Conceitos e Benefícios do Test Driven Development. Universidade Federal do Rio Grande do Sul. Disponível em: <http://www.inf.ufrgs.br/~cesantin/TDD-Eduardo.pdf>.


# Treinamento TDD

## Introdução

<p align="justify">Para realizar o treinamento de TDD (<i>Test Driven Development</i>), definimos uma metodologia de dinâmica em grupo e a utilizamos em uma atividade. A metodologia escolhida foi uma prática de pareamento já que, assim, podemos aplicar o treinamento em grupos grandes de pessoas. A ideia principal é dividir o TDD em duas partes, para que cada elemento da dupla realize uma etapa.

<p align="justify">Em qualquer aplicação da metodologia TDD existem três partes básicas: a declaração do problema, a transformação dele em testes e por fim a codificação para que os testes sejam aceitos. Sendo assim no treinamento é apresentado o problema, um dos elementos da dupla fará os testes enquanto o outro faz o código. Por fim a ideia é que seja percebido que não é tão trivial quanto parece e vem a ser algo que se aperfeiçoa com prática.

<p align="justify">Além da metodologia, devemos nos atentar a qual linguagem de programação utilizaremos. Tal fator é variável dependendo do grupo que está sendo treinado. Aconselha-se utilizar alguma linguagem que possua um <i>framework</i> de testes e que não exija longas configurações, logo o grupo possa se familiarizar rapidamente. No exemplo dado, utilizamos a linguagem <i>Python</i> com a biblioteca unittest como ferramenta de testes unitários, pois a mesma consegue atender todos esses objetivos.

<p align="justify">Por conta da apresentação teórica, que foi feita em slides, precisamos de um projetor ou televisor no ambiente de treinamento. Além disso, precisamos de um número de computadores maior ou igual à metade do número de participantes. Caso o ambiente de desenvolvimento necessite de maiores configurações, disponibilize-as antes do treinamento para os participantes que desejarem utilizar máquinas próprias e realize os procedimentos necessários nos computadores locais. No exemplo que será trabalhado, foi utilizada uma linguagem que possui suporte nativo na maioria das máquinas dos participantes. Caso não houvesse suporte, seria possível desenvolver em IDEs online, como o IDEOne.</p>



O treinamento é dividido em três etapas:
 - Apresentação teórica sobre o Test Driven Development, tendo como ênfase suas vantagens em uma produção.
 - Breve introdução às ferramentas que serão utilizadas no treinamento.<br>
 - Trabalho prático com aplicação de TDD.

## Desenvolvimento das etapas

### Primeira etapa
Composta pela apresentação teórica sobre TDD, nela ressaltamos as vantagens da prática:<br>
- Não há influência de um código pronto ao codificar os testes, logo você consegue ter testes melhores e consequentemente melhor qualidade de código.
- Com o TDD o programador é forçado a olhar seu código de maneira diferente, isso gera designs diferentes para o código.
- A segurança que o TDD gera para o software é incomparável, pois com testes qualquer mínima alteração tem de ser muito cuidadosa para não quebrar testes anteriores e nem os da feature em si.
- Novos programadores tem vantagem ao entrar no projeto. Em alguns casos o programador novo já tem projetos entregáveis no primeiro dia pois elimina uma necessidade de adaptação gigante.
- Testes descritivos ajudam muito na documentação fácil e enxuta.

Porém nem tudo é um mar de rosas, há também dificuldades (desvantagens) que fazem muitos quererem fugir desta prática:

- A curva de aprendizado é difícil, é algo que necessita de adaptação e prática, porém vem muito bem recompensada.
- O início no meio do projeto é difícil pois os testers tentam aplicar testes a código já existente perdendo algumas vantagens do TDD.
O início da prática TDD é demorada, logo muitas empresas visando que tempo é dinheiro não se interessam em aplicar o método.

### Segunda etapa
Na segunda etapa, a ideia principal é o nivelamento do conhecimento prático de criação de testes na linguagem específica escolhida, Python. Para isso não é necessário muito tempo graças a simplicidade da própria. É mostrado o seguinte código:

![Exemplo](https://github.com/fga-gpp-mds/00-Disciplina/blob/master/MDS_Material/TDD/exemplo.png?raw=true)

<p align="justify">A partir dele, mencionamos as principais peculiaridades da linguagem para que seja possível desenvolver pequenos programas. Caso o problema a ser apresentado na terceira etapa tenha como requisito alguma estrutura mais avançada, esta deve ser mencionada neste momento do treinamento para que o foco permaneça apenas na prática do TDD. Além disso deixa-se o código projetado para que todos possam consultá-lo caso necessário.

<p align="justify">Utilizamos a biblioteca “unittest”, que possibilita realizar testes unitários como demonstrado no código de exemplo. O resultado da execução do exemplo, que contém dois testes válidos e um falhando, é:</p>

![Resultado](https://github.com/fga-gpp-mds/00-Disciplina/blob/master/MDS_Material/TDD/exemploResultado.png?raw=true)

<p align="justify">Apresenta-se um teste falhando para exemplificar o funcionamento da biblioteca de testes e, após esclarecimentos necessários sobre sintaxe, partimos para a terceira e última etapa do treinamento.</p>

### Terceira etapa

<p align="justify">Neste último momento, é apresentado um problema real que deve ser resolvido com o uso do TDD. É orientado aos treinados para se unirem em pares e desenvolverem os testes. Dá-se o tempo necessário para desenvolver os testes baseado na problemática apresentada e, logo em seguida, apresenta-se a solução esperada para o problema até o momento. Como exemplo, temos uma classe Banco com alguns métodos vazios que devem ser preenchidos para tornarem os testes verdadeiros.</p>

![CodigoInicial](https://github.com/fga-gpp-mds/00-Disciplina/blob/master/MDS_Material/TDD/classeBancoEstruturaBasica.png?raw=true)

<p align="justify">Perceba que os testes validam os valores retornados por cada função em determinadas situações. Apresente o código parcial com a classe montada e os testes falhando. A partir daqui, oriente os participantes a tornarem um dos testes verdadeiro e, só após isso, ir para o próximo teste. Dá-se mais tempo para escrever a solução e, ao final, mostra-se o código completo. O código que completa as funções de forma que os testes mostrados como exemplo pode ser visto abaixo.</p>

![ClasseBanco](https://github.com/fga-gpp-mds/00-Disciplina/blob/master/MDS_Material/TDD/classeBanco.png?raw=true)

<p align="justify">Por fim, aponte as vantagens obtidas na prática. No exemplo, podemos mencionar que caso não houvesse o teste de saque inválido, a implementação da função saque poderia não considerar operações que solicitassem valores maiores que o saldo, o que resultaria em saldo negativo. Assim, exemplificamos uma maior qualidade de código como resultado do desenvolvimento orientado a testes. O 
<a href="https://github.com/fga-gpp-mds/00-Disciplina/blob/master/MDS_Material/TDD/banco.py"> código </a> que foi utilizado como exemplo e um modelo de <a href="https://github.com/fga-gpp-mds/00-Disciplina/blob/master/MDS_Material/TDD/TDD%20Apresenta%C3%A7%C3%A3o.pptx"> apresentação </a> em slides, estão disponíveis no repositório da disciplina.</p>
