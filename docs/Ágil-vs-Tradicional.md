## Alunos
- Filipe Ribeiro - 12/0117738
- Gabriel Silva - 12/0118220
- Phelipe Wener - 12/0132893

## Sumário

- [1.0 Introdução](https://github.com/fga-gpp-mds/00-Disciplina/wiki/Ágil-vs-Tradicional---Uma-abordagem-pragmática#10-introdução)
- [2.0 Escopo](https://github.com/fga-gpp-mds/00-Disciplina/wiki/Ágil-vs-Tradicional---Uma-abordagem-pragmática#20-escopo)
- [3.0 Qualidade](https://github.com/fga-gpp-mds/00-Disciplina/wiki/Ágil-vs-Tradicional---Uma-abordagem-pragmática#30-qualidade)
- [4.0 Custos](https://github.com/fga-gpp-mds/00-Disciplina/wiki/Ágil-vs-Tradicional---Uma-abordagem-pragmática#40-custos)
- [5.0 Riscos](https://github.com/fga-gpp-mds/00-Disciplina/wiki/Ágil-vs-Tradicional---Uma-abordagem-pragmática#50-riscos)
- [6.0 Conclusão](https://github.com/fga-gpp-mds/00-Disciplina/wiki/Ágil-vs-Tradicional---Uma-abordagem-pragmática#60-conclusão)
- [7.0 Referências](https://github.com/fga-gpp-mds/00-Disciplina/wiki/Ágil-vs-Tradicional---Uma-abordagem-pragmática#70-referências)

## 1.0 Introdução

Nos dias atuais, a necessidade de automatização de processos se faz cada vez mais presente. Processos são essenciais dentro de qualquer organização em qualquer área de atuação, inclusive em uma das áreas mais recentes, que é a produção de software. A definição de processos de desenvolvimento de software vem com o objetivo de aumentar a produtividade e diminuir os riscos de um projeto(VIEIRA, 2003).

Com o grande crescimento da demanda na produção de software na atualidade os prazos estão cada vez mais curtos e cobrança relacionada a qualidade estão cada vez maiores. A qualidade de um produto de software está diretamente ligada a melhor forma de atender as necessidades do cliente, o que torna um produto totalmente dinâmico. Uma vez que a natureza do produto é dinâmica existem grandes dificuldades no gerenciamento do desenvolvimento, por exemplo: a essência volátil dos requisitos do cliente(TAVARES, 2008).

O produto de software também possui outra característica única, é totalmente desenvolvido por pessoas, o que gera outra gama de variáveis que podem causar risco e mudanças imprevisíveis no meio de processo de produção (SCHWABER, 2004).

Com base nessas dificuldades, vários processo durante a história da Engenharia de Software foram desenvolvidos, par amenizar esses problemas. Podemos citar destes processos, os processos cascata, interativo, espiral, incremental.

Considerando que para cada contexto de desenvolvimento, um processo pode ser melhor aplicado, foram analisadas e comparadas - nos quesitos de escopo, custo, qualidade e risco - uma versus a outra duas abordagens: Rational Unified Process(RUP) e metodologias ágeis(MA).

## 2.0 Escopo

Nessa sessão, visa-se mostrar a diferente abordagem e mentalidade entre a definição de escopo, ou seja, mostrar as diferenças em como é desenvolvido e gerenciado os requisito em abordagens tradicionais versus a abordagem em metodologias ágeis trazendo primeiro uma visão geral do que é requisito e seu gerenciamento.

### 2.1 Requisito

A elicitação, compreensão e manutenção de requisitos é um fator comum à todas as metodologias de desenvolvimento de software, uma vez que esse item (requisito) é o fundamento de qualquer produto de software.(Aurum; Wohlin, 2005)

O fato de que requisitos são vitais ao desenvolvimento de software deve-se principalmente às responsabilidades que um requisito desempenha no produto, isto é, este identifica, modela, comunica e documenta o sistema, o ambiente de uso e quem o usará. (Paetsch; Eberlein; Maurer, 2003)

### 2.2 Processo genérico de Gerênciamento de Requisitos

O processo genérico consiste de cinco atividades fundamentais. São elas: Elicitação, Análise e Negociação, Documentação, Validação e Gerenciamento (Paetsch; Eberlein; Maurer, 2003). Cada abordagem tem a sua forma de executar cada uma das etapas como veremos na ultima sessão desse capítulo.

#### 2.2.1 Elicitação

Nessa atividade do processo genérico, tenta-se descobrir e definir o que faz e o que não faz parte do sistema com auxilio dos envolvidos no projeto (gerentes, desenvolvedores, cliente). Nessa etapa é fundamental o desenvolvimento correto do produto desejado, isto é, fundamental para fazer o software que resolve o problema do cliente.(Leffingwell, 2003)

#### 2.2.2 Análise e Negociação

Nessa etapa do processo a checagem dos requisitos é realizado. Verifica-se a consistência, a necessidade, a capacidade de realização e a completude. De forma geral, há uma verificação se é possível fazer, se o que foi definido realmente é necessário para o sistema e se nada está em conflito ou incompleto. Essa é uma forma de melhorar a definição do produto. (Leffingwell, 2003)

#### 2.2.3 Documentação

Nessa etapa é documentado todos os requisitos definidos. Dessa forma é possível uma visão do produto à ser realizado por todos os envolvidos. Assim como também servirá como insumo para as atividade de manutenção. (Leffingwell, 2003)

#### 2.2.4 Validação

Nessa etapa são validados os requisitos, ou seja, se estão descrevendo corretamente o produto. (Leffingwell, 2003)

#### 2.2.5 Gerenciamento de Requisitos

O objetivo do gerenciamento é capturar, armazenar, disseminar e gerenciar informação. Gerenciamento de requisitos inclui todas as atividades preocupadas com mudanças, controle de versão e rastreamento de requisitos. Rastreamento de requisitos provê relacionamento entre requisitos, projeto e implementação de um sistema a fim de gerenciar suas mudanças. (Leffingwell, 2003)

### 2.3 Aplicação nas abordagens

Na abordagem tradicional, a definição e gerenciamento de requisitos é realizada por uma equipe específica dentro do projeto. Por exemplo o papel de engenheiro de requisitos é fundamental para essa abordagem. Nas metodologias ágeis toda a equipe é responsável pela elicitação e gerenciamento de requisitos.

Um outro ponto que podemos levar em consideração são os padrões estabelecidos pelas abordagens tradicionais:

- Padrão IEEE 830 – Práticas Recomendadas para Especificação de Requisitos de Software (IEEE, 1998);
- Padrão IEEE 1233 – Guia para Desenvolvimento de Especificação de Requisitos de Sistemas (IEEE, 1998);
- Padrão IEEE 1362 – Guia para Tecnologia da Informação – Definição de Sistema – Documento de Conceito de Operações (IEEE, 1998)

Uma vez que a abordagem tradicional define um processo metódico, há a necessidade de definir diretrizes. Dessa forma toda a equipe deve ser guiada por essas diretrizes tornando o processo reproduzível e bem definido.

Por outro lado, as metodologias ágeis não se baseiam nestes padrões para elicitação e gerenciamento de requisitos. Nessa abordagem, o processo é mais pragmático. E a equipe tem a autonomia de aprender no decorrer do processo o que melhor se adapta ao contexto dos envolvidos e do projeto (Aurum; Wohlin, 2005). Por exemplo: na abordagem tradicional há todo um processo bem definido de gerenciamento de mudança, com responsável e entrada e saída. Já a abordagem ágil, lida com a mudança de forma diferente, o entendimento dessa abordagem é que variabilidade de requisitos é um problema constante em praticamente todos os projetos de software, portanto, o suporte a essas mudanças está incluso em seu processo como um ponto forte dando liberdade à cada equipe para definir como deve ser realizada (Tomayko JE, 2002).

Outro fator importante é que as metodologias ágeis não lidam com a mudança ou necessidade de forma futura. Foca-se nas necessidade pela quais agregam valor ao cliente. Assim, evita-se o desenvolvimento de uma arquitetura geral e robusta que requer um esforço grande. Busca-se incrementar o software modulo por modulo . Diferente da abordagem tradicional onde há a necessidade de uma definição de uma arquitetura robusta (Beck, 1999).

O entendimento da natureza volátio de requisitos tem um grande impacto na capacidade das metodologias ágeis de serem _enxutos_. Em geral, uma arquitetura genérica e mais abrangente é esperada para suportar a variabilidade nos requisitos. Contudo, uma arquitetura mais complexa custa mais, não só para a equipe de desenvolvimento, mas também para a equipe de manutenção e correção de erros (Aurum; Wohlin, 2005).

## 3.0 Qualidade

A qualidade de produtos de software pode ser provida através de processos preventivos ou de um processo iterativo de melhoria contínua que requer o controle de gerenciamento, coordenação e _feedback_ de muitos processos simultâneos: (1) os processos do ciclo de vida do software, (2) detecção, remoção e prevenção de defeitos, e (3) o processo de melhoria de qualidade (SWEBOK, 2014).

A maioria das metodologias tentam implementar o conceito descrito pelo SWEBOK a sua maneira. Essencialmente, metodologias tradicionais e ágeis não se distinguem no quesito de qualidade, em ambos tem-se o controle da qualidade do produto realizados de diversos modos, seja de uma forma mais preventiva, através do comprimento de métricas, ou na adoção de práticas comumente ágeis pareamento ou TDD.

Entretanto, no tradicional nota-se que o conceito de qualidade está mais associado a ações preventivas, conforme mostra o tópico de Gerenciamento de Qualidade do PMBOK, que é dividido na visão geral como: Planejar e gerenciar, realizar a garantia de qualidade e realizar o controle (PMI, 2013, ADAPTADO). Nas metodologias tradicionais é perceptível um esforço em se documentar mecanismos que irão suportar monitoria e controle da qualidade, tal como orienta o PMBOK, claro que na prática não se usa tudo que um _framework_ como o RUP fornece, nesse ponto, como em qualquer metodologia é necessário senso crítico.

Nos métodos ágeis, conforme argumentado por (D’AMORIM, 2008), percebe-se uma tentativa de produção enxuta, inspirada na forma de produção _just-in-time_, o qual o gerenciamento da qualidade se dá através de práticas. Fato notável no manifesto ágil por: Indivíduos e interações mais que processos e ferramentas (BECK, 2013). O que não quer dizer que os processos ágeis não documentam e nem planejam insumos para melhoria de qualidade, mas que a visão da metodologia é de um viés mais prático. Por exemplo, no XP, vemos uma tentativa de controle de qualidade voltado fundamentalmente nos testes, tal que as métricas desses são o indicativo mínimo de qualidade que um projeto XP demanda. Nos processos tradicionais, essas métricas estão compreendidas em uma especificação previamente acordada, que pode acompanhar testes, métricas de código, conformidade da solução, entre outras expectativas de qualidade.

## 4.0 Custos

A gerencia de custos do projeto tem como meta a inclusão dos processos
envolvidos por meio de estimativas, orçamentos e controle de custos de forma que 
o projeto possa ser executado dentro do orçamento inicialmente acordado entre os
envolvidos. A gerencia de custos tem como maior foco de atuação os custos de
recursos necessários para conclusão as atividades do projeto.
Dessa forma deve-se levar em consideração o efeito das decisões de projeto no
custo recorrente a subsequencia do uso, prestando a manutenção e o suporte do
produto, serviço ou qualquer produto do projeto. O  planejamento de
gerenciamento dos custos ocorre nas fases iniciais do projeto fornecendo a
estrutura para cada processo do gerenciamento dos custos para que seu
desempenho seja eficiente e coordenado (BONFIN; NUNES; HESTENREITER, 2012).

### 4.1 Gerência de Custos em Metodologias Tradicionais

Metodologias de desenvolvimento de _software_ usam como base o PMBOK para
gerência de custos. o PMBOK propõe as seguintes atividades: 
* Planejar o Gerenciamento dos Custos: é o processo que visa o estabelecimento
das políticas, documentos, gestão e controle de custos;
* Estimar os Custos: processo de desenvolvimento visando estimações de recursos
monetários para terminar as atividades do projeto;
* Determinar o Orçamento:  é o processo de agregação  dos custos estimados de
atividades individuais ou pacotes de trabalho para estabelecer uma linha de
base dos custos autorizada;
* Controlar os Custos: processo de monitoramento do andamento do projeto para
atualização do seu orçamento e gerenciamento das mudanças feitas na linha de
base de custos (MACEDO, 2014).

Os custos são determinados com base na agregação dos custos estimados de
atividades individuais, ou seja, a entrega do que foi inicialmente planejado,
sendo que uma vez que a entrega foi feita em um tempo diferente do combinado,
esse custo inicial tende a sofrer variações (MACEDO, 2014).

#### 4.1.1 Termos e fórmulas para cálculo de valores
* **VP** - Valor Planejado;
* **VA** - Valor Agregado;
* **CR** - Custo Real;
* **ONT** - Orçamento no término;
* **ENT** - Estimativa No Término;
* **EPT** - Estimativa para Término;
* **VNT** - Variação no Términoi (quanto acima ou abaixo do orçamento esperamos
estar no fim do projeto).

|                          Sigla                          |             Fórmula            |                                                               Descrição                                                               |
|:-------------------------------------------------------:|:------------------------------:|:-------------------------------------------------------------------------------------------------------------------------------------:|
|                  Variação de Custo (VC)                 |           VC = VA-CR           | Negativa está acima do orçamento Positiva está abaixo do orçamento                                                                    |
|                 Variação do Prazo (VPR)                 |          VPR = VA – VP         | Negativa o projeto está atrasado em relação ao cronograma Positiva está adiantado em relação ao cronograma.                           |
|           Índice de Desempenho de Custo (IDC)           |          IDC = VA / CR         | Um valor igual ou maior que 1 indica condição favorável. Um valor menor que 1 indica condição desfavorável.                           |
|            Índice de Desempenho de Prazo (IDP)          |          IDP = VA / VP         | Um valor igual ou maior que 1 indica uma condição favorável Um valor menor que 1 indica uma condição desfavorável.                    |
|              Estimativa Para Término (EPT)              |         EPT = ENT – CR         | Quanto o projeto vai custar.                                                                                                          |
|                Variância No Término (VNT)               |         VNT = ONT – ENT        | Quanto acima ou abaixo do orçamento nós vamos estar ao final do projeto?                                                              |
|               IDC por um período de tempo               |          IDC = VA / CR         | IDC calculado por um período de tempo ao invés de todo o tempo até o momento.                                                         |
|                      IDC acumulado                      |       IDCac = Vac / CRac       | Ac – Aumento até o total acumulado.                                                                                                   |
| Índice de Desempenho Para Término (IDPT) baseado na ENT | IDPT = (ONT – VA) / (ENT – CR) | É a projeção calculada do desempenho de custos que deve ser atingido no trabalho restante para alcançar um objetivo de gerenciamento. |
| Índice de Desempenho Para Término (IDPT) baseado no ONT | IDPT = (ONT – VA) / (ONT – CR) | É a projeção calculada do desempenho de custos que deve ser atingido no trabalho restante para alcançar um objetivo de gerenciamento. |

### 4.2 Gerência de Custos em Metodologias Ágeis

Tendo como base a definição no _Framework_ Scrum, não se encontram registros
relacionados a Gerenciamento de Custo, com isso, pode-se dizer que o Scrum não
cuida desta prática formalmente. Porém a outros pontos a serem analisados. O **MVP**
é o _Minimum Viable Product_, que significa a menor parte utilizável de um
produto, que uma vez lançada  agrega retorno imediato ao investimento para um 
determinado cliente (DIAS, 2009). 

Com o MVP consolidado, cria-se então a entrada para o Planejamento da Release,
sendo que o próximo passo é a descoberta da **velocidade** do time para
consolidar um plano funcional (se não houver um registro da velocidade do time,
pelo fato de ser um time novo; deve-se estimar analogamente com base na
experiência) (OLIVEIRA, 2015).

Uma vez que esse cenário está estabelecido, o próximo passo é estimar o tamanho,
esforço e complexidade das _User Stories_. Nesse caso deve-se separar todas as
histórias que compõem o seu MVP. Feito isso, é feita uma reunião com o time e
iniciada uma sessão de estimativa, utilizando por exemplo o _Planing Poker_

Com o planejamento concluído e as histórias pontuadas, sendo por exemplo uma de
7 pontos, uma de 2 pontos e uma de 1 ponto, pode-se fazer a seguinte distribuição de
custo que será empregado para cada história: 70% do custo na história 7 pontos,
20% na de 2 pontos e 10% na de 1 ponto.

Esses insumos são fundamentais para fornecer o **Gerenciamento do Valor Agregado**,
do inglês, o _**Earned Value Management**_ (EVM). O EVM nada mais é do que uma
técnica que permiti, de forma clara e objetiva, avaliar e medir o avanço de um
projeto no que se refere a custos e prazos, baseando-se no trabalho realizado
versus o planejado. O valor agregado é obtido a partir do produto da porcentagem
de conclusão daquilo que foi planejado, junto ao valor estimado (OLIVEIRA, 2015).

## 5.0 Riscos

Riscos: Eventos específicos que podem ocorrer em um certo nível de probabilidade e os quais, se acontecerem, terão um impacto sobre alguns aspectos do projeto(duração, custo ou escopo)(IESE, 2013).

Em ambas abordagens vê-se mecanismos para controle dos riscos do projeto. Nos projetos tradicionais percebe-se um esforço mais preventivo, tal que seja feito um planejamento de como os riscos do projeto serão gerenciados, suas ações corretivas e níveis de impacto. Nos ágeis, esses riscos são mitigados com a prática, onde as técnicas de _mettings_ são fundamentais para a identificação, mitigação ou até mesmo eliminação desses riscos.

## 6.0 Conclusão

Pode-se concluir que metodologias de desenvolvimento ágeis são melhor executadas
em times com maior experiência, uma vez  que se baseiam muito em experimentar e analisar os resultados. Com isso em mente, é difícil imaginar que
um projeto possa apresentar um grande sucesso usando essa forma de trabalho uma
vez que os membros não tenham tantas experiências para basear o empirismo que
que norteia o desenvolvimento. Por outro lado o tradicional define cada papel e
cada etapa do processo, dando insumos para guiar equipes imaturas com relação as
atividades que devem ser realizadas em seus respectivos momentos.

Sabe-se que dentro do contexto de desenvolvimento de software não há um modelo
perfeito e todas as decisões devem ser tomadas com relação a descrição do projeto,
pessoas envolvidas e processo a ser seguido. Cabe aos membros de cada equipe
terem a maturidade necessária para adoção da melhor metodologia que se encaixa
no contexto de trabalho.

## 7.0 Referências

- VIEIRA, M. Gerenciamento de Projetos de Tecnologia da Informação. Rio Janeiro, Brasil. 2003.
- TAVARES, A. Gerência de Projetos com PMBOK e Scrum: um estudo de caso. Gravataí, Brasil. 2008.
- SCHWABER, K. Agile Project Management with Scrum. Microsoft Press. 2004.
- D'AMORIM, F. Engenharia de requisitos para métodos ágeis. Universidade Federal de Pernambuco. Brasil. 2008.
- Aurum, Aybüke; Wohlin, Claes (Eds.) “Engineering and Managing Software Requirements” 2005.
- Paetsch F., Eberlein A., Maurer F. Requirements engineering and Agile software development. In Proceedings of 8th International Workshop on Enterprise Security, Linz, Austria. 2003.
- Tomayko JE. Engineering of unstable requirements using Agile methods. In: Proceedings of International Conference on Time-Constrained Requirements Engineering, Essen, Germany. 2002.
- Leffingwell, D., Widrig, D. Managing Software Requirements: A Use Case Approach, 2a. Edição, Addison-Wesley. 2003.
- BONFIM, D. F.; NUNES, P. C. A.; HASTENREITER, F. Project Management by PMBOK Guide: Challenges for Managers. São Paulo, Brasil. 2012.
- OLIVEIRA, P. P. MVP e a Gestão de Custos em Projetos Ágeis. 2015.
- DIAS, A. Existe Gestão de Custo no Scrum?. 2009.
- MACEDO, D. Gerenciamento dos Custos do Projeto. 2014.
- Beck K. Extreme programming explained: Embrace change. Addison-Wesley, United Kingdom. 1999.
- Leffingwell, D., Widrig, D., Managing Software Requirements: A Use Case Approach, 2a. Edição, Addison-Wesley, 2003.
- IESE, A Project Management Methodology. University of Navarra. 2013.
- SWEBOK, Guide to the Software Engineering Body of Knowledge. IEEE, 2014.
- IEEE Standard 830 IEEE recommended practice for software requirements. 1998.
- IEEE Standard 1233 IEEE guide for developing system requirements specifications. 1998.
- IEEE Standard 1362 IEEE guide for information technology: System definition, concept of operations document. 1998.