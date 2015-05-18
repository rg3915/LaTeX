Dica: Tamanho de fonte em expressões matemáticas
================================================

Dica: Tamanho de fonte em expressões matemáticas
------------------------------------------------

Neste tópico veremos como alterar o _tamanho de fonte em expressões matemáticas e como manter expressões matemáticas sempre com mesmo tamanho_.

#####Tamanho de fonte em expressões matemáticas
O tamanho da fonte em expressões matemáticas é sempre padrão, mas caso a expressão matemática fique muito grande, excedendo a largura da página, é possível reduzir seu tamanho com o comando \scriptstyle ou \scriptscriptstyle. Este comando deve ser digitado no início da expressão.

```
$p(x) = a_0 + a_1 x + a_2 x^2 + \ldots + a_n x^n$

$\scriptstyle p(x) = a_0 + a_1 x + a_2 x^2 + \ldots + a_n x^n$

$\scriptscriptstyle p(x) = a_0 + a_1 x + a_2 x^2 + \ldots + a_n x^n$
```

![image](http://1.bp.blogspot.com/-pqDw1sWZKiM/UASKxps2RLI/AAAAAAAAAc0/mn4ihCULVuU/s400/mat04.png)

#####Expressões matemáticas sempre com mesmo tamanho
As expressões matemáticas escritas na linha de texto geralmente tem sua altura ajustada para caber no espaço vertical da linha. Esta diferença pode ser facilmente observada numa fração, onde os caracteres ficam encolhidos para caber na linha.

O LaTeX oferece três comandos que dão suporte ao tamanho de frações: \frac{}{}, \tfrac{}{} e \dfrac{}{}. Veja a diferença de tamanho em cada caso na figura a seguir.

__Obs__: \tfrac{}{} e \dfrac{}{} requer o pacote amsmath.

![image](http://1.bp.blogspot.com/-1hzdNx5u9ps/UASLIdZgb6I/AAAAAAAAAdM/15TbtZQHkM8/s400/mat01.png)

Mas existe uma opção que mantêm as frações num tamanho ideal usando apenas o comando \frac{}{}. Digite \everymath{\displaystyle} no preâmbulo e pronto. Todas as frações terão um tamanho ideal.

![image](http://3.bp.blogspot.com/-MOEYV6lLBRI/UASK_46k33I/AAAAAAAAAdE/amr840ZzXLg/s400/mat02.png)

