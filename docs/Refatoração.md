## O que é?

Refatoração é uma alteração feita na estrutura interna do _software_ para torná-lo mais fácil de entender e mais barato para modificar sem alterar seu comportamento observável. Pode ser vista como uma forma disciplinada de limpar código e que minimiza as chances de introduzir _bugs_.

## O que não é?

Há uma certa confusão em relação à vários conceitos que são percebidos como refatoração, mas que não o são. Dentre eles, estão:

* Encontrar e arrumar bugs no meio do caminho
* Otimização do código
* Intensificar o tratamento de erros
* Adicionar código defensivo
* Tornar o código mais testável

## Pra quê?

* Encontrar atalhos
* Eliminar código duplicado
* Eliminar código morto
* Deixar lógica e design claros
* Fazer o melhor uso da linguagem

## Como se faz refatoração?

A refatoração pode ser feita através do uso de cinco orientações básicas:

* Conjunto de pequenas mudanças: a refatoração deve ser sutil e constante. Caso contrário, é uma grande manutenção de código
* Uma mudança de cada vez
* Mudanças não devem adicionar funcionalidades: a refatoração preserva o comportamento original. Se muda, não é refatoração
* Mudanças não devem quebrar os testes já feitos: mesma razão acima.
* Código limpo: será o resultado da utilização de refatoração orientada por essas práticas.

## Quando a refatoração é necessária?

Há alguns indícios observáveis de que há a necessidade de uma refatoração. Esses indícios podem ser conhecidos como "regra de três":

1. Quando você faz algo pela primeira vez e só está fazendo para ter a funcionalidade pronta.
2. Quando você faz algo parecido pela segunda vez e se sente mal por ter de repetir mas faz a mesma coisa assim mesmo.
3. Quando você faz algo pela terceira vez, você começa a refatorar.

Há outras ocasiões importantes de mencionar, como:
* Na hora de consertar bugs: Os bugs vivem nas partes mais sujas do seu código. Limpe frequentemente o código e os erros se acharão.
* Na hora de adicionar features: A refatoração permite que outras pessoas entendam melhor o código de outros programadores. Além disso, torna mais fácil a adição de código.
* Na revisão do código: Antes de tornar seu código disponível para o público pode ser uma boa chance de refatorá-lo.



