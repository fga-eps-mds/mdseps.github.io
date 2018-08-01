
<a href="http://techblog.netflix.com/2013/08/deploying-netflix-api.html">Deploying the Netflix API</a>

<a href="https://www.youtube.com/watch?v=ZLBhVEo1OG4">Adopting Continuous Delivery</a>

****
 
<ul style="list-style-type:disc">
<li><p align = "justify" >GitHub, de Janeiro a Setembro de 2012 foram realizados 41.679 builds e 12.602 deploys sendo somente no dia 23 de agosto de 2012 realizados 563 builds e 175 deploys.</li>
<li><p align = "justify" >A Amazon uma das maiores varejistas do mundo com serviços de cloud realiza o deploy de um novo software a cada segundo.</li>
<li><p align = "justify" >O Facebook, visando o tamanho e o impacto que ele oferece atualmente, possui um departamento de release engineering desde 2008 com o objetivo de realizar uma liberação por dia como melhorias e novas funcionalidades. Com o novo escritório de engenharia em Londres, tinha como objetivo dobrar o número de deploys.</li></p>

# Integração Contínua

<ul style="list-style-type:disc">
<li><p align = "justify" > Durante o desenvolvimento de um software, seus conjuntos de procedimentos e devido a presença de uma equipe que se constitui de diversos integrantes trabalhando e fazendo o controle de versionamento em um repositório, surge a necessidade de tratar erros e manter cada build da aplicação coesa através da utilização de um dos maiores pilares do desenvolvimento ágil, a integração contínua. A integração é responsável por garantir o funcionamento do código através de feedbacks ainda que o mesmo esteja sendo alterado simultaneamente, agilizando e facilitando a resposta da equipe com relação a possíveis problemas com a criação de outras funcionalidades e contribuindo para a redução do tempo gasto com testes, pois será necessário que o programador teste somente a nova funcionalidade implementada enquanto o servidor da integração contínua fica responsável por realizar os testes do sistema e garantir sua funcionalidade. Ela permite melhor visibilidade do projeto.</li> 
<li><p align = "justify" > A Integração Contínua ajuda a construir confiança para inovar novas melhorias. Os projetos sofrem quando não há dados reais ou recentes para apoiar as decisões. Normalmente, os membros da equipe agrupam essas informações manualmente, exigindo tempo e esforço. O resultado é que muitas vezes a informação relevante nunca é coletada. Desse modo a integração facilita fazendo com que a equipe tome decisões eficazes fornecendo informações sobre o status de construção e métricas de qualidade do código e geralmente projetos que não abraçam essas abordagens são propensos a lançamentos atrasados.</li>


* Vantagens da integração contínua:
  - Feedback instantâneo
  - Segurança em relação a mudanças
  - Agilidade para correção de problemas
  - Automação
  - Sincronização

![Integração](http://i.imgur.com/h1x61BP.png)

## Como ocorre a integração contínua
* Envio do código atualizado para o repositório com o código fonte.
<br><br/>
* Um sistema automatizado observa o sistema de controle de versão. 
   - O sistema automatizado compila o código;
   - O sistema automatizado executa os testes unitários;
   - O sistema automatizado envia o feedback para que os membros da equipe possam conhecer o estado atual da build.

![Int2](http://i.imgur.com/dlXW3av.png)

# Deploy Contínuo
<p align = "justify" > Um processo de Deploy Contínuo (“Continuous Deploy”) é a capacidade de automatizar a homologação e testes do software de um produto desenvolvido de forma automática e rápida, onde a cada alteração significativa seja possível rodar toda a integração contínua, validar o produtos e suas credencias e deixa-lo disponível para produção. Esse processo geralmente é classificado dentro de duas vertentes, que variam de acordo com as capacidades de cada projeto e seus requisitos:</p>

<ol>
<li><p align = "justify" ><b>Totalmente automatizado:</b> uma mudança no código é automaticamente verificada e, se tudo estiver certo, a aplicação vai para produção;</li></p>

<li><p align = "justify" ><b>Semi-automatizado:</b> a ideia é ser capaz de empurrar para produção a última versão estável do aplicativo em qualquer momento apenas apertando um botão. Nesse caso, chamamos de “one-click-deployment”.</li></p>

## Exemplo: Task gradle para subir para google play beta ou production

Antes de configurar a task, voce deve adiquirir o serviceAccountEmail e o jsonFile como descrito no 
[Tutorial de Deploy Automatico na Google Play PDF](https://github.com/GPP-MDS-2016/ImagensDaWiki/raw/master/tutorial_deploy_automático_google_play.pdf)

O ${track} foi configurado como uma variavel de ambiente do gradle no script do circle ci, para especificar se é uma build de produção que vai para a play store ou uma build de testes que vai para emails selecionados. 

```groovy
play {
    track = "${track}"
    serviceAccountEmail = 'example@mail'
    jsonFile = file('/path/to/uknonwnfile.json') //renomeie o file com a extensao .json
}
```

<p align = "justify" >Basicamente, sua ferramenta de integração contínua deverá gerar a build do produto, rodando os testes unitários e de aceitação, ou quaisquer outras medidas de validação do seu produto e de acordo com o configurado, podendo ser por commit ou push em uma branch específica ele irá enviar o seu aplicativo para ser publicado na loja de acordo com suas configurações ou para beta ou para distribuição de produção.</p>

# Build Automation

# Treinamento

* Incluir descrição do treinamento/DOJO - passo a passo - etapas
* Registrar os detalhes da dinâmica
* Infraestrutura Necessária para a dinâmica
* Código referência no projeto da disciplina (00-Disciplina)
* Treinamento em, pelo menos 2 linguagens
