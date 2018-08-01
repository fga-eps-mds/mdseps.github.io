# EAP (Estrutura Analítica de Projeto) / <i>WBS (Work Breakdown Structure)</i>

* **Autores:**
    * Elmar Roberto - [GitHub](https://github.com/ElmarRoberto)
    * Cecília Dib - [GitHub](https://github.com/ceciliadib)
    * Maria Carolina - [GitHub](https://github.com/carolinaferreira)

[1. Introdução](#1-introdução)

[2. Visão de etapas do PMBOK](#2-visão-de-etapas-do-pmbok)

[3. Tipos de EAP](#3-tipos-de-eap)
>[3.1 Por pacotes de trabalho](#31-por-pacotes-de-trabalho)

>[3.2 Por fases](#32-por-fases)

>[3.1 Por entregas principais](#33-por-entregas-principais)

[4. Dicas para a criação de uma EAP](#4-dicas-para-a-criação-de-uma-eap)
>[4.1 Decomposição](#41-decomposição)

>[4.2 Planeje entregas, não planeje ações](#42-planeje-entregas-não-planeje-ações)

>[4.3 Detalhando](#43-detalhando)

>[4.4 Utilize modelos](#44-utilize-modelos)

>[4.5 O Custo do Gerenciamento não pode ser maior que o custo da tarefa](#45-o-custo-do-gerenciamento-não-pode-ser-maior-que-o-custo-da-tarefa)

[5. Tópicos relevantes para criação da EAP](#5-tópicos-relevantes-para-criação-da-eap)

[6. Referência Bibliográfica](#6-referência-bibliográfica)

## 1. Introdução

<p align="justify">&emsp;&emsp;Segundo o guia PMBOK, EAP é uma <b>decomposição hierárquica do escopo total do trabalho</b> a ser executado pela equipe a fim de alcançar os objetivos do projeto e criar as entregas requeridas, em outras palavras, é a subdivisão das entregas em componentes menores e mais facilmente gerenciáveis.</p>
<p align="justify">&emsp;&emsp;Uns dos principais benefícios para o uso desta ferramentas em gerenciamento de projetos, é a validação do escopo em fases de projeto com o cliente, abertura de visão para elaboração do cronograma, redução no número de surpresas e <b>melhor base para estimar fases futuros do projeto</b>.</p>
<p align="justify">&emsp;&emsp;Segundo o site WorkBreakDownStructure [3], se elaborada e revisada uma boa EAP em seu projeto, é possível então determinar os processos necessários, tempo e os custos previstos para alcançar cada uma das metas, mas claro que para chegar a esse nível a equipe necessita de alta nível de abstração de gerência de projeto em conjunto com certo nível de maturidade e experiência para prever esses tipo de dados, mesmo assim, pode ser visto que é uma poderosa ferramenta.</b>

Exemplo de uma EAP com previsão de custo e tempo para atividades:

![ert](https://cloud.githubusercontent.com/assets/18271197/26567201/aa1a4a3a-44cf-11e7-97bb-cfedf19c34df.png)

## 2. Visão de etapas do PMBOK

<p align="justify">&emsp;&emsp;Como em todo tópico descrito no guia, toda atividade tem suas entradas, ferramentas e técnicas e saídas, no caso da EAP são estes:</p>

* **Entradas:** Informações requeridas para o cumprimento do objetivo;
>* Plano de gerenciamento do escopo
>* Especificação do escopo do projeto
>* Documentação dos requisitos
>* Fatores ambientais da Empresa
>* Ativos de processos organizacionais
* **Ferramentas e técnicas:** Atividades disponíveis para a elaboração do objetivo;
>* Decomposição
>* Opinião especializada
* **Saídas:** Resultados ao término do objetivo.
>* Linha de base de escopo
>* Atualizações

<p align="justify">&emsp;&emsp;<u>OBS:</u> Para maior detalhamento das etapas, acesse o guia.</p>

## 3. Tipos de EAP
<p align="justify">&emsp;&emsp;A escolha de algum tipo para o projeto depende da interpretação de contexto e viabilidade do que se encaixa melhor no processo de abstração das atividades.</p>

### 3.1 Por pacotes de trabalho

![pacotes](https://cloud.githubusercontent.com/assets/18271197/26565209/9b7d10b2-44bf-11e7-8c8e-bfc08abe018d.png)

### 3.2 Por fases

![fases](https://cloud.githubusercontent.com/assets/18271197/26566398/3c58fcd6-44c9-11e7-9f39-fc70842fc651.png)

### 3.3 Por entregas principais

![entrgas](https://cloud.githubusercontent.com/assets/18271197/26566396/34cd95f8-44c9-11e7-9331-f45f5bdbc5c6.png)


## 4. Dicas para a criação de uma EAP

<p align="justify">&emsp;&emsp;As dicas abaixo tem como fonte base o site <i>Project Builder</i> [2], nele são descritas 5 dicas para facilitar a elaboração de uma EAP.</p>

### 4.1 Decomposição

<p align="justify">&emsp;&emsp;Deve-se decompor a EAP em fases e atividades até um nível que seja fácil de se gerenciar. Esse processo pode ser realizado em dois caminhos, o primeiro é a descrição em alto nível apenas com atividades que agregam valor real ao cliente e o segundo é em casos de projetos que o interessado tenha alto conhecimento técnico ou apenas a equipe de desenvolvimento vá utilizar a EAP para validações completas, assim, pode-se seguir com descrições mais técnicas e de baixo nível de abstração que podem agregar ou não valor real ao cliente buscando descrições com padrão de importância e prioridade, mas essa segunda não é a forma mais recomendada, pois a estrutura analítica tem em sua base o foco de descrição e entendimento de atividades para os <i>stakeholders</i> que nem sempre entenderão termos técnicos. Mais adiante serão passadas dicas de boas práticas para essa ferramenta. Na EAP podem-se se seguir as seguintes váriações de descrições tomando como base os tipos já citados neste documento:</p>

* **Primeiro nível (nível 0):** 
    * Nome do projeto.
* **Segundo nível (nível 1, também chamado de primeiro nível de decomposição):** É o nível onde é imposta a estrátegia de execução, dentro deste nível pode haver variações dependendo do modo que o projeto necessitará de ser dividido. Abaixo seguem alguns modelos, mas outros exemplos podem ser abstraidos pela equipe dependendo de cada contexto.
    * **Tipo 1:** Por entregas completas. Ex.: Releases. (mais indicado a disciplina de GPP).
    * **Tipo 2:** Por fases do ciclo de vida do projeto. Por exemplo, análise, design, construção e testes.
    * **Tipo 3:** Por pontos de trabalho. Ex.: Planejamento, Documentação, Desenvolvimento etc.

* **Níveis seguintes**: Dentro destes níveis podem haver váriações dependendo do que já foi escrito no início deste tópico.

    * **Tipo 1:** Segue com atividades com maior nível de abstração e que apenas agregam valor real ao cliente. (mais indicado a disciplina de GPP e à qualquer outro projeto.) Ex:

    ![eap](https://cloud.githubusercontent.com/assets/18271197/26565927/b2370cf8-44c5-11e7-9950-06a212c404df.png)

    * **Tipo 2:** Segue com atividades técnicas de prioridade de gerência ou prioridade de implementação. Ex: 

    ![eap](https://cloud.githubusercontent.com/assets/18271197/26566066/a2949774-44c6-11e7-85a1-599af5a179eb.JPG)

<p align="justify">&emsp;&emsp;Observa-se que a grande diferença dos dois está no tipo de descrição das atividades. <b>Ex.:</b> no primeiro tipo, a atividade de teste é descrita como "Testes Técnicos do Software" que dá a ideia geral à um interessado leigo, e no segundo tipo é descrito como "Fazer Teste Funcional" dando a ideia mais técnica da atividade. Então tudo é uma questão de abstração do contexto.</p>

### 4.2 Planeje entregas, não planeje ações

<p align="justify">&emsp;&emsp;Se tentarmos desenvolver a EAP orientada a ação, ela incluirá ações de mais ou de menos. No lugar de planejar ações, concentre-se na decomposição por entrega, assim você assegurará que a EAP não exagere na visão dos métodos, permitindo ideias mais criativas e inovadoras por parte dos participantes do projeto.</p>

### 4.3 Detalhando

<p align="justify">&emsp;&emsp;Outro ponto importante é a granularidade que você vai aplicar. Não há uma regra única, mas as boas práticas recomendam que você tenha pacotes com durações adequadas ao seu projeto. Não é interessante ter pacotes de curta duração, como 30 minutos (a não ser que eles sejam relevantes ao projeto), ou pacotes de longa duração como, por exemplo, um mês. Em casos assim, recomenda-se quebrar em pacotes menores. Quando tiver dúvida se vale a pena continuar decompondo, faça-se as seguintes perguntas:</p>

* O trabalho tem um responsável? 
* O esforço foi estimado ou dá pra estimar? 
* Tem custo ou dá para estimá-lo? (Em casos de prévia estimativa de custos)

<p align="justify">&emsp;&emsp;Se todas essas perguntas tiverem resposta afirmativa, você pode continuar a decompor, caso contrário você pode parar e retornar ao nível acima.</p>

### 4.4 Utilize modelos

<p align="justify">&emsp;&emsp;Se há projetos recorrentes dentro de sua organização, no caso da descrição desta <i>wiki</i> o contexto são os diferentes projetos realizados nos diferentes semestres que a disciplina de GPP esta ou foi aplicada, envolva outros gerentes de projetos, a professora e os <i>coachs</i> com o objetivo de trabalhar a definição de modelos padrão para novos projetos. Utilizando dos projetos exemplos e trocando experiências, as chances de desenvolvimento de EAP’S eficientes aumentam, já avaliadas na prática.</p>

### 4.5 O Custo do Gerenciamento não pode ser maior que o custo da tarefa

<p align="justify">&emsp;&emsp;A última dica é que o custo para se gerenciar um pacote obviamente não deve ser maior que o custo do mesmo (nem metade ou mesmo 20% – sugerimos no máximo 10%). Afinal, a EAP deve nos ajudar no gerenciamento, e não criar mais burocracia.</p>

## 5. Tópicos relevantes para criação da EAP

<p align="justify">&emsp;&emsp;Esses passos foram retirados da referência [3], a descrição da fonte foi escolhido por ser baseada no guia PMBOK.</p>

* O primeiro nível, ou mais alto, representa o produto final.
* As entregas subsequentes contêm pacotes de trabalho atribuídos ao tipos de divisões do projeto.
* Todos os elementos da estrutura de divisão de trabalho não precisam ser definidos para o mesmo nível.
* O pacote de trabalho define o trabalho, a duração e os custos para as tarefas necessárias para produzir o subproduto, no caso da disciplina é necessário apenas a definição do trabalho.
* Os pacotes de trabalho não devem exceder 10 dias de duração.
* Os pacotes de trabalho devem ser independentes de outros pacotes de trabalho na estrutura de repartição do trabalho.
* Os pacotes de trabalho são únicos e não devem ser duplicados em toda a estrutura de repartição do trabalho.


### 6 Referência Bibliográfica

* [1] PMBOK, GUIA. "Um guia do conjunto de conhecimentos em gerenciamento de projetos." Project Management Institute. 2004.
* [2] Project Builder, EAP - Disponível em - <<http://www.projectbuilder.com.br/blog-home/entry/projetos/5-dicas-para-facilitar-a-criacao-de-uma-estrutura-analitica-de-projeto>>. Acessado em 29 de Maio de 2017.
* [3] WorkBreakDownStructure, WBS - Disponível em - <<http://www.workbreakdownstructure.com/>>. Acessado em 29 de Maio de 2017.