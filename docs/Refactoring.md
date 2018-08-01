
<a href="https://labs.spotify.com/2014/04/11/qualities-of-quality/"> Qualities of Quality</a>

Dívidas técnicas:
https://www.youtube.com/watch?v=pqeJFYwnkjE

***

# Refatoração

<p align="justify"> A refatoração é um processo de reorganização da estrutura interna do software, sem alterar o seu comportamento externo. É um modo disciplinado de reorganizar código, facilitando a posterior depuração, eliminando código presumível de introduzir erros. De modo geral, quando se refabrica o código, melhora-se o desenho e a estruturação deste.</p>

# O que não é Refatoração

- Encontrar e arrumar bugs enquanto faz o código, de maneira que essa ação é considerada apenas como melhoria de código.
- Intensificar o tratamento de erros, que também é considerado apenas como melhoria da cobertura de código.
- Código defensivo, de maneira que erros aplicação sejam raros.
- Tornar o código mais testável.

Em resumo, melhoria de cobertura e tratamento de erros não é considerado como refatoração de código.

# Quando a refatoração é necessária?
## Para se encontrar um bug no código
<p align="justify"> Bugs são como baratas: se escondendo nos lugares mais escuros e sujos do código. Desta forma, a limpeza do código vai tornar evidente os possíveis bugs.</p>

## Ao se adicionar uma nova funcionalidade 
<p align="justify"> Ao se adicionar uma nova funcionalidade é necessário refatorar o código para um melhor entendimento do código e para que os bugs fiquem mais visíveis, pois um código desnecessariamente complexo dificulta a visualização de problemas.</p>

## Durante a visão de código
<p align="justify"> A revisão de código é sempre um bom momento para a refatoração, pois pode ser o último momento antes do código/software estar disponível para o público.</p>

<p align="justify"> A melhor forma de revisar o código é em conjunto com o autor do código, pois pode-se decidir formas e técnicas de refatoração sem prejudicar as funcionalidades. As mudanças podem ser feita diretas ao ponto.</p>

## Qualquer hora
De tempos em tempos o código precisa ser revisado para refatoração, de forma que fique mais limpo.

# Para quê utilizar a refatoração?

- Eliminação de código duplicado, fazendo com que a repetição de código seja nivelada ao mínimo possível.
- Elimanação de código morto, excluindo linhas de código que não acrescentam nada à aplicação.
- Melhorar a lógica utilizada no sistema, de maneira que o design seja mais claro para programadores de fora.
- Melhorar o uso da linguagem, otimizando o desempenho.

# Bad Smells in code (mal cheiro de código)

Bad smell é uma situação na qual a estrutura do programa pode ser melhorada com refatoração, como por exemplo: Duplicação de código e classe ou métodos longos.

# Identificando mal cheiro de código - métricas de código fonte

<p align="justify"> Existem vários indicativos de bad smells, abaixo deixo algumas definições desses bad smells bem como a refatoração sugerida:</p>

* **Long Method/ God Method:** 
<p align="justify"> São métodos que centralizam a funcionalidade da classe e que, geralmente, são difíceis de entender e de manter.
Para melhorar esses métodos pode-se dividir o método em dois ou transformar o método em uma classe.</p>

* **Feature Envy:** 
<p align="justify"> Acontece quando uma parte do código de uma classe "inveja" outra classe, por exemplo quando um método de uma classe usa atributos somente de outra classe.
Para refatorar pode-se mover os métodos e atributos entre classes ou juntar duas classes em uma.</p>

* **Divergent Change:**
<p align="justify"> Ocorre quando uma classe pode mudar frequentemente de diferentes formas e por razões distintas.
Como refatoração pode-se dividir a classe em duas.</p>

* **Shotgun Surgery:** 
<p align="justify"> Oposto do Divergent Change acima, pois toda vez que uma classe for alterada, são necessárias várias pequenas mudanças em outras classes diferentes.
Como refatoração pode se mover métodos e atributos entre as classes e juntar duas classes em uma.</p>

* **Refused Bequest:** 
<p align="justify"> Ocorre quando uma classe herda atributos e métodos de outra classe, mas não os usa.
Como refatoração propõe-se mover o método ou atributo da superclasse para a subclasse e substituir o relacionamento de herança por associação.</p>

* **Comments:** 
<p align="justify"> Os comentários não são ruins, porém quando em excesso podem indicar que os nomes de métodos/atributos não estão suficientemente expressivos.
Pode-se quebrar um método em dois ou renomear.</p>

# Exemplo de Refatoração

A refatoração deve resultar em um código mais limpo, que seja legível, claro e com o mínimo de repetições. Na imagem abaixo podemos fazer uma analogia a refatoração:

![](https://raw.githubusercontent.com/wiki/fga-gpp-mds/00-Disciplina/img/refatoracao-casa.png)

<p align="justify"> Esta imagem retrata uma cozinha em duas situações distintas. Na esquerda, vemos uma cozinha em situação caótica, onde preparar alimentos, lavar e encontrar utensílios, que são o objetivo principal da cozinha, se tornaram tarefas difíceis. Já na direita, vemos uma cozinha limpa e organizada, onde pode-se realizar as mesmas tarefas da anterior, porém com muito mais facilidade.</p>

<p align="justify"> A refatoração deve funcionar desta mesma forma: fazer com que um código inadequado se torne limpo, facilitando seu entendimento, e tornando a detecção de bugs mais simples. A refatoração não pode alterar o comportamento do código.</p>

## Ferramentas das métricas

# Relação entre Testes e Refatoração

## Refatoração e Testes
<p align="justify"> Os testes estão intrinsecamente relacionados à refatoração. Como a refatoração não pode alterar o funcionamento do código, os testes são a perfeita ferramenta para garantir o funcionamento correto do código <b>antes e depois</b> da refatoração.</p>

## Refatoração e TDD
<p align="justify"> O TDD também está relacionado à refatoração, pois a refatoração dos testes é parte básica do ciclo de desenvolvimento direcionado à testes. Pode-se entender essa relação através da figura abaixo:</p>

![](https://github.com/fga-gpp-mds/00-Disciplina/wiki/img/tdd.png)

# Tipos de Refatoração

# Treinamento

- Incluir descrição do treinamento/DOJO - passo a passo - etapas
- Registrar os detalhes da dinâmica
- Infraestrutura Necessária para a dinâmica
- Código referência no projeto da disciplina (00-Disciplina)
- Treinamento em, pelo menos 2 linguagens

# Referências

<a href="http://paginas.fe.up.pt/~ei02017/docs/relatorio_es.pdf"> Engenharia de software. Refactoring.</a>

Ian Sommerville. Engenharia de Software, 9ª Edição. Pearson Education, 2011.