# Teste de Aceitação  


O teste de aceitação é aplicado no desenvolvimento de _software_, sendo uma abordagem que  enxerga o sistema como uma caixa preta, e o principal objetivo do mesmo é a verificação das funcionalidades em relação aos requisitos e funcionalidades originais do projeto, verificando assim se elas atendem as necessidade mais importantes dos usuários.
    Para o teste de aceitação existem três estratégias comuns para a implementação de um teste, no qual são elas:

  * Teste de Aceitação Formal: esse teste é um processo altamente gerenciado, no qual costuma a ser uma extensão de teste do sistema. Esses testes são planejados e projetados com um cuidado e um nível de detalhamento do sistema.  Os casos de teste devem ser um subconjunto dos realizados no teste do sistema. O teste de informação formal é totalmente automatizado.
    
Os benefícios dessa forma de teste são:

    - O progresso dos testes podem serem monitorados e medidos;

    - Critério de aceitabilidade é conhecido;

    - Os testes podem ser automatizados.

As desvantagens são:

    - Teste não revela os defeitos subjetivos no software;

    - Testes podem se tornar uma nova implementação dos testes do sistema.

  
* Teste de Aceitação Informal: o procedimento para a execução do teste não são definidos com um rigor como é feito no formal. As funções e as tarefas de negócios são identificadas e documentadas, porém não há caso de testes específicos para serem seguidos. Esse teste não é tão controlado como o formal, contudo é mais subjetivo.

Benefícios do teste informal:
 
    - São revelados defeitos subjetivos;

    - A função e recurso que serão testados são conhecidos.


Desvantagens:

    - Não há controle dos casos de teste que são usados;

    - Os teste de aceitação podem ser limitados.

 * Teste Beta:  é o que menos pode ser controlado, no qual a quantidade de detalhes, os dados de abordagem são de responsabilidade do testados individual, assim cada um tem que identificar os próprios critérios que levarão se ele será aceito ou negado no seu sistema atual. Esse teste é implementado pelos usuários finais.

Benefícios do teste beta:

    - Teste implementado por usuários finais;

    - Possibilidade de recursos de teste;

    - Aumenta a satisfação do cliente.

As desvantagens:
   
    - Nem todas as funções e recursos podem ser testados;

    - Dificuldade de medir o progresso do teste.

## Execução

Para iniciar os testes, deve-se criar o arquivo contendo os testes a serem realizados. O nome do arquivo deve ser NomeDaFuncionalidadeTestada.feature. Deve necessariamente terminar em “.feature”. Esse arquivo conterá os cenários de teste escritos, estruturando-se em:

__Feature__: (nome do arquivo. Exemplo do projeto: registration_member)

__Background__ (opcional): É uma forma de setup. De forma geral, o que estiver contido no background rodará antes de executar cada um dos outros testes, de forma a criar condições específicas.

__Scenario__: É o teste em si. Consiste de vários steps (passos) que indicam a ocorrência de algo no sistema. Se os passos são seguidos corretamente, o teste passa e a funcionalidade está de acordo com o escrito.

Como exemplo de um arquivo “.feature”, pode-se mostrar parte de um teste de aceitação do projeto Owla, chamado “registration_member.feature”:

          Feature: registration_member

 	  Scenario: a user should be able to registrate
    		Given I go to /
    		When I click "Register yourself"
    		Then I should be in "/members/new"
    		When I write "Gabriel Alves" on "member_name"
    		When I write "gabriel@gmail.com" on "member_email"
    		When I write "gabi" on "member_alias"
    		When I write "testtest" on "member_password"
    		When I write "testtest" on "member[password_confirmation]"
    		When I click button "Register"
    		Then I should be in "Gabriel Alves" homepage
    		And the object with attribute "name" and value "Gabriel Alves" of "member" klass was created

Nesse teste, não há a presença de um background. Porém, um _background_ seria a mesma coisa de um cenário, sem a presença da descrição presente na linha do _scenario_. Porém, apenas isso não é suficiente para que o teste rode sem problemas. Cada um dos _steps_ deve ser definido em outro arquivo, para que o sistema saiba que ações devem ser chamadas para cada passo. Deve-se criar um arquivo de definição de passos. No caso do projeto Owla, esse arquivo se chama web_steps.rb e está contido na pasta _step_definitions_. Seu conteúdo é o que se segue:

          Given(/^I go to (.+)$/) do |path|
           visit path
          end

          When(/^I click "(.+)"$/) do |link|
           click_link(link)
          end

          When(/^I click button "(.+)"$/) do |link|
            click_button(link)
          end

          Then(/^I should be in "(.+)"$/) do |page|
            assert current_path == page
          end

          Then(/^I should be in "(.+)" homepage$/) do |object|
            member = Member.find_by(name: object)
            assert current_path == "/members/#{member.id}/home"
          end

          Then(/^I should be in "(.+)" edit$/) do |object|
            member = Member.find_by(name: object)
            assert current_path == "/members/#{member.id}/home"
          end

          When(/^I write "(.+)" on "(.+)"$/) do |value, field|
            fill_in field, :with => value
          end

          Given(/^I have created "(.+)"$/) do |value|
            member = Member.create(name: "Victor Navarro", email: value, alias: "vivi",
            password: 'testtest', password_confirmation: 'testtest')
          end

          And(/^the object with attribute "(.+)" and value "(.+)" of "(.+)" klass was created$/) do |attribute, value, klass|
            object = klass.capitalize.constantize.find_by("#{attribute}": value)
            assert klass.capitalize.constantize.last.id == object.id
          end

Percebe-se que, nesse arquivo, contém “frases” com REGEX especiais que funcionam da seguinte forma: para cada step contido no arquivo de testes, o sistema procurará no arquivo de definição de steps um com a mesma “frase” de comando. Lá, ele encontrará a frase e o que dentro da frase é uma variável, que deve ser pega do arquivo de testes. Então, dentro do bloco de código presente na definição do step, ele implementará o que for especificado.
	É importante notar que há muitas funções referentes a clicar em botões, acessar links e páginas diferentes para auxiliar o desenvolvedor na hora de criar os testes. Apenas a pesquisa pode mostrar todas as funções, mas há sites que tentam fazer um resumo delas, como:
                        
                   https://gist.github.com/zhengjia/428105
