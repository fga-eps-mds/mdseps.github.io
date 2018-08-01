# Automatizando o ambiente com Vagrant

o _Vagrant_ é uma ferramenta para automatizar a criação, configuração e principalmente gerenciamento de ambientes de desenvolvimento através de máquinas virtuais (VM) via softwares de virtualização como VirtualBox, VMWare, Parallels, entre outros. A ideia principal é você poder montar e configurar uma máquina virtual de maneira totalmente automatizada através de um conjunto de instruções escritas usando a **DSL** (_Domain-Specific Language_) da própria ferramenta. Sempre que você rodar essas instruções o resultado deverá ser o mesmo.

O _Vagrant_ irá isolar dependências e configurações em um único ambiente virtual, consistente e descartável, sem precisar sacrificar nenhuma das ferramentas que estamos acostumados a trabalhar. Para isso, só precisamos criar um único arquivo dentro do projeto, o _Vagrantfile_, e logo em seguida dar um simples comando para que todo o ambiente seja montado, instalado e configurado.

Outra grande vantagem é a possibilidade de replicar o mesmo ambiente de maneira fácil e rápida em diferentes máquinas. Por as configurações do _Vagrant_ serem apenas arquivos texto, elas podem estar embutidas dentro do seu projeto e controle de versão, como no caso o _git_, onde qualquer membro da equipe poderá baixar e criar o próprio ambiente de desenvolvimento a partir do _Vagrantfile_ criado dentro do seu repositório.

## Criação do ambiente

Considerando que o seu sistema operacional é um Linux Ubuntu, o primeiro passo, é instalar o programa _VirtualBox_, que é um software de virtualização, utilizando-o para criar dinamicamente máquinas virtuais configuráveis, leves e portáteis. Para isso, execute o seguinte comando no terminal:

`sudo apt-get install virtualbox`

Após o VirtualBox ter sido instalado corretamente, falta instalar o _Vagrant_. No terminal, execute:

`sudo apt-get install vagrant`

E pronto, agora temos a vagrant instalada com sucesso, próximo passo é a configuração do ambiente.

## Configuração da Vagrant

Primeiramente escolha e acesse, via terminal, um diretório ou projeto qualquer existente da sua máquina.

Agora, iremos criar o arquivo que conterá toda a configuração inicial do nosso ambiente virtual. Esse arquivo é o _Vagrantfile_, mencionado anteriormente. Ele será criado automaticamente quando executarmos o seguinte comando:

_vagrant init ubuntu/trusty64_

Note que este comando cria uma máquina virtual com um sistema operacional Ubuntu server 14.04 LTS, no qual é considerado o suficiente para este tutorial. 

Para rodar esta _VM_ basta executar o comando abaixo:

`vagrant up`

É importante ter paciência ao rodar este comando pela primeira vez, pois o _Vagrant_ terá que baixar a _VM_ da internet de um repositório global com _VMs_ pré-configuradas.

Se o comando foi executado com sucesso, já podemos utilizar nossa máquina virtual. Para isso, podemos conectar na VM via SSH através do comando a seguir:

`vagrant ssh`

### Provisionamento

Está é uma etapa importante para inicializar o _Vagrant_ com todas as dependências necessárias para trabalhar no projeto, sendo que a _Vagrant_ recém criada é um vem enxuta e normalmente não satisfaz os requisitos do nosso ambiente de desenvolvimento.

O ideal é que o _Vagrant_ fizesse isso automaticamente sempre criássemos a VM no primeiro comando `vagrant up`. Para isso, eu teria que de alguma forma indicar ao _Vagrant_ para executar alguns comandos dentro da VM assim que ela fosse inicializada. Esses comandos poderiam estar em um _script shell_.

Para isso é necessário criar um arquivo, como por exemplo `init.sh`, contendo as instruções de instalação das dependências para o ambiente de desenvolvimento.

Neste arquivo devem conter instruções do tipo:

```
sudo apt-get -y update
sudo apt-get -y install openjdk-7-jdk
sudo apt-get -y install tomcat7
sudo service tomcat7 start
```

Pronto! Agora só resta indicar ao `Vagrant` para rodar o script `init.sh` acima que fica localizado na raiz do nosso projeto. Para isso, precisamos configurar o arquivo `Vagrantfile` como a seguir:

```ruby
Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.provision :shell, path: "init.sh"
end
```

Basicamente adicionamos a linha `config.vm.provision` informando o tipo do arquivo a ser provisionado :_shell_ e sua localização relativa dentro do projeto. Para finalizar, só precisamos executar o comando `vagrant up` e nossa VM será criada e configurada a partir do nosso _script shell_.

A principal vantagem de usar o provisionamento do _Vagrant_ é que podemos automatizar todo o processo de configuração da _VM_ o que nos permite ter ambientes replicáveis. 

Agora está finalizada a instalação e configuração do ambiente virtual utilizando a `Vagrant`.





