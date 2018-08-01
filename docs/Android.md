[Configuração de Ambiente](#configuração-de-ambiente)

[DOJO de linguagem](#dojo-de-linguagem)

[DOJO de testes ](#dojo-de-testes)

[Repositórios educativos](#repositórios-educativos)

[Material didático produzido na disciplina ](#material-didático-produzido-na-disciplina)

-----
# Configuração de Ambiente

<p align = "justify"><b>Android</b> é o sistema operacional de código aberto desenvolvido pela <b>Google</b>, para ser utilizado majoritariamente em despositivos com tela touchscreen, como
smarthphones ou tablets. 

<p align = "justify">A criação de aplicativos para este sistema é feita em <i>Java</i> utilizando-se de um kit de desenvolvimento (SDK)
 específico. Além disso, normalmente se utiliza uma IDE específica, o <b>Android Studio</b>. É de extrema <b>importância</b> que todos os integrantes da equipe tenham a mesma configuração de ambiente para que não haja incompatibilidade entre versões diferentes das ferramentas usadas, que podem comprometer o desenvolvimento do software.

<p align = "justify">Configurar o ambiente do Android Studio requer alguns passos.

Linux (64-bits):

<b>Passo 1:</b> Instale o kit de desenvolvimento java:

<b>1)</b> Via terminal, adicione o repositório PPA com o seguinte comando:

    sudo add-apt-repository ppa:webupd8team/java

<b>2)</b> Atualize os pacotes disponíveis em seus repositórios:

    sudo apt-get update

<b>3)</b> Instale o kit de desenvolvimento:

    sudo apt-get install oracle-java8-installer

<b>4)</b> Defina o SDK da Oracle como o kit padrão a ser utilizado:

    sudo apt-get install oracle-java8-set-default

<b>5) Se o seu sistema for de 64 bits, instale as bibliotecas de 32 bits :</b>

    sudo apt-get install lib32z1 lib32ncurses5 lib32ncurses5-dev lib32stdc++6


<b>Passo 2:</b> Instale o ubuntu-make:

<p align = "justify">O ubuntu make é uma ferramenta de linha de comando a qual permite baixar e atualizar plataformas de desenvolvimento de software com mais facilidade.

<b>1)</b> Adicione o repositório PPA para instalar a última versão do ubuntu-make com o seguinte comando:

    sudo add-apt-repository ppa:ubuntu-desktop/ubuntu-make

<b>2)</b> Atualize os pacotes disponíveis em seus repositórios:

    sudo apt-get update

<b>3)</b> Instale o ubuntu-make

    sudo apt-get install ubuntu-make

<b>Passo 3:</b> Instalar o Android Studio

<b>1)</b> Com o ubuntu-make instalado, basta utilizar o seguinte comando:

    umake android

<b>2)</b> Após o termino do download, basta executar o programa Android Studio presente na máquina. Este irá realizar o download do kit de desenvolvimento
Android. Quando finalizado, o Android Studio estará pronto para ser utilizado.

## Observação Importante!

<p align = "justify">Ficar sempre atento às configurações do gradle tanto no seu app, quanto na sua IDE. Elas podem afetar significativamente os resultados de teste e deploy. Tente definir uma config padrão para todo o grupo o mais cedo possível.

# Arquitetura MVC Android 

# DOJO de linguagem 

<b>1)</b> Curso completo da plataforma [Udacity](https://www.udacity.com) sobre <i>Android</i>:

* <b>Tais cursos apresentados nesta plataforma são bastante completos e de alta qualidade, contudo bastante extensos. Logo, demanda-se uma quantia considerável de tempo para completá-los com eficácia e obter o resultado esperado.</b>

        https://www.udacity.com/courses/android

<b>2)</b> Sugestões de aprendizado direcionado na plataforma [Udacity](https://www.udacity.com):

* <b>Indicado para um desenvolvimento aceitável em <i>Android</i>:</b>
 
  Desenvolvimento intermediário de <i>Android</i> (<i>Gradle, Layout, Intent,</i> Banco de Dados, Testes e outros):

      https://br.udacity.com/course/developing-android-apps--ud853/

  Material <i>Design</i> para <i>Android</i>:
    
      https://br.udacity.com/course/material-design-for-android-developers--ud862/

* <b>Indicado como um complemento, mas fortemente recomendado para um desenvolvimento aceitável em <i>Android</i>:</b>
 
  Desenvolvimento inicial de <i>Android</i> (<i>XML</i> e básico do <i>Framework</i>):

      https://br.udacity.com/course/android-development-for-beginners--ud837/

  <i>Login</i> do <i>Google</i> para <i>Android</i>:
    
      https://br.udacity.com/course/add-google-sign-in-to-your-android-apps--ud876-5/

* <b>Indicado para quem deseja aprofundar-se em <i>Android</i>:</b>
 
  Desenvolvimento avançado de <i>Android</i> (<i>Libraries, localization,</i> Material <i>Design</i>):

      https://www.udacity.com/course/advanced-android-app-development--ud855

  Outros tópicos (Sistemas de controle, menu, <i>layout</i>, entrada e saída):
    
      https://br.udacity.com/course/how-to-create-anything-in-android--ud802/

# DOJO de testes 

<p align = "justify">Neste link, encontra-se um tutorial para entendimento e realização de teste unitários e instrumentais no Android, assim como as configurações de ambiente para que estes ocorram:

      http://www.vogella.com/tutorials/AndroidTesting/article.html

<p align = "justify">O link abaixo pertence à uma serie de treinamentos fornecidos pelo próprio site do Android para desenvolvedores. Este foca na elucidação dos testes:

      https://developer.android.com/training/testing/index.html

* Testes Unitários 

><b>Utilizando JUnit</b>

      https://developer.android.com/training/testing/unit-testing/local-unit-tests.html 

      http://alexzh.com/tutorials/android-testing-unit-testing/

><b>Utilizando Mockito e Robolectric</b>

      http://alexzh.com/tutorials/android-testing-mockito-robolectric/

* Testes Instrumentais utilizando Espresso

      http://alexzh.com/tutorials/android-testing-espresso-part-3/

      http://alexzh.com/tutorials/android-testing-ui-automator-part-4/

      http://alexzh.com/tutorials/android-testing-espresso-uiautomator-together/

      https://jabknowsnothing.wordpress.com/2015/11/05/activitytestrule-espressos-test-lifecycle/ 

# Repositórios educativos


# Material didático produzido na disciplina 
(times, coaches, etc)