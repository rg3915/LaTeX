Indice remissivo no LaTeX
=========================

Indice remissivo no LaTeX
-------------------------
Neste post veremos:

* Criando índice remissivo
* Indice remissivo personalizado
* Indice remissivo em 3 colunas
* Compilando índice remissivo com Rubber
* Compilando índice remissivo com Latexmk


####Criando índice remissivo
Para criar índice remissivo no LaTeX usamos o pacote [makeidx]. E ainda no preâmbulo escrevemos \makeindex para habilitar os comandos de indexação.

```latex
\usepackage{makeidx}
\makeindex
```

Para criar um índice usamos o comando \index{chave}, onde chave é a palavra de entrada do índice. Também podemos escrever \index{chave!subchave}.

Veja alguns exemplos.

```latex
\index{Cor}
\index{Cor!Amarelo}
```

E no final do documento escrevemos \printindex para imprimir o índice remissivo.

Um exemplo mínimo:
```latex
\documentclass[a4paper]{article}
\usepackage{makeidx}
\makeindex
\begin{document}
 texto
 \index{Cor}
 \index{Cor!Amarelo}
 \printindex
\end{document}
```

Para compilar digite no terminal:
```
pdflatex arquivo
makeindex arquivo
pdflatex arquivo
```

Baixe [indice_remissivo.tex]

####Indice remissivo personalizado

A ideia é retornar um índice remissivo agrupado com uma letra maiúscula em todas as letra do alfabeto.
Para isso, além dos passos para se criar um índice remissivo crie um arquivo com o nome indexstyle.ist na mesma pasta do seu arquivo.tex com o seguinte conteúdo.

```latex
%%% Coloca cada letra entre grupos no início da linha
heading_prefix "{\\bfseries " % Insert in front of letter
heading_suffix "}\\nopagebreak\n" % Append after letter
headings_flag 1 % Turn on headings (uppercase)
%%% Traduz ‘‘Symbols’’ e ‘‘Numbers’’ para Portugues.
symhead_positive "S\\’{\\i}mbolos"
symhead_negative "s\\’{\\i}mbolos"
numhead_positive "N\\’umeros"
numhead_negative "n\\’umeros"
```

Para compilar digite no terminal:

```
pdflatex arquivo
makeindex -s indexstyle.ist arquivo
pdflatex arquivo
```

![image](http://2.bp.blogspot.com/-b4FWNy8A5nM/UQXvQnygX3I/AAAAAAAAAsM/rV75U1FMa1w/s200/indice_remissivo.png)

Baixe [indexstyle.ist] e [indice_remissivo_personalizado.tex]

####Indice remissivo em 3 colunas

Para retornar o índice remissivo em três colunas escrevemos o seguinte comando no preâmbulo:
Requer o pacote [multicol].
```latex
\makeatletter
\renewenvironment{theindex}
 {\if@twocolumn
  \@restonecolfalse
 \else
  \@restonecoltrue
 \fi
 \setlength{\columnseprule}{0pt}
 \setlength{\columnsep}{35pt}
 \begin{multicols}{3}[\section*{\indexname}]
 \markboth{\MakeUppercase\indexname}%
   {\MakeUppercase\indexname}%
 \thispagestyle{plain}
 \setlength{\parindent}{0pt}
 \setlength{\parskip}{0pt plus 0.3pt}
 \relax
 \let\item\@idxitem}%
 {\end{multicols}\if@restonecol\onecolumn\else\clearpage\fi}
\makeatother
```

![image](http://1.bp.blogspot.com/-my_WKkwe-Tk/UQXvkX1UQxI/AAAAAAAAAsY/yDahF1E-D4E/s320/indice_remissivo_tres_colunas.png)

Baixe [indice_remissivo_tres_colunas.tex]

####Compilando índice remissivo com Rubber

Para compilar o índice remissivo usando o [Rubber] basta digitar no terminal
```
rubber -d arquivo
```

Se estiver usando o arquivo _indexstyle.ist_, então escreva
```latex
% rubber: makeidx.style indexstyle.ist
\documentclass[a4paper]{article}
```

na primeira linha do seu arquivo.tex. Assim o Rubber interpreta o conteúdo de _indexstyle.ist_ sem a necessidade de opções adicionais durante a compilação. A partir dai é só compilar com o Rubber normalmente.
Para limpar os arquivos auxiliares da compilação digite
```
rubber --clean arquivo
```

Baixe [indice_remissivo_rubber.tex]

####Compilando índice remissivo com Latexmk

```
latexmk -pdf arquivo
```
que ele já faz tudo. Para limpar digite
```
latexmk -c
```

Baixe
[indice_remissivo.tex]
[indexstyle.ist]
[indice_remissivo_personalizado.tex]
[indice_remissivo_tres_colunas.tex]
[indice_remissivo_rubber.tex]

O [Latexmk] é o compilador mais simples e fácil de usar. Basta digitar

[makeidx]:http://www.tex.ac.uk/tex-archive/help/Catalogue/entries/makeindex.html

[indice_remissivo.tex]:https://bitbucket.org/rg3915/latex/downloads/indice_remissivo.tex

[indexstyle.ist]:https://bitbucket.org/rg3915/latex/downloads/indexstyle.ist

[indice_remissivo_personalizado.tex]:https://bitbucket.org/rg3915/latex/downloads/indice_remissivo_personalizado.tex

[multicol]:http://www.tex.ac.uk/tex-archive/help/Catalogue/entries/multicol.html

[indice_remissivo_tres_colunas.tex]:https://bitbucket.org/rg3915/latex/downloads/indice_remissivo_tres_colunas.tex

[Rubber]:http://latexbr.blogspot.com.br/2011/11/compilando-com-rubber.html

[indice_remissivo_rubber.tex]:https://bitbucket.org/rg3915/latex/downloads/indice_remissivo_rubber.tex

[Latexmk]:http://latexbr.blogspot.com.br/2012/06/compilando-com-latexmk.html

[indice_remissivo.tex]:https://bitbucket.org/rg3915/latex/downloads/indice_remissivo.tex

[indexstyle.ist]:https://bitbucket.org/rg3915/latex/downloads/indexstyle.ist

[indice_remissivo_personalizado.tex]:https://bitbucket.org/rg3915/latex/downloads/indice_remissivo_personalizado.tex

[indice_remissivo_tres_colunas.tex]:https://bitbucket.org/rg3915/latex/downloads/indice_remissivo_tres_colunas.tex

[indice_remissivo_rubber.tex]:https://bitbucket.org/rg3915/latex/downloads/indice_remissivo_rubber.tex