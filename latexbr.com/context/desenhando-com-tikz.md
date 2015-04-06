Desenhando com TikZ
===================

Desenhando com TikZ
-------------------


TikZ é um poderoso pacote de desenho dentro do LaTeX desenvolvido por Till Tantau. A linguagem do TikZ é similar a do [Postscript]  (baixe este livro). Além de figuras com qualidade vetorial e precisão matemática, como retas, arcos, círculos, gráficos de funções; o TikZ também trabalha com curvas, esquemas (tipo organograma), etc.
Dois recursos exclusivos e muito úteis do TikZ é o [nó]  (node) e [posição absoluta]. Veja no link.
Aqui veremos apenas o básico de TikZ. Mais informações no final do tópico.
Para inserir uma figura TikZ carregue o pacote TikZ seguido de um preâmbulo
mínimo.

```latex
\documentclass{article}
\usepackage{tikz}
\begin{document}
 \begin{tikzpicture}
  %escreva os códigos de desenho TikZ aqui.
 \end{tikzpicture}
\end{document}
```

Vamos ao primeiro exemplo com um simples segmento de reta.

![image](https://lh5.googleusercontent.com/-_uglDNuHink/TXv1OGKZYCI/AAAAAAAAAFg/jchrqi6V4oM/s200/figreta.png)
```latex
\documentclass{article}
\usepackage{tikz}
\begin{document}
 \begin{tikzpicture}
  \draw (0,0) -- (2,1); %reta
 \end{tikzpicture}
\end{document}
```

Lembrando que todos os elementos do seu desenho devem estar entre \begin{tikzpicture} e \end{tikzpicture} vejamos o código mais simples para mais alguns elementos:

![image](https://lh4.googleusercontent.com/-uNNAXxefwEI/TXv1IghWxhI/AAAAAAAAAFc/6hOYBMhl4S4/s320/figExemplos.png)

```latex
\begin{tikzpicture}
%círculo com centro na origem e raio unitário
 \draw[blue] (0,0) circle (1);
%também podemos usar unidades de medida
 \draw (0,0) circle (8mm);
%retângulo
 \draw (-1,-1) rectangle (2,1);
%arco
 \draw[->,red] (1.2,0) arc (0:60:1.2);
\end{tikzpicture}
%curvas
\begin{tikzpicture}
 \draw[line width=10pt] (0,0) .. controls (1,1) .. (4,0)
  .. controls (5,0) and (5,1) .. (4,1);
 \draw[color=gray] (0,0) -- (1,1) -- (4,0) -- (5,0) -- (5,1) -- (4,1);
\end{tikzpicture}
```

![image](http://1.bp.blogspot.com/_nn5BgloqIug/TSJQyk-2FOI/AAAAAAAAADk/1l2JLTkQF0I/s400/fig01.jpg)

```latex
%gráfico de função
\begin{tikzpicture}
  \draw[->] (-3,0) -- (3,0);
  \draw[->] (0,-1) -- (0,4);
  \draw[blue,smooth,samples=100,domain=-2.0:2.0] plot(\x,{\x^2});
\end{tikzpicture}
```

![image](http://3.bp.blogspot.com/_nn5BgloqIug/TSJQ-5n70pI/AAAAAAAAADs/l7YI6yhVkeM/s400/fig02.jpg)

```latex
%função seno
\begin{tikzpicture}
  \draw[->] (-3.14,0) -- (3.14,0);
  \draw[->] (0,-1.1) -- (0,1.1);
  \draw[blue,smooth,samples=100,domain=-3.14:3.14] plot(\x,{sin(\x r)});
\end{tikzpicture}
```

![image](http://3.bp.blogspot.com/_nn5BgloqIug/TSJRIRwZ3XI/AAAAAAAAAD0/BcLnk9wzvYI/s400/fig03.jpg)

Repare em sin(\x r) o uso do 'r' para conversão em radianos; sem ele não teríamos a curva do seno como a conhecemos.

A vantagem do TikZ também é que podemos compilar via PDFLaTeX direto.

Veja exemplos de Tikz no site [TeXample] e leia [PGF manual 2.10] e [PGF/TikZ Graphics for LaTeX]



[Postscript]:http://www.orbispictus.com.br/downloads.php?cat_id=7

[nó]:http://latexbr.blogspot.com/2011/01/usando-node-do-tikz.html

[posição absoluta]:http://latexbr.blogspot.com/2011/01/trabalhando-com-posicao-absoluta-no.html

[TeXample]:http://www.texample.net/tikz/examples/

[PGF manual 2.10]:http://linorg.usp.br/CTAN/graphics/pgf/base/doc/generic/pgf/pgfmanual.pdf

[PGF/TikZ Graphics for LaTeX]:http://www.mathematik.uni-leipzig.de/~hellmund/LaTeX/pgf-tut.pdf