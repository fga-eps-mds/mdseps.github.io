# Documentação complementar:

Além das informações aqui mostradas, é interessante consultar, sempre que necessário, as documentações oficiais de cada uma das ferramentas:

[chef](https://docs.chef.io/)

[rake](http://docs.seattlerb.org/rake/)

[chake](https://gitlab.com/terceiro/chake)

# Instalações:

### Vagrant

Para instalar o vagrant, é possível utilizar o gerenciador de pacotes de sua distribuição linux, mas é preferível baixar o pacote diretamente do site para manter a versão mais atualizada (no archlinux o yaourt ja instala a mais nova).

No [site](https://www.vagrantup.com/downloads.html) é possível baixar os pacotes .rpm e .deb.

### Virtualbox

Pelo mesmo motivo é preferível instalar o pacote do [site](https://www.virtualbox.org/wiki/Downloads)

### RVM

RVM é uma ferramenta para gerenciar, instalar e facilitar utilização de ambientes ruby. É opicional, mas pode evitar algumas dores de cabeça (ou criar algumas outras).

Siga os passos do [site ](https://rvm.io/rvm/install) ou da [wiki do archlinux](https://wiki.archlinux.org/index.php/RVM) que serve para outras distros

### Ruby no rvm

Para instalar uma versao especifica do ruby, por exemplo a 2.1.8, basta executar

    rvm install 2.1.8

### Chake, Rake, Chef

Para instalar ruby gems em um ambiente específico de um diretório, é necessário ir pro diretório onde o [repositório foi clonado](https://wiki.archlinux.org/index.php/RVM). Exemplo:

    cd $HOME/workspace/saap/ # só um exemplo

Então é interesante criar um gemset somente para esse diretório:

    rvm gemset create saap

e para usar uma versao especifica do ruby com um gemset criado:

    rvm use 2.1.8@saap

no formato <versão>@<nome do gemset>

Com uma versão e um gemset em uso, podemos instalar as gems:

    gem install rake
    gem install chef # não é necessário no home, mas pode ser útil
    gem install chake

### Rsync

Instale a ultima versão pelo seu gerenciador de pacotes:

Exemplo:

    sudo apt-get install rsync # ubuntu e debian likes

ou
    sudo pacman -S rsync # archlinux

**
# Utilizando
## Vagrant : 

Faz o boot na máquina virtual

    vagrant up

Faz login na máquina virtual, não precisa de login ou senha

    vagrant ssh

Para reiniciar a máquina virtual:

    vagrant reload

Para destruir a VM:

    vagrant destroy

e confirme.

para levantar tudo de novo basta usar o vagrant up, mas não se esqueça de remover a pasta tmp/

    rm -rf tmp .vagrant

###Chake
Com a VM levantada é possivel usar o chake para fazer diversas configurações e utilidades como passar comandos para a vm:

    rake run:$NODE[command]

um exemplo:

    rake run:digitalocean[date]

ou simplesmente
    
    rake run

e ele espera por um comando para rodar em todos os guests. O ambiente local está como default.

Um exemplo de como seria rodar isso em um ambiente especifico seria:

    rake run SAAP_ENV=local

ou

    rake run SAAP_ENV=dev

Para rodar as receitas de configuração e instalações nos nós basta:

    rake converge:digitalocean

um exemplo de como seria rodar em produção:

    rake converge:digitalocean SAAP_ENV=prod

o chake salva coisas nessa pasta, e só é possível rodar outro converge do 0 com ela vazia, se a VM tiver sido destruída.