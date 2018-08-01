# Tutorial de Instalação do Ionic  

O tutorial leva em consideração o sistema operacional Ubuntu, na versão 16.04. Outras versões do Ubuntu devem funcionar bem. Se você está usando Debian, o passo a passo não deverá ser muito diferente.  
Acessar o site do [Node.js](https://nodejs.org/en/), e fazer o download da ferramenta. A versão v4.5.0 LTS servirá bem.  

Descompactar o tar em uma pasta de sua preferência. Eu recomendo a sua home (/home/nome_de_usuario), e o tutorial assume que a pasta estará lá.  

Abra o terminal de seu sistema, e se certifique de que ele está na sua home (digite cd e aperte enter), e então abra o arquivo .bashrc com seu editor de textos favorito. Neste caso, usou-se o gedit:  

>    gedit .bashrc  

(Note que há de fato um ponto antes do nome do arquivo).

No arquivo que se abrirá, adicione na útima linha:  

>    PATH="/home/seu_usuario/node-v4.5.0-linux-x64/bin/:$PATH"  

Nota: o nome da pasta do Node pode ser diferente, dependendo de seu Sistema Operacional.

Salve e feche o arquivo.

Neste ponto, você precisaria fazer logout e login. Contudo, se não quiser fazê-lo, digite no terminal:  

>    source .bashrc  

Nota: este comando também deve ser realizado na sua home. Digite cd e aperte enter no terminal para se certificar de que está lá.

Note, porém, que será necessário fazer isso em cada novo terminal que abrir, até o logout ser realizado. Agora, para se certificar de que deu tudo certo, digite:  

>  node -v  

e  

>  npm -v  

As versões destas duas aplicações devem ser retornadas a você.

Em seguida, instale o cordova:

>  npm install -g cordova

Deve demorar alguns minutos. Talvez ele retorne um ou dois warnings.

Para se certificar de que deu tudo certo, digite:

>    cordova -v

Talvez ele faça uma pergunta sobre envio de estatísticas anônimas. Fica ao seu critério se você quer tornar o mundo um lugar melhor ou não.

Após instalado o cordova, digite:

>    npm install -g ionic

Nota: Caso se deseje utilizar a versão 1 do Ionic, que não utiliza o Angular 2, digite:

>    npm install -g ionic@1.7.14

Ele deve instalar sem problemas também. Para se certificar, digite:

>    ionic -v

Instalado o ionic, agora você pode criar o primeiro app:

>    ionic start nome_do_seu_projeto tabs

"tabs" utiliza um template de demonstração do framework.

Vá para o diretório do projeto criado:

>    cd nome_do_seu_projeto

E digite então:

>  ionic serve --lab

Ele talvez retorne múltiplos endereços de servidor que você pode escolher. Digite 1, por exemplo, para escolher um. 

Em seguida, basta abrir este endereço no navegador (na verdade, ele deve abrir sozinho).


