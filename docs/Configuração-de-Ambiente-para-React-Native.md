<p align = "justify"> Para realizar a configuração do ambiente necessário para desenvolver o front-end da aplicação pode-se seguir os seguintes passos:</p>

<p align = "justify"> Primeiramente vamos verificar se o Node (também é necessário possuir o npm, que vem junto a instalação do Node) está instalado no seu ambiente, caso não esteja, siga os passos que seguem, caso você já tenha alguma versão do Node já instalada no seu ambiente, pule para a criação do projeto em React Native no passo 9. </p>

<b>OBS:</b> Na data atual 05/11/2017, o React Native não está funcionando corretamente nas versões do Node 8.0 em diante. Recomenda-se a instalação da versão 6.11.5.

**Passo 1**  
Cheque se o <i>Node</i> já está instalado em sua máquina.

``$ node --version``

**Passo 2**  
Caso não esteja instalado em sua máquina, faça o download acessando o site do <a href="https://nodejs.org/en/">Node.js<a>, e fazendo o download da ferramenta.

<p align = "justify">Caso a versão o Node apresente problemas com o ReactNative posteriormente, tente retorná-la a versão 6.11.5 através deste <a href="https://stackoverflow.com/questions/7718313/how-to-change-to-an-older-version-of-node-js">link</a>. </p>

<p align = "justify">Caso a versão do npm apresente problemas com o ReactNative posteriormente, tente retorná-la a versão 3.10.10 através deste <a href="https://stackoverflow.com/questions/15890958/how-do-i-install-a-previous-version-of-an-npm-package">link</a>. </p>

**Passo 3**  
Descompacte o <i>.tar</i> em uma pasta de sua preferência. Recomenda-se a sua home, e o tutorial leva em consideração que a pasta estará lá.

**Passo 4**  
Renomeie a pasta descompactada para um nome mais simples como "node".

**Passo 5**  
Abra seu terminal e vá para a home, utilize o comando abaixo para se certificar de que estará lá:

``$ cd``

**Passo 6**  
Abra o arquivo <b>.bashrc</b> com seu editor de textos favorito. Nesse caso usou-se o sublime:

``$ subl .bashrc``

**Passo 7**  
No arquivo que abrirá, digite no fim:

`` PATH="/home/SEU_USUÁRIO/node/bin/:$PATH" ``

**OBS.:** Troque SEU_USUÁRIO, pelo seu nome de usuário na sua máquina.

Salve e feche o arquivo.

**Passo 7**  
Neste ponto, você precisaria fazer logout e login. Contudo, se não quiser fazê-lo, digite no terminal:

`` source .bashrc ``

Note, porém, que deverá fazer isso em cada novo terminal que abrir, até você fazer logout e login.

**Passo 8**  
Agora, para se certificar de que deu tudo certo, digite:

`` node --version ``  

e  

`` npm --version ``  

As versões destas duas aplicações devem ser retornadas a você.

**Passo 9 - Instalação React-Native**  
Instale a ferramenta "create-react-native-app" através de seu terminal:

`` npm install -g create-react-native-app ``

**Passo 10**  
Crie uma pasta para os eu projeto:

`` mkdir projeto ``  

Entre na pasta:

`` cd projeto ``

Crie seu projeto:

`` create-react-native-app NomeDoSeuProjeto ``

**Passo 11**  
Pronto! Seu ambiente para desenvolvimento em React Native está configurado e com um projeto criado. Para rodar seu projeto escreva no terminal:

`` npm start  ``  

Este comando pode demorar um pouco, e após sua execução, aparecerá um QRCode em seu terminal.

**Passo 12**  
Para utilizar o QRCode e testar seu projeto, instale a aplicação <b><i>EXPO</i></b> (Mais detalhes sobre o EXPO no <a href="https://github.com/fga-gpp-mds/2017.2-MerendaMais#20172---merenda---auxílio-aos-conselheiros-do-conselho-de-alimentação-escolar-cae">README</a> do projeto) em seu aparelho mobile (Android ou IOS) e leia o QRCode, após alguns minutos, seu projeto estará rodando na tela do seu celular e você poderá começar a modificar seu software e ver os resultados simultaneamente.


<b>OBS:</b> Na data atual 16/03/2018, o React Native apresentou problemas por conta do **JDK**. Recomenda-se que tenha versão 8 do JDK, onde até o momento funcionou sem problemas durante o uso do React.