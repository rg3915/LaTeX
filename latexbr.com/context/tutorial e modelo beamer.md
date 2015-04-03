Tutorial e modelo Beamer
========================

Tutorial e modelo Beamer
------------------------

Um tutorial e exemplo de [Beamer] é sempre bom para nossas apresentações, então baixe [beamer_modelo2013.tex] e [beamer_modelo2013.pdf] e leia o tutorial abaixo:

* Começando do começo
* Compilando
* Imagem como plano de fundo
* Expressões matemáticas
* Ambientes
* Verbatim e códigos de programação
* Figuras
* Tabelas
* Transição
* Bibliografia

[SLIDE MODELO DO BEAMER]

#####Começando do começo

Vejamos o mínimo para se começar um documento no Beamer:
```latex
\documentclass[aspectratio=169]{beamer}
\usepackage[utf8]{inputenc} % codificacao de caracteres
\usepackage[T1]{fontenc}    % codificacao de fontes
\usepackage[brazil]{babel}  % idioma
\usetheme{AnnArbor}         % tema
\usecolortheme{orchid}      % cores
\usefonttheme[onlymath]{serif} % fonte modo matematico
% Titulo
\title[\sc{Texto no rodap\'e}]{Modelo do Beamer - Digite o titulo}
\author[digite seu Nome]{digite seu Nome}
\institute{nome do instituto} % opcional
\date{\today}
```

A opção aspectratio=169 ajusta o documento para o modo wide screen 16:9.
Veja mais temas e cores em [Beamer theme matrix].

```atex
\begin{document}

\begin{frame}
  \titlepage
\end{frame}

\begin{frame}
Segundo frame
\end{frame}

\end{document}
```
Este exemplo já está pronto para gerar um slide no Beamer.
Note que \titlepage define o título no primeiro frame.

#####Mais configurações
Só que nosso modelo é mais robusto, tem muito mais configurações.
```latex
% Colocando numero de paginas no slide
\setbeamertemplate{footline}[frame number]

% Desativando os botoes de navegacao
\beamertemplatenavigationsymbolsempty

% Tela cheia
\hypersetup{pdfpagemode=FullScreen}

% Layout da pagina
\hypersetup{pdfpagelayout=SinglePage}

% Definicao de novos comandos
\providecommand{\sin}{} \renewcommand{\sin}{\hspace{2pt}\textrm{sen}}
\providecommand{\tan}{} \renewcommand{\tan}{\hspace{2pt}\textrm{tg}}
\newcommand{\R}{\mathbb{R}}

% Capa - requer o TikZ
\newcommand{\capa}{
    \begin{tikzpicture}[remember picture,overlay]
        \node at (current page.south west)
            {\begin{tikzpicture}[remember picture, overlay]
                \fill[shading=radial,top color=orange,bottom color=orange,middle color=yellow] (0,0) rectangle (\paperwidth,\paperheight);
            \end{tikzpicture}
          };
    \end{tikzpicture}
}
```

Todos os comandos são opcionais, mas dá uma aparência melhor a apresentação. A capa neste caso é o fundo laranja e amarelo que aparece ao fundo do frame de título.

#####Compilando
O processo de compilação é simples:
```
pdflatex beamer_modelo2013.tex
```
Mas como teremos códigos de programação escrito com o pacote minted a compilação deverá ser feita com o comando -shell-escape.
```
pdflatex -shell-escape beamer_modelo2013.tex
```
Se voce quiser usar o [LaTeXmk] digite
```
latexmk -pdf -shell-escape beamer_modelo2013.tex
```

#####Imagem como plano de fundo
Com o comando a seguir podemos inserir imagens como plano de fundo, bastando carregar o pacote graphics no preâmbulo.
```latex
{%
 \usebackgroundtemplate{
  \centering
  \includegraphics[width=\paperwidth]{figuras/figBackground}
 }

 % Frame 3: plano de fundo
 \begin{frame}
  \begin{center}
    % texto colorido
    \color{yellow}{\Huge Imagem como plano de fundo}
  \end{center}
 \end{frame}
}
```

Note que todo o código está dentro de chaves, isto permite que a figura fique apenas no frame selecionado.

#####Expressões matemáticas
```latex
% Frame 4: expressoes matematicas
\begin{frame}\frametitle{Express\~oes Matem\'aticas}

Seja $f: \R \to \R$ tal que $y = \sin x$.

Exemplo de uma equa\c c\~ao matem\'atica centralizada.

\[
S = \int_a^b \frac{\sqrt x}{x}dx
\]
\end{frame}
```

#####Ambientes
Por padrão o Beamer oferece dois ambientes que são: block e exampleblock.
```latex
% Frame 5: exemplo e solucao
\begin{frame}\frametitle{Exemplo e Solu\c c\~ao}
  
  \begin{block}{Exemplo}
    Este \'e um ambiente chamado \emph{block} com um titulo \emph{Exemplo}.
  \end{block}

  \begin{exampleblock}{Solu\c c\~ao}
    Este \'e um ambiente chamado \emph{exampleblock} com um titulo \emph{Solu\c c\~ao}.
  \end{exampleblock}

\end{frame}
```

Mas podemos definir mais ambientes no preâmbulo:

```latex
% Definicao de novos ambientes
\theoremstyle{Definition}
\newtheorem{defn}{Defini\c c\~ao}
\newtheorem{teo}[theorem]{Teorema}
\newtheorem{ex}[theorem]{Exemplo}
E usá-los no documento:
% Frame 6: novos ambientes
\begin{frame}\frametitle{Novos ambientes}
  
  \begin{defn}
    Novo ambiente chamado \emph{defini\c c\~ao}.
  \end{defn}

  \begin{teo}
    Novo ambiente chamado \emph{teorema}.
  \end{teo}

\end{frame}
```

#####Verbatim e códigos de programação
O verbatim serve para mostrar códigos na tela. Para usá-lo é necessário usar a opção [fragile] como segue:

```latex
% Frame 7: verbatim
\begin{frame}[fragile]\frametitle{Verbatim}
Para usar o verbatim no Beamer \'e necess\'ario usar a op\c c\~ao \verb|fragile|.

\begin{verbatim}
 \begin{frame}[fragile]\frametitle{Verbatim}
  % qualquer codigo LaTeX ou outros
 \end{frame}
\end{verbatim}

\end{frame}
```

O pacote [minted] permite mostrar códigos de programação com highlights. Para isso carregue o pacote minted e digite um exemplo de ambiente no preâmbulo:

```latex
% Ambiente Java (minted)
\newminted{java}{bgcolor=cyan!10}
E no documento digite:
% Frame 8: Linguagem de programacao
\begin{frame}[fragile]\frametitle{Linguagem de programa\c c\~ao}
Para mostrar c\'odigos de linguagem de programa\c c\~ao use o pacote \verb|minted|.

Exemplo de c\'odigo Java.

\begin{javacode}
public class HelloWorldApp {
    public static void main (String args[])
    {
      System.out.println("Hello World!");
    }
}
\end{javacode}
```

Para compilar com o pacote \verb|minted| \'e necess\'ario usar o comando \verb|-shell-escape| pelo terminal.

```latex
\begin{minted}[bgcolor=lightgray!20]{bash}
pdflatex -shell-escape minted01.tex
ou
latexmk -pdf -shell-escape minted01.tex
\end{minted}
\end{frame}
```

#####Figuras
Carregando o pacote graphics podemos inserir figuras nos formatos PNG, JPG ou PDF.

```latex
% Frame 9: Inserindo figuras
\begin{frame}\frametitle{Inserindo figuras}
Figuras devem ser inseridas no formato PNG, JPG ou PDF.

  \begin{figure}[h]
    \centering
    \includegraphics[height=0.6\paperheight]{figuras/figCoordEsf02}
    %\includegraphics[height=6cm]{figCoordEsf02}
    \caption{Sistema de coordenadas esf\'ericas.}\label{figCoordEsf02}
  \end{figure}
\end{frame}
```

Com o pacote [TikZ] podemos inserir figuras desenhadas em TikZ.

```latex
% Frame 10: figuras TikZ
\begin{frame}\frametitle{Figuras TikZ}
Figuras feitas com TikZ.

  \begin{figure}[h]
    \centering
    \input{figuras/integral}
    \caption{Integral.}\label{figintegral}
  \end{figure}
\end{frame}
```

#####Tabelas
Para usar os comandos \toprule,\midrule e \bottomrule carregue o pacote booktabs.

```latex
% Frame 11: tabela
\begin{frame}\frametitle{Tabelas}
  \begin{table}
    \centering
    \begin{tabular}{cclrr}
      \toprule
      ID & Quant & Produto & Unit & Total\\
      \midrule
      1 & 2 & manga     & 3,00 & 6,00\\
      2 & 7 & laranja   & 1,20 & 8,40\\
      3 & 5 & banana    & 3,50 & 17,50\\
      4 & 3 & melancia  & 8,00 & 24,00\\
      5 & 4 & abacaxi   & 4,00 & 16,00\\
      \midrule
       Total &   &      &      & 71,90\\
      \bottomrule
    \end{tabular}
    \caption{Lista de compras}
  \end{table}
\end{frame}
```



[Beamer]:http://www.ctan.org/tex-archive/macros/latex/contrib/beamer/

[beamer_modelo2013.tex]:https://bitbucket.org/rg3915/latex/downloads/beamer_modelo2013.tex

[beamer_modelo2013.pdf]:https://bitbucket.org/rg3915/latex/downloads/beamer_modelo2013.pdf

[Beamer theme matrix]:http://www.hartwork.org/beamer-theme-matrix/

[LaTeXmk]:http://latexbr.blogspot.com.br/2012/06/compilando-com-latexmk.html

[minted]:http://latexbr.blogspot.com.br/2012/08/dica-mostrando-codigos-no-latex-com.html

[TikZ]:http://latexbr.blogspot.com.br/2011/01/desenhando-com-tikz.html
