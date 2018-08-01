# Integração Contínua
“Integração Contínua é uma pratica de desenvolvimento de software onde os membros de um time integram seu trabalho frequentemente, geralmente cada pessoa integra pelo menos diariamente – podendo haver multiplas integrações por dia. Cada integração é verificada por um build automatizado (incluindo testes) para detectar erros de integração o mais rápido possível. Muitos times acham que essa abordagem leva a uma significante redução nos problemas de integração e permite que um time desenvolva software coeso mais rapidamente.” [Martin Fowler](http://martinfowler.com/articles/continuousIntegration.html)

## Travis-CI
1. O primeiro passo é acessar o site do [travis-ci](https://travis-ci.org) e fazer login com o seu usuário do [github](https://github.com).
[Imagem - Travis-CI](http://imgur.com/MwU2GtU)

2. Feito isso você vai acessar a página do seu [perfil](https://travis-ci.org/profile/), lá você irá visualizar uma lista de todos os seus projetos. Basta mudar a chave para a posiçao ON e clicar na engrenagem ao lado, isto te levará para a página de configurações. [Imagem - Perfil](http://imgur.com/vk0ACjR)

3. Na página de configurações nós temos as seguintes opções:

  * Build only if .travis.yml is present: Este vem como off por padrão, pois ainda não criamos o arquivo .travis.yml
  * Build pushes: Toda vez que for feito um push, ele vai gerar um novo build
  * Build pull requests: Toda vez que for feito um pull request, ele vai gerar um novo build
  * Limit concurrent jobs

  Mude a primeira chave "Build only if .travis.yml is present", para criar o .travis.yml e dar um commit para o repositório. [Imagem - Chave.](http://imgur.com/UnU4HKY)
Escolha a linguagem que deseja utilizar [aqui](https://docs.travis-ci.com/user/getting-started/). Aqui neste exemplo eu irei utilizar o Ruby, e o arquivo ficará assim:
  ```yml
  1 language: ruby
  2 rvm:
  3 - 2.2.0
 ```
  Também é possível validar o seu .travis.yml [neste link](http://lint.travis-ci.org).

4. Feito isso, o arquivo deve ter sido criado/validado e devidamente "commitado" para o seu repositório.
5. O resultado final deverá ser semelhante a este: [Imagem - Resultado.](http://imgur.com/LI2hfJM)

Este foi um exemplo bem simples de como utilizar a integração contínua com o travis-ci, o arquivo .travis.yml pode ser personalizado de acordo com as necessidades do seu projeto.