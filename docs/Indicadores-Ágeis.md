
[1. Indicadores de Qualidade do Processo](#1-indicadores-de-qualidade-do-processo)

 * [1.1 Fechamento da _Sprint_](#11-fechamento-da-sprint)
 * [1.2 _Burndown_](#12-burndown)
 * [1.3 _Velocity_](#13-velocity)
 * [1.4 Quadro da Retrospectiva](#14-quadro-da-retrospectiva)
 * [1.5 Quadro de Conhecimento](#15-quadro-de-conhecimento)

[2. Indicadores de Qualidade de Código](#2-indicadores-de-qualidade-de-código)

 * [2.1 Métricas](#21-métricas)

[3. EVM](#3-evm)
 * [3.1 BAC](#31-bac)
 * [3.2 Valor Planejado (PV) e Custo Real (AC)](#32-pv-e-ac)
 * [3.3 Valor Agregado (EV)](#33-valor-agregado-ev)
 * [3.4 Variação do Custo e Variação do Prazo](#34-variação-do-custo-e-variação-do-prazo)
 * [3.5 Índice de Desempenho de Custo (CPI) e Índice de Desempenho de Prazo (SPI)](https://github.com/fga-gpp-mds/00-Disciplina/wiki/Indicadores-%C3%81geis/_edit#35-%C3%8Dndice-de-desempenho-de-custo-cpi-e-%C3%8Dndice-de-desempenho-de-prazo-spi)

---------
## 1. Indicadores de Qualidade do Processo

### 1.1 Fechamento da _Sprint_

<p align = "justify">O fechamento da <i>sprint</i> indica se as histórias planejadas para aquela <i>sprint</i> foram concluídas ou não. Esse indicador auxilia no acompanhamento do progresso do valor agregado do projeto em relação ao que foi planejado até então. O melhor indicador possível é que todas as histórias planejadas estejam concluídas, caso contrário, é necessário adicioná-la no planejamento de futuras <i>sprint</i> se possível.</p>

### 1.2 _Burndown_

<p align = "justify">O <i>burndown</i> indica a frequência de trabalho da equipe durante a <i>sprint</i>. Na coluna vertical, é indicado o número total de pontos planejados para aquela <i>sprint</i> e na coluna horizontal as datas contidas no intervalo da duração da <i>sprint</i>. A linha azul indica os pontos planejados, é decrescente de forma constante e indica que idealmente os pontos devem diminuir gradativamente e constantemente ao passar da <i>sprint</i>. A linha vermelha representa o progresso real da equipe, ou seja, a quantidade de pontos concluído e o período da conclusão. Esse indicador auxilia a equipe à observar a constância dos pontos concluídos e portanto melhorar nas próximas <i>sprints</i> fazendo com que o sistema receba um incremento com uma alta frequência.</p>


### 1.3 _Velocity_

<p align = "justify">O <i>velocity</i> indica a quantidade de pontos que a equipe consegue concluir em uma <i>sprint</i>. O gráfico possui uma coluna azul que indica a quantidade de pontos planejados para aquela <i>sprint</i> e a coluna vermelha que indica a quantidade de pontos concluídos naquela <i>sprint</i>. O valor do velocity (em verde) é calculado a partir da divisão entre o número de pontos concluídos até aquela <i>sprint</i> e o número de semanas de desenvolvimento até aquela sprint. Portanto, este valor indica a média de produtividade da equipe até a <i>sprint</i> indicada.</p>

<p align = "justify">Exemplo de um <i>velocity</i>:

![](https://raw.githubusercontent.com/wiki/fga-gpp-mds/00-Disciplina/img/velocity-exemplo.png)

### 1.4 Quadro da Retrospectiva

<p align = "justify">O quadro da retrospectiva geralmente possui três tópicos:

 * Os **pontos negativos** em relação a <i>sprint</i> realizada. Este indicador ajuda a identificar eventuais problemas no processo.
 * Os **pontos positivos** em relação a <i>sprint</i> realizada. Este indicador ajuda a identificar o que está correto e que deve continuar sendo realizado nas outras <i>sprints</i> no processo.
 * As **melhorias** que são propostas pela equipe de forma a indicar soluções para os pontos negativos.

<p align = "justify">Portanto, é um indicador importante para o processo visando sempre aprimorá-lo para o melhor desenvolvimento do projeto. Era realizada no final de toda <i>sprint</i> através de uma reunião e auxiliava nas decisões gerenciais acerca do processo das outras <i>sprints</i>.</p>


### 1.5 Quadro de Conhecimento

<p align = "justify">O quadro de conhecimento indica o conhecimento de cada integrante da equipe em relação à alguma tecnologia utilizada no projeto. A partir desse quadro, devem ser definidas as duplas de pareamento de forma que a distribuição sempre possua o objetivo da melhor disseminação de conhecimento possível dentro da equipe. É esperado que os indicadores do quadro sempre evoluam durante as <i>sprints</i> indicando a evolução do conhecimento dos integrantes da equipe.</p>

### 1.6 Quadro de Commits

<p align = "justify">Um outro indicador que consegue nos trazer melhor ainda a progressão do trabalho da equipe durante a sprint é o quadro de <i>commit</i>. Com esse quadro é possível se ter uma ideia bem melhor da divisão do trabalho entre a semana, pois se tratando do contexto universitário da matéria de GPP-MDS se torna muito difícil em detrimento de inúmeras razões conseguir manter um burndown aceitável. E com esse quadro de commits tudo fica mais transparente.</p>

![](https://raw.githubusercontent.com/wiki/fga-gpp-mds/2017.2-Receituario-Medico/imagens/sprint_07/commits.png)

<p align="justify">Diferente do burndown o quadro de commits demonstra melhor o trabalho da equipe. Como pode ser visto no exemplo acima no começo da semana houve um progresso considerável nas histórias como mostra o gráfico de commits, mas pode-se notar que quinta e sexta houve uma queda nos commits por conta dos trabalhos de todos os membros da equipe. Dados esses que não conseguem ser observados no burndown dependendo da dificuldade das histórias.</p>

## 2. Indicadores de Qualidade de Código

### 2.1 Métricas

<p align = "justify">As métricas são um indicador para a qualidade do código. No final de toda <i>sprint</i>, elas devem ser analisadas e a partir dessa análise, serem definidos os pontos necessários para a refatoração. Exemplos de métricas:</p>


 * **_Afferent Connections per Class_ (ACC):** Mede o nível de acoplamento de uma classe através do número de outras classes que fazem referência a ela, por meio da utilização de algum método ou atributo.
 * **_Average Cyclomatic Complexity per Method_ (ACCM):** Complexidade ciclomática nada mais é do que o número de caminhos, independentes que um software pode seguir em sua execução, calculado a,partir da representação em grafo das estruturas de controle.
 * **_Average Method Lines of Code_ (AMLOC):** AMLOC representa a média do número de linhas dos métodos de uma classe.
 * **_Depth of Inheritance Tree_ (DIT):** DIT é uma métrica que mede a profundidade que uma classe se encontra na árvore de herança, e caso haja herança múltipla, DIT mede a distância máxima até o nó raiz da árvore de herança.
 * **_Number of Methods_ (NOM):** NOM é uma métrica de tamanho que conta o número de métodos de uma classe.

## 3. EVM

### 3.1 BAC
<p align = "justify"> O custo total planejado consiste no calculo dos pontos totais planejados (PRP) multiplicado pelo custo do ponto. </p>


### 3.2 Valor Planejado (PV) e Custo Real (AC)
<p align = "justify"> O valor planejado (PV) fundamenta-se do calculo entre a Porcentagem planejada Completa (PPC) multiplicado pelo Custo Total Planejado (BAC). A cada sprint este valor será diferente, indicando quanto que o projeto está custando do ponto de vista do planejamento.</p>

<p align = "justify">O Custo Real (AC) fundamenta-se do calculo entre Pontos Completos Reais (PCR) multiplicado pelo Custo Do Ponto. A cada sprint este valor será diferente, indicando o quanto essa sprint está realmente valendo, do ponto de vista dos pontos completado na mesma.</p>


### 3.3 Valor Agregado (EV)

<p align = "justify"> Diferente do valor planejado e do custo real, o valor agregado se difere em cada <i>sprint</i> dependendo do desempenho da equipe na mesma. O valor agregado é um indicador da produtividade da equipe refletida no custo, onde é possível perceber se a equipe está fazendo as entregas conforme o planejado. Para o cálculo do valor agregado, é necessário saber a Porcentagem Concluída na <i>sprint</i> (PPC) e o Valor Planejado (PV).</p>


| PPC = PC / PP |
|---------------|
| EV = PPC * PV |                                                      

Onde, PC = Pontos Concluídos e PP = Pontos Planejados

### 3.4 Variação do Custo e Variação do Prazo

<p align = "justify"> As variações de custo (CV) e de prazo (SV) possuem valores iguais em todas as <i>sprints</i> por consequência de serem calculadas de acordo com o custo real e valor planejado, respectivamente. </p>


| CV = EV - AC |
|:------------:|
| SV = EV - PV |

### 3.5 Índice de Desempenho de Custo (CPI) e Índice de Desempenho de Prazo (SPI)

<p align = "justify"> Assim como as variações, os índices refletem a mesma característica, onde seus valores são iguais nas <i>sprints</i>. A fórmula para o cálculo destes índices encontra-se abaixo:

| CV = EV / AC |
|:------------:|
| SV = EV / PV |