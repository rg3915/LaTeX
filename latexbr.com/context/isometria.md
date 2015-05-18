# Isometria

Neste tópico veremos construções sob o ponto de vista das
*transformações geométricas*. O objetivo é reproduzir essas
construções com o [TikZ][0], mas antes precisamos de algumas definições
matemáticas.

texto $\frac{x}{2}$ texto 

* **Transformações geométricas** são funções que associam a cada ponto do
plano um outro ponto também do plano através de certas regras.

* Uma **transformação** $T$ no plano $\Pi$ é uma função
$T:\Pi \to \Pi$ que associa a cada ponto $A$ do plano um outro
ponto $A' = T(A)$ do plano chamado *imagem* de $A$ por
$T$.

* Transformação **bijetiva** (ou bijetora) é uma transformação onde pontos
distintos possuem imagens distintas e cada ponto do plano é imagem de um
outro ponto desse plano.


> **Isometria** são transformações que *preservam distâncias*.

Em linguagem matemática, $T$ é uma isometria quando

$$ d[T(A),T(B)] = d(A,B) $$

para quaisquer pontos $A$ e $B$ do plano $\Pi$.

Toda isometria possui as seguintes propriedades:

* a imagem de uma reta por uma isometria é uma reta.
* uma isometria preserva paralelismo.
* uma isometria preserva ângulos.

Como consequência da definição, a imagem de uma figura $F$ por uma
isometria, é uma figura $F'$ *congruente* a $F$.

Abordaremos aqui três isometrias, que são: *translação*, *rotação* e
*reflexão*, e uma outra transformação que é a *homotetia*.

### Translação

A **translação** determinada pelo vetor $v$ é a transformação
$T_v: \Pi \to \Pi$ que leva cada ponto $A$ do plano $\Pi$ no
ponto $A' = A + v$ desse plano.

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figT1.jpg" style="margin-left: auto; margin-right: auto;">
                    <img src="figT1.jpg" alt="Translação determinada pelo vetor v" width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                Translação determinada pelo vetor v
            </td>
        </tr>
    </tbody>
</table>

A translação transforma toda reta em outra paralela e por ser uma
isometria, transforma qualquer figura em outra congruente.

A figura a seguir mostra a *translação determinada pelo vetor $v$*
aplicada a um triângulo $ABC$.

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figT2.jpg" style="margin-left: auto; margin-right: auto;">
                    <img src="figT2.jpg" alt="A translação $T_v$ transforma $ABC$ em $A'B'C'$" width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                A translação $T_v$ transforma $ABC$ em $A'B'C'$
            </td>
        </tr>
    </tbody>
</table>

Em outras palavras, a translação **movimenta** uma figura.

Para ilustrar a translação no TikZ vamos desenhar um [patinho][1].

![Patinho](patinho2.jpg)

```latex
\begin{tikzpicture}
    \draw (0,0) -- (2,1);
\end{tikzpicture}
```

No TikZ podemos aplicar as transformações geométricas de diversas
maneiras, usando diversos comandos num conjunto de objetos ou num único
objeto em particular. Mas, para que haja um modelo padrão para diversas
aplicações usaremos o ambiente **scope**, assim teremos mais
flexibilidade na aplicação das transformações. Além disso, podemos usar
vários *scopes* na mesma figura.

Para a *translação* usaremos o comando `shift={(x,y)}`, então a
sintaxe é a seguinte:

```latex
\begin{tikzpicture}
    \begin{scope[shift={(x,y)}]}
        % desenhe aqui
    \end{scope}
\end{tikzpicture}
```

Exemplo: Vamos transladar o nosso [patinho][1].

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figpatoT01.jpg" style="margin-left: auto; margin-right: auto;">
                    <img src="figpatoT01.jpg" alt="Comentário sobre a translação x=3cm e y=2cm" width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                Comentário sobre a translação x=3cm e y=2cm
            </td>
        </tr>
    </tbody>
</table>

### Rotação

Fixemos um ponto O no plano $\Pi$ agora orientado com o sentido
positivo anti-horário. Dado um ângulo $\alpha$, a **rotação de
centro O e amplitude $\alpha$** é a transformação que a cada ponto $A$ do plano $\Pi$ associa o ponto $A' = R_\alpha(A)$ de forma que se tenha $OA' = OA$, onde $AOA' = \alpha$ e o sentido de $A$ para $A'$ (em torno de $O$), positivo.

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figRo1.jpg" style="margin-left: auto; margin-right: auto;">
                    <img src="figRo1.jpg" alt="A rotação de centro O e amplitude \alpha leva A em A'." width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                A rotação de centro O e amplitude \alpha leva A em A'.
            </td>
        </tr>
    </tbody>
</table>

No TikZ usamos o comando `rotate`, que usualmente faz uma rotação em graus.

```latex
\begin{tikzpicture}
    \begin{scope}[rotate = \alpha]
        % desenhe aqui
    \end{scope}
\end{tikzpicture}
```

Exemplo: Vamos girar o nosso [patinho][1] em $60^\circ$.

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figpatoRo1.jpg" style="margin-left: auto; margin-right: auto;">
                    <img src="figpatoRo1.jpg" alt="Rotação do patinho em $60^\circ$." width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                Rotação do patinho em $60^\circ$.
            </td>
        </tr>
    </tbody>
</table>

### Reflexão

Dada uma reta $r$, dizemos que o ponto $A'$ é **simétrico** do
ponto $A$ em relação a $r$ quando $r$ é *mediatriz* de
$AA'$. Se $A$ pertence a $r$, dizemos que o seu simétrico em
relação a $r$ é ele próprio.

A **reflexão** em torno da reta $r$ (também chamada de simetria em
relação a $r$) é a transformação $S_r$ que faz corresponder a
cada ponto $A$ do plano o ponto $A' = S_r(A)$, simétrico de
$A$ em relação a $r$.

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figRe1.jpg" style="margin-left: auto; margin-right: auto;">
                    <img src="figRe1.jpg" alt="O ponto A' é simétrico ao ponto A por reflexão." width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                O ponto A' é simétrico ao ponto A por reflexão.
            </td>
        </tr>
    </tbody>
</table>

Um processo prático para a construção do simétrico de um ponto em
relação a uma reta consiste em traçar pelo ponto $A$ dois círculos
quaisquer com centros em $r$. O outro ponto comum a esses círculos
será $A'$, simétrico de $A$.

A reflexão é uma isometria e portanto, transforma cada figura $F$ em uma
outra $F'$ *congruente* a $F$. Entretanto, a reflexão inverte a orientação
do plano, como na figura a seguir, onde o triângulo $ABC$ foi transformado
em $A'B'C'$.

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figRe2.jpg" style="margin-left: auto; margin-right: auto;">
                    <img src="figRe2.jpg" alt="A reflexão inverte a figura em relação a reta $r$." width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                A reflexão inverte a figura em relação a reta $r$.
            </td>
        </tr>
    </tbody>
</table>

Um exemplo muito comum para o uso de reflexão é o desenho de rostos,
reflexão de objetos sobre lago, entre outros.

Como a reflexão é dada em torno de uma reta, no TikZ precisaremos fazer
uma adaptação. Mas primeiro vejamos as reflexões **vertical** e
**horizontal**.

#### Reflexão horizontal

Muito usado para desenhar rostos ou cabeças de animais.

A sintaxe para reflexão horizontal no TikZ é a seguinte:

```latex
\begin{tikzpicture}
    \begin{scope}[x=-1]
        % desenhe aqui
    \end{scope}
\end{tikzpicture}
```

O segredo está em $[x = -1]$, que inverte os pontos do plano em
relação ao eixo $y$.

No exemplo a seguir desenhamos um ponto $A$ no primeiro quadrante,
mas com $x = -1$ o resultado mostra o ponto $A'$ no segundo
quadrante.

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figRe3.jpg" style="margin-left: auto; margin-right: auto;">
                    <img src="figRe3.jpg" alt="Ponto A' obtido por reflexão horizontal." width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                Ponto A' obtido por reflexão horizontal.
            </td>
        </tr>
    </tbody>
</table>

> CÓDIGOS AQUI

```latex
\begin{tikzpicture}
    \begin{scope}[x=-1]
        % TODO
    \end{scope}
\end{tikzpicture}
```

Vejamos agora como fica nosso patinho após uma reflexão horizontal.

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figpatoRe1.jpg" style="margin-left: auto; margin-right: auto;">
                    <img src="figpatoRe1.jpg" alt="Patinho da esquerda obtido por reflexão." width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                Patinho da esquerda obtido por reflexão.
            </td>
        </tr>
    </tbody>
</table>

Usando o comando `\foreach` podemos desenhar as duas figuras de uma vez.

```latex
    % codigos
```

Quando aplicamos a variável em `[x = \m]` obtemos as duas figuras.

E finalmente, o desenho de uma cabeça.

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figcabeca.jpg" style="margin-left: auto; margin-right: auto;">
                    Cimg src="figcabeca.jpg" alt="cabeça" width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                Cabeça
            </td>
        </tr>
    </tbody>
</table>

#### Reflexão vertical

Um exemplo típico é a reflexão de um objeto sobre um lago.

A sintaxe para reflexão vertical no TikZ é

```latex
\begin{tikzpicture}
    \foreach \n in {-1,1}{
        \begin{scope}[y=\n]
            % desenhe aqui
        \end{scope}
    }
\end{tikzpicture}
```

Um ponto $A$ desenhado no primeiro quadrante, com $y = -1$,
resulta no ponto $A'$ no quarto quadrante.

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figRe4.jpg" style="margin-left: auto; margin-right: auto;">
                    <img src="figRe4.jpg" alt="Ponto A' obtido por reflexão vertical." width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                Ponto A' obtido por reflexão vertical.
            </td>
        </tr>
    </tbody>
</table>

```latex
    % codigos
```

Agora vamos colocar o patinho num lago.

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figpatoRe2.jpg" style="margin-left: auto; margin-right: auto;">
                    <img src="figpatoRe2.jpg" alt="Patinho no lago." width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                Patinho no lago.
            </td>
        </tr>
    </tbody>
</table>

#### Reflexão em torno de uma reta

Para refletir um ponto em torno de uma reta $r$ qualquer precisamos
levar em consideração o ângulo $\alpha$ de inclinação da reta
$r$ em relação ao eixo $x$, onde a equação da reta $r$ é
dada por $r: y = \alpha x$.

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figRe5.jpg" style="margin-left: auto; margin-right: auto;">
                    <img src="figRe5.jpg" alt="Reflexão em torno de uma reta." width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                Reflexão em torno de uma reta.
            </td>
        </tr>
    </tbody>
</table>

Lembrando que a inclinação da reta $r$ em [radianos][3] é dada por
$\alpha = \arctan \frac{y}{x}$, e que $\pi$ radianos equivale a
$180^\circ$.

Façamos uma reflexão no TikZ de um ponto $A(2,1)$ em relação a reta
$r$ dada por $y = \frac{\sqrt 3}{3}x$. Note que
$\alpha = 30^\circ$. A estratégia para realizar esta transformação é
fazer uma [reflexão horizontal] e depois uma [rotação]. Sendo assim,
precisaremos de dois *scopes* no nosso desenho, onde o segundo (mais
interno) faz a reflexão e o primeiro (mais externo) faz a rotação.

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figRe6.jpg" style="margin-left: auto; margin-right: auto;">
                    <img src="figRe6.jpg" alt="legenda" width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                legenda
            </td>
        </tr>
    </tbody>
</table>

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figRe7.jpg" style="margin-left: auto; margin-right: auto;">
                    <img src="figRe7.jpg" alt="legenda" width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                legenda
            </td>
        </tr>
    </tbody>
</table>

```latex
\begin{scope}[rotate = \alpha]
    \begin{scope}[y=-1]
        ...
    \end{scope}
\end{scope}
```

Note que a ordem é importante.

### Homotetia

Fixado um ponto $O$ no plano $\Pi$ e dado número real $k \ne 0$, a
*homotetia de centro $O$ e razão $k$* é a transformação que a cada
ponto $A$ do plano $\Pi$ associa o ponto $A' = H(A)$ tal que
$\vec{OA'} = k.\vec{OA}$.

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figH1.jpg" style="margin-left: auto; margin-right: auto;">
                    <img src="figH1.jpg" alt="A homotetia amplia, reduz ou inverte uma figura." width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                A homotetia amplia, reduz ou inverte uma figura.
            </td>
        </tr>
    </tbody>
</table>

$k$ é um fator multiplicador onde se $k > 0$ a homotetia chama-se
*direta* e se $k < 0$ a homotetia chama-se *inversa*.

Se $k = -1$ temos uma [reflexão].

Se $k = 1$ então $A' = A$ e portanto a $H$ é a transformação
*identidade* (a figura é idêntica).

Se $k > 1$ a homotetia **amplia** a figura.

Se $0 < k < 1$ a homotetia **reduz** a figura.

Se $k = 0$ a figura torna-se um ponto adimensional.

A homotetia *preserva ângulos* e se $A' = H(A)$ e $B' = H(B)$ temos
que

[ OA' = k.OA e OB' = k.OB ]

portanto $A'B' = |k|.AB$, isto significa que a homotetia transforma
qualquer figura $F$ em uma figura $F'$ **semelhante** a $F$.

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figH2.jpg" style="margin-left: auto; margin-right: auto;">
                    <img src="figH2.jpg" alt="$A_1 B_1 C_1$ é uma ampliação de $ABC$ e $A_2 B_2 C_2$ é uma inversão reduzida." width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                $A_1 B_1 C_1$ é uma ampliação de $ABC$ e $A_2 B_2 C_2$ é uma inversão reduzida.
            </td>
        </tr>
    </tbody>
</table>

No TikZ fazemos uma homotetia com o comando `[scale = k]`, onde $k$ é o
número que amplia, reduz ou inverte a figura.

```latex
\begin{tikzpicture}
    \foreach \k in {-1,1,2}{
        \begin{scope}[scale = \k]
            % desenhe aqui
        \end{scope}
    }
\end{tikzpicture}
```

<table align="center" cellpadding="0" cellpadding="0" style="margin-left: auto; margin-right: auto; text-align: center; border: none;">
    <tbody>
        <tr>
            <td style="text-align: center;">
                <a href="figpatoH1.jpg" style="margin-left: auto; margin-right: auto;">
                    <img src="figpatoH1.jpg" alt="Patinho invertido, original e ampliado." width="300px">
                </a>
            </td>
        </tr>
        <tr>
            <td style="text-align: center;">
                Patinho invertido, original e ampliado.
            </td>
        </tr>
    </tbody>
</table>

[0]: http://latexbr.blogspot.com.br/search/label/TikZ