Medindo desenhos no TikZ
========================

Medindo desenhos no TikZ
------------------------

Algumas vezes precisamos inserir medidas em nossos desenhos, veremos aqui como calcular medidas automaticamente e inserir cotas nos desenhos com o [TikZ].

#####Inserindo cotas
O código a seguir foi desenvolvido por _ESultanik_ em resposta à questão [Dimensioning of a technical drawing in TikZ]. Porém, aqui ele se encontra com algumas adaptações.

```latex
\usepackage{tikz}
%bibliotecas
\usetikzlibrary{arrows,calc,patterns,decorations.markings}
%Define as cotas
\pgfarrowsdeclarecombine{|<}{>|}{|}{|}{latex}{latex}
\def\Dimline[#1][#2][#3]{
 \begin{scope}[>=latex,red] % redefine as flechas
  \draw let \p1=#1, \p2=#2, \n0={veclen(\x2-\x1,\y2-\y1)} in [|<->|,
  decoration={markings,mark=at position .5 with {\node[#3] at (0,0) {\DimScale{\n0}};},
  },
  postaction=decorate] #1 -- #2 ;
 \end{scope}
}
%Define o arredondamento das casas decimais
\def\DimScale#1{\pgfmathparse{#1/28.4}\pgfmathprintnumberto[precision=1]{\pgfmathresult}{\roundednumber} \roundednumber cm}
```

Esta é a sequência de comandos que define e calcula as cotas. Vamos entender algumas partes importantes:

\usetikzlibrary{...} - carrega algumas bibliotecas do TikZ.
\pgfarrowsdeclarecombine - a partir daí define-se a cota. É no trecho veclen(\x2-\x1,\y2-\y1) que o TikZ calcula a distância entre dois pontos.
\DimScale - define o arredondamento das casas decimais.

O básico
A partir daí criamos os pontos usando o comando \coordinate ([nomeando coordenadas]) e desenhamos a figura.

```latex
\begin{tikzpicture}
%coordenadas
\coordinate[label=left:A1] (A1) at (0,0);
\coordinate[label=right:B1] (B1) at (4,0);
%figura
\draw[*-*,blue,line width=1pt] (A1) -- (B1);
%cotas
\Dimline[($(A1)+(0,-.5)$)][($(B1)+(0,-.5)$)][below];
\end{tikzpicture}
```

A cota é inserida com o comando
```latex
\Dimline[($(A1)+(0,-.5)$)][($(B1)+(0,-.5)$)][below];
```

Observe que no trecho ($(A1)+(0,-.5)$) a cota fica deslocada 5mm para baixo ([coordenadas relativas]).

Veja dois exemplos: retas e triângulo retângulo.
```latex
\usepackage{tikz}
%bibliotecas
\usetikzlibrary{arrows,calc,patterns,decorations.markings}
%Define as cotas
\pgfarrowsdeclarecombine{|<}{>|}{|}{|}{latex}{latex}
\def\Dimline[#1][#2][#3]{
 \begin{scope}[>=latex,red] % redefine as flechas
  \draw let \p1=#1, \p2=#2, \n0={veclen(\x2-\x1,\y2-\y1)} in [|<->|,
  decoration={markings,mark=at position .5 with {\node[#3] at (0,0) {\DimScale{\n0}};},
  },
  postaction=decorate] #1 -- #2 ;
 \end{scope}
}
%Define o arredondamento das casas decimais
\def\DimScale#1{\pgfmathparse{#1/28.4}\pgfmathprintnumberto[precision=1]{\pgfmathresult}{\roundednumber} \roundednumber cm}
\begin{tikzpicture}
%coordenadas
\coordinate[label=left:A1] (A1) at (0,0);
\coordinate[label=below:A2] (A2) at (6,0);
\coordinate[label=right:B1] (B1) at (4,0);
\coordinate[label=below:B2] (B2) at (11,0);
\coordinate[label=C1] (C1) at (6,3);
\coordinate[label=C2] (C2) at (7,3);
%figura
\draw[*-*,blue,line width=1pt] (A1) -- (B1);
\draw[*-*,blue,line width=1pt] (A2) -- (C1);
\draw[*-*,blue,line width=1pt] (B2) -- (C2);
%cotas
\Dimline[($(A1)+(0,-.5)$)][($(B1)+(0,-.5)$)][below];
\Dimline[($(A2)+(-.5,0)$)][($(C1)+(-.5,0)$)][left];
\Dimline[($(B2)+(0.3,0.3)$)][($(C2)+(0.3,0.3)$)][right];
\end{tikzpicture}
```

![image](http://3.bp.blogspot.com/-VqxzTbDUhzE/Ter9A5VL2nI/AAAAAAAAAMs/1yykk92Uvw0/s400/dimension01.png)

```latex
%...
\begin{tikzpicture}
%coordenadas
\coordinate[label=below left:A] (A) at (0,0);
\coordinate[label=below right:B] (B) at (4,0);
\coordinate[label=C] (C) at (0,3);
%figura
\draw[blue,line width=1pt] (A) -- (B) -- (C) -- cycle;
%cotas
\Dimline[($(A)+(0,-.5)$)][($(B)+(0,-.5)$)][below];
\Dimline[($(A)+(-.5,0)$)][($(C)+(-.5,0)$)][left];
\Dimline[($(B)+(0.3,0.3)$)][($(C)+(0.3,0.3)$)][right];
\end{tikzpicture}
```

![image](http://3.bp.blogspot.com/-5LxnhhJ3pJE/Ter9F4C-LOI/AAAAAAAAAMw/jTNJEIOPibY/s320/dimension02.png)

#####Um exemplo
Veja um exemplo mais parecido com o que originou esse tema.

```latex
\usepackage{tikz}
%bibliotecas
\usetikzlibrary{arrows,calc,patterns,decorations.markings}
%Define as cotas
\pgfarrowsdeclarecombine{|<}{>|}{|}{|}{latex}{latex}
\def\Dimline[#1][#2][#3]{
 \begin{scope}[>=latex,red] % redefine as flechas
  \draw let \p1=#1, \p2=#2, \n0={veclen(\x2-\x1,\y2-\y1)} in [|<->|,
  decoration={markings,mark=at position .5 with {\node[#3] at (0,0) {\DimScale{\n0}};},
  },
  postaction=decorate] #1 -- #2 ;
 \end{scope}
}
%define mais uma cota para raio
\def\DimRaio[#1][#2][#3]{
 \begin{scope}[>=latex,red] % redefine as flechas
  \draw let \p1=#1, \p2=#2, \n0={veclen(\x2-\x1,\y2-\y1)} in [<-,
  decoration={markings,mark=at position 1 with {\node[#3] at (0,0) {R\DimScale{\n0}};},
  },
  postaction=decorate] #1 -- #2 ;
 \end{scope}
}
%Define o arredondamento das casas decimais
\def\DimScale#1{\pgfmathparse{#1/28.4}\pgfmathprintnumberto[precision=1]{\pgfmathresult}{\roundednumber} \roundednumber cm}
%Define uma nova hachura de preenchimento com espa\c{c}amento diferente \pgfdeclarepatternformonly{hachura}{\pgfqpoint{-1pt}{-1pt}}{\pgfqpoint{10pt}{10pt}}{\pgfqpoint{9pt}{9pt}}%
{
 \pgfsetlinewidth{0.4pt}
 \pgfpathmoveto{\pgfqpoint{0pt}{0pt}}
 \pgfpathlineto{\pgfqpoint{9.1pt}{9.1pt}}
 \pgfusepath{stroke}
}
\begin{tikzpicture}
%coordenadas
\coordinate (A) at (0,0);
\coordinate (B) at (-1.41,-0.5);
\coordinate (C) at (-2.5,-0.5);
\coordinate (D) at (-2.5,0.5);
\coordinate (E) at (-1.41,0.5);
\coordinate (F) at (1.12,1);
\coordinate (G) at (3,1);
\coordinate (H) at (3,0.4);
\coordinate (I) at (1.45,0.4);
\coordinate (J) at (1.45,-0.4);
\coordinate (K) at (3,-0.4);
\coordinate (L) at (3,-1);
\coordinate (M) at (1.12,-1);
%figura
\draw[even odd rule,pattern=hachura]
(A) circle (1.5)
(A) circle (0.5cm);
\draw[thick] (B) -- (C) -- (D) -- (E);
\draw[thick] (F) -- (G) -- (H) -- (I);
\draw[thick] (J) -- (K) -- (L) -- (M);
%eixos
\draw[cyan,dashed] (0,-1.8) -- (0,1.8) (-2.8,0) -- (3.3,0);
%cotas
\Dimline[($(C)+(-.5,0)$)][($(D)+(-.5,0)$)][left];
\Dimline[($(C)+(0,-1.5)$)][($(L)+(0,-1)$)][below];
\Dimline[($(L)+(.5,0)$)][($(G)+(.5,0)$)][right];
%cota diametro
\Dimline[($(A)+(-45:-.5)$)][($(A)+(-45:.5)$)][above right,inner sep=0,outer sep=2,fill=white,font=\tiny];
%cota raio
\DimRaio[(A)][($(A)+(220:1.5)$)][left,font=\tiny];
%prolongamento
\draw[red] (C) ++(0,-1mm) -- ++(0,-1.5);
\draw[red] (L) ++(0,-1mm) -- ++(0,-1);
\end{tikzpicture}
```

![image](http://3.bp.blogspot.com/-GYRwNM23pt4/Ter9KOwBnRI/AAAAAAAAAM0/JMrO1F7jOOc/s400/dimension03.png)

Mais informações: [Dimensioning of a technical drawing in TikZ], [How to solve the 10.09999 rounding problem with pgfmath?], [How to omit printing the decimal part in pgfmath macros].



[TikZ]:http://latexbr.blogspot.com/2011/01/desenhando-com-tikz.html

[Dimensioning of a technical drawing in TikZ]:http://tex.stackexchange.com/questions/14901/dimensioning-of-a-technical-drawing-in-tikz

[nomeando coordenadas]:http://latexbr.blogspot.com/2011/05/sistemas-de-coordenadas-no-tikz.html

[coordenadas relativas]:http://latexbr.blogspot.com/2011/05/sistemas-de-coordenadas-no-tikz.html

[Dimensioning of a technical drawing in TikZ]:http://tex.stackexchange.com/questions/14901/dimensioning-of-a-technical-drawing-in-tikz

[How to solve the 10.09999 rounding problem with pgfmath?]:http://tex.stackexchange.com/questions/19626/how-to-solve-the-10-09999-rounding-problem-with-pgfmath

[How to omit printing the decimal part in pgfmath macros]:http://tex.stackexchange.com/questions/19588/how-to-omit-printing-the-decimal-part-in-pgfmath-macros