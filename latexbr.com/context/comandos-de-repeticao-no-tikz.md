Comandos de repetição no TikZ (foreach)
=======================================

No TikZ é possível trabalhar com comandos de repetição (ou laço) com o comando `foreach`.

Para usar o `foreach` precisamos de uma sequência finita, que pode ser interpretada como uma progressão aritmética (P.A.) ou não.

Por exemplo, a sequência `(0,2,...,10)` é uma sequência dos números pares de 0 à 10.

A sequência `(1,3,...,11)` é uma sequência dos números ímpares.

E `(12,9,...,0)` é uma sequência decrescente dos múltiplos de 3.

O `foreach` interpreta todas essas sequências como uma P.A., sendo necessário o primeiro, o segundo e o último termo da sequência junto com as reticências.

A sequência `(-5,-2,-1,1,2,7)` não é uma P.A., mas é interpretada pelo `foreach` como uma sequência finita.

O `foreach` pode ser aplicado em todo e qualquer parâmetro numérico do TikZ, desde coordenadas até escala, rotação, cor, etc.

## Sintaxe do foreach

A sintaxe geral do foreach é:

	\foreach <variavel> in {<sequencia>}{<comandos>}

Onde `<variavel>` é o nome da variável, iniciado com `\`, `<sequencia>` é a sequência numérica onde os números são separados por vírgula e decimal por ponto, exemplo 3.14.

E `<comandos>` é onde iremos desenhar usando as variáveis.

Também podemos escrever

	\foreach <variavel> in {<sequencia>} {
		<comandos>
	}

assim poderemos estruturar melhor nosso código.

**Dica**: Use o [KTikZ] para fazer os exemplos.

**Exemplo**: Sequência dos números pares.

	\begin{tikzpicture}
		\foreach \x in {0,2,...,10} {
			\node at (\x,0) {\x};
		}
	\end{tikzpicture}

**Atenção**: nome da variável não pode conter caracteres numéricos.

O foreach também aceita mais de uma variável, por exemplo, uma tabela com a idade de um grupo de pessoas. Mas neste caso a sequência deve ser completa, ou seja, sem reticências.

A sintaxe é:

	\foreach <var1>/<var2>/<var3> in {<sequencia>} {
		<comandos>
	}

onde `<var1>`, `<var2>`, `<var3>`, são as variáveis. Note que cada variável é separada por `/`.

**Exemplo**: idade de um grupo de pessoas.

fig02

	\foreach \n / \nome / \idade in { } {
		% linear
	}

Vejamos agora várias aplicações do `foreach` em ilustrações diversas.

% pg 35 e 504

% retangular e polar (radial)

As aplicações mais comuns do `foreach` são baseados em três repetições fundamentais: **linear, retangular (matriz) e polar (radial).**

* Linear - neste exemplo as figuras ficam alinhadas.

	\foreach \i in {0,1,...,5} {
		\draw (\i,0) circle ();
	}

fig03

O alinhamento pode ser horizontal, vertical ou inclinado, nesse caso, variamos as entradas das coordenadas: `(0,\i)` para vertical e `(\i,\i)` para inclinada.

fig04 e fig05

* Retangular - como o nome já diz, basicamente a figura se assemelha a um retângulo, ou podemos interpretar também como uma matriz. Neste caso precisamos usar dois `foreach`, um dentro do outro, também conhecido como "foreach aninhado".

	\foreach \x in {...}
		\foreach \y in {...} {
			\draw (\x,\y) circle ();
		}

fig

* Polar ou radial nos remete a coordenadas polares onde existe um *raio* e um *ângulo*. O objetivo aqui é [rotacionar] um objeto sobre um ponto fixo.

	\foreach \a in {0,45,...,315} {
		\fill circle (2pt);
		\draw (0,0) -- (1;\a);
		\draw (1;\a) circle ();
	}

fig

Note que a sintaxe `(r;a)` é quem determina uma [coordenada polar], onde `r` é o raio e `a` é o ângulo em graus. Na figura anterior `r=1` e `a=\a` variando sobre os ângulos declarados pelo `foreach`.

% fazer os exemplos + grafico seno

