# Projetos MDS/EP:

## 2018.2 

Os temas serão avaliados/apresentados na segunda aula do semestre para aprovação do projeto.

As áreas de interesse são:
* Data science
* Processamento distribuido
* Processamento de imagem
* Processamento de Linguagem Natural (PLN)

Temas disponíveis (só serão aceitos os temas propostos na disciplina):

- [ ] PDF2knowledge (3 Grupos) + HTML2KNowledge -- até 3 grupos

PDF2knowledge é uma ferramenta para extrair informação a partir de arquivos pdf. Possui os seguintes produtos:
1 - Modulo processamento de pdfs nativos - tem seu próprio package Python  que:
(a) identifica se o arquivo pdf eh nativo (b) extrai informações do arquivo (c) processa o texto do pdf e extrai conteúdo

2 - modulo processamento de pdf escaneados - tem seu próprio package Python que
(a) identifica se o arquivo pdf eh escaneado, (b) identifica se o arquivo digitalizado tem escrito à Mao, caso contrario
 (c) faz pré processamento de imagem para melhorar a qualidade do arquivo , (d) extrai informações do arquivo

3 - modulo de processamento de pdf escaneados à Mao - tem seu próprio package Python que
(a) identifica se o arquivo pdf eh escaneado, (b) identifica se o arquivo digitalizado tem escrito à Mao
 (c) treinamento deep Learning aplicado para extrair informações do arquivo  

Todos os módulos serão disponibilizados também via  API e um serviço para consumir (prova de conceito) 


Fonte de dados(357677 arquivos pdfs): sudo pip3 install salic-receipt


- [ ] Dataviz (até 3 grupos)

- Gerar visualizacoes a partir de indicadores/metricas. (json)
- Processamento de linguagem natural… extração do conteúdo principal 
- Similaridade de documento (como fazer)
- Grafo de relacionamento de documentos (por similaridade de conteudo)

- [ ] App utilidades FGA - Proteja meu carro Unb (2 grupos)

* cadastro de carro
* reconhecimento de placas (checkin)
* app de monitoramento 
* BI de comportamento

- [ ] App utilidades FGA - ifood (1 grupo)
* cadastro de vendedores
* comunicaçao entre vendedores/clientes
* pedidos
* compartilhar localizaçao  ( ideia. uber beta)


- [ ] App utilidades FGA - Bot FGA (1 grupo)
* Canais de comunicacao com o processo
* bots de requisição adm
* bots de requisicoes academicas
* log
* dashboard de serviços
* BI

- [ ]  Projeto X MDIC (1 GRUPO)

- [ ] Projeto Y MPOG (1 GRUPO)

- [ ] BI do mercado de Jogos (1 grupo)

* Reconhecer a paleta de cores a partir de print de jogos
*  estatisticas de jogos

## 2018.1 Uso de conceitos de Data Science

<p align="justify"> A disciplina MDS/GPP terá tema único: Data Science. Os temas serão avaliados/apresentados na segunda aula do semestre para aprovação do projeto.</p> 

As áreas de interesse são:

* Saúde
* Cultura
* Software

Temas sugeridos (os times podem sugerir temas, para serem avaliados. soluções mobiles serão privilegiados):

- [ ] Falko BI - Sistema de BI para avaliar/acompanhar projetos de software livre (métricas/indicadores/sistema de recomendação). Fonte de dados: Github.

- [ ] Gestão de Leitos BI - Sistema de BI para analisar/acompanhar/gerir leitos em hospitais  públicos. Fonte de dados: Dados da secretaria de saúde do DF

- [ ] Gestão de Internações cirúrgicas (alarme alérgico) - escopo ainda a ser definido

- [ ] Dengue BI - monitoramento dos casos de dengue (por localidade), mapa histórico da evolução/avanço da dengue. Sistema de predição de epidemias a partir de dados climáticos em tempo real. Dados: banco histórico de casos confirmados de dengue no brasil/brasília, banco histórico dos dados climáticos. Obs: o algoritmo de predição será disponibilizado.

- [ ] App AGR BI- app (2 grupos: dev nativo e híbrido) BI para análise/monitoramento de indicadores da saúde pública regional (DF). Objetivo: realizar benchmark do desempenho de app nativos vs hibrido no acesso aos recursos de hardware.

- [x] "Jogo" para reabilitação motora de pacientes com AVC. Protótipo disponível, algoritmos implementados em Python (boa implementação), documentação técnica disponível (requisitos bem definidos). Unity3D, python, processamento real-time/paralelo. Coach experiente nas tecnologias.

- [ ] Dr. Down - plataforma para gestão de pacientes infantis (pediátrico) com sindrome de down. Escopo a ser definido.

- [ ] Aplicativo lei rouanet - salic (projeto com design)

- [ ] Cidades Inteligentes - escopo a ser definido

- [ ] "Serenata de Amor" Lei Rouanet - escopo a ser definido.

- [ ] Benchmark de aplicativos mobile nativo vs hibrido - desenvolvimento de uma ferramenta para monitorar a execução de apps mobile tanto nativo quanto hibrido (tempo de acesso à hardware - câmera, GPS, Bluetooth, tempo de execução de funcionalidades similares nas duas implementações). 

# Ferramenta de fixação de aprendizado
---

## Problema

Aprender algo novo não é uma tarefa simples, principalmente porque o nosso
cerebro não absorve todo o conteúdo de uma vez. Mesmo quando algo novo é
aprendido, nos facilmente esquecemos como a curva de esquecimento de Ebbinghaus
demonstra [1]. Vários estudos mostram que é preciso realizar uma série de
revisões em diferentes momentos para tornar o conhecimento permanente e que
existem várias coisas que são importantes de serem feitas para otimizar a
absorção de novos conteúdos.

Existem dezenas de aplicativos na internet que auxiliam o estudande a organizar
a sua agenda de estudos. Contudo, poucos que auxiliam na fixação de
conhecimentos para longo prazo.

## Ideia

Criar um aplicativo que permita ao estudante gerenciar a sua fixação de
conteúdo. O aplicativo deve ter mecânismos que permita ao estudante cadastrar
um novo conteúdo estudado, então o app passa a ser responsável por gerir as
revisões do do assunto. Por exemplo, se o aluno acabou de aprender como o
escalador round-robin funciona, então o app monta a agenda de revisão da
seguinte forma:

1. Revisão: próxima revisão para 3 daqui a 3 horas;
2. Revisão: próxima revisão para 3 daqui a 1 dia;
3. Revisão: próxima revisão para 3 daqui a 1 semana;
4. Revisão: próxima revisão para 3 daqui a 1 mês;
5. Revisão: próxima revisão para 3 daqui a 3 meses.

O app deve notificar o aluno quando o período de revisar estiver próximo (algo
como as notificações do google agenda e do whatapp). Por fim, o app deve permitir
configurar diferentes modos de aprendizado, por exemplo:

1. Modo memorizar;
2. Aprender rápido;
3. Aprendizado longo mas permanente;
4. etc

Além disso, o app pode ter um controle de round de revisão na qual o aluno é
incentivado a fazer coisas que podem potencializar o estudo dele durante a revisão.

De forma bem grosseira, tem dois vídeos no youtube que dão uma orientação dos
requisistos para a parte de agendar aprendizado e para a parte de coisas
necessárias para potencializar o estudo:

1. Sobre fixar conteúdo: https://www.youtube.com/watch?v=mHdy1xS59xA&t=
2. Sobre melhorar potencializar o aprendizado: https://www.youtube.com/watch?v=mHdy1xS59xA&t=

[1] https://en.wikipedia.org/wiki/Forgetting_curve


# Ferramenta de controle de gasto de tempo com coisas não esperadas
---

## Problema

Durante a o nosso dia dia, temos diversas tarefas para serem cumpridas.
Infelizmente, em torno das tarefas importantes muitas vezes temos outras
tarefas que não te levam diretamente a concluir o que você precisa mas por
algum motivo precisam ser executada. Por exemplo, uma pessoa tem que terminar o
relatório mas o chefe constantemente pede para que a mesma pessoa faça uma
tarefa periféricas (como carimbar papeis) e a pessoa acaba perdendo um tempo
importante com outra tarefa. Outro exemplo, é o de uma pessoa que quer malhar
mas tem um tempo grande gasto com o deslocamento. Para facilitar a discussão,
chamamos isto de "Overhead".

O grande problema relacionado aos overheads é que as pessoas normamente não
compreendem quanto tempo foi gasto com coisa não tão relevantes para a
conclusão da tarefa. Contudo, como medir tal tempo? Como manter um histórico do
tempo gasto de forma não produtiva por forças externas?

## Ideia

Criar um aplicativo que permita ao usuário registrar o tempo perdido em uma
tarefa. O princípal requisito é o rápido registro; este deve ser simples e deve
realizado de forma rápida, ou seja, sem overheads. O usuário pode criar algumas
categorias gerais a princípio, como por exemplo: faculdade, trabalho, família,
etc. O usuário pode inserir o tempo total gasto no overhead, como também pode
iniciar e parar um cronômetro.


# Controlar promessas de ano novo
---

## Problema

Todo ano é a mesma história. As pessoas fazem milhões de promessas com a
esperança de ter um ano melhor do que o anterior. Contudo, quase sempre o
resultado é o mesmo: promessas não realizadas. Muitas vezes as pessoas esquecem
o objetivo que tinham definido ou até mesmo lembram mas são objetivos tão
grandes que a pessoa fica desistimulada.

## Ideia

Criar um app que permita ao usuário registrar as suas promessas de ano novo. O
app deve permitir criar uma tarefa maior e subtarefas pertencentes a promessa
maior. Durante o ano, o usuário é lembrado das promessas registradas. Caso o
usuário consiga cumprir a promessa, ele pode compartilhar nas redes sociais de
forma a estimular o mesmo a continuar. O usuário também pode ir criando
subtarefas ao longo do ano para atingir o seu objetivo maior.

Além disto, o app deve contar com um sistema de "ranking" na qual cada tarefa
concluída rende pontos para os usuários. No final, deve haver um rank com todos
os usuários classifcados de acordo com a sua pontuação. Seria interessante se o
usuário tivesse a flexibilidade de mudar a promessa, mas isso custaria alguns
pontos.
 

## 2017.2 Uso de conceitos de Data Science

<p align="justify"> A disciplina MDS/GPP terá tema único: Data Science. As equipes são responsáveis por desenvolver pelo menos 2 propostas de projetos de software no tema (pelo menos 1 dos temas deve estar entre os propostos pela professora). Os temas serão apresentados na sala de aula para aprovação do projeto.</p> 

Algumas áreas de interesse são:

*  Educação/merenda escolar
*  Saúde

### Os temas propostos 2017.2
* Sistema de gestão de infraestrutura de rede metropolitana
   - cliente: Giga candanga - prof. Lazarte (llazarte@unb.br, pa@pauloangelo.com)


* Web monitoramento de indicadores culturais 
     - Contato: Nitai (coodenador TI ministério da cultura) - nitai.silva@cultura.gov.br
     - Palavras-chave: Business Intelligence



* Aplicativos multiplataformas/ webapp para Conselheiros da Merenda Escolar - Cliente: TCU (Minimo 2 grupos)
[http://portal.tcu.gov.br/imprensa/noticias/cartilha-do-tcu-e-fnde-vai-ajudar-na-fiscalizacao-da-merenda-escolar.htm](http://portal.tcu.gov.br/imprensa/noticias/cartilha-do-tcu-e-fnde-vai-ajudar-na-fiscalizacao-da-merenda-escolar.htm)
     - Palavras-chave: atender a 70.000 potenciais usuários (armazenamento e processamento dos dados). Uso da nuvem civica
     - Contato: Marcela de Oliveira Timoteo  (assessora secretário da educação) - marcela.timoteo@tcu.gov.br
* Me representa - auxiliar o eleitor brasileiro a decidirm de forma refletida e individual, seu voto nas próximas eleições do legislativo nacional. App que cruze dados sobre o comportamento de deputdo federais e senadores nas principais votações realizadas na camara e no senado nos ultimos anos.
     - cliente Elida Silpe (BH) - elidasilpe@gmail.com



* Sistema de monitoramento e controle de projetos de software livre
  - Cliente: GPP/MDS - Contato: João Guilherme Silva <joaaogui@gmail.com>
  - Palavras-chave: Sistema BI - identificar anomalias, gerar indicadores/metricas em tempo real
* Smart Triagem pediátrica
  - Cliente:  Dr. Getúlio Morato (medico pediatra)- drgetulio@clinimeta.com
  - Palavras-chave: webapp, arvore de decisões, 

* smart Receituario eletrônico 
  - Cliente:  Dr. Getúlio Morato (medico pediatra)- drgetulio@clinimeta.com
  - Palavras-chave: webapp, arvore de decisões, big data

***

### Os temas de 2017.1 foram
Algumas propostas de interesse são:

* Plataforma de Minicursos abertos UnB -  cliente: laboratório lappis
* Plataforma de Sugestões de Software UnB - cliente: laboratório lappis 
* Plataforma de Jogos UNB - clientes: prof. Edson/Prof Tiago (desenho industrial)
* Infraestrutura para contribuição dos jogos UnB - Cliente: prof. Edson (https://github.com/fgagamedev)
* Acompanhamento da presença e rendimento do aluno - cliente: Escola X (Attany)
* Aplicativo 300 -  cliente: Prof. Fragelli
* Aplicativo - web -- sistema de localização no campus darcy ribeiro - cliente: CPD Central 

Propostas de projetos de software demandados pela UNB:

* Sistema de Controle de cirurgia laparoscópica minimamente invasiva (software crítico e tolerante a falha) - cliente: laboratório Lara UNB. ([https://github.com/lara-unb](https://github.com/lara-unb))
* Simulador bike reabilitação - cliente: laboratórios LART/LARA UNB
* Jogo labirintos urbanos - cliente:  Laboratório Transdisciplinar de Cenografia da UnB ([http://laboratoriodecenografia.blogspot.com.br/](http://laboratoriodecenografia.blogspot.com.br/))
* Plataforma para projetos de cadernos digitais - cliente:  Laboratório Transdisciplinar de Cenografia da UnB ([http://laboratoriodecenografia.blogspot.com.br/](http://laboratoriodecenografia.blogspot.com.br/))

