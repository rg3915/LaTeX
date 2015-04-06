Desenhando com PSTricks
=======================

Desenhando com PSTricks
-----------------------


PSTricks é uma coleção de macros do LaTeX onde é possível se fazer desenhos através de uma linguagem de programação baseada em PostScript. Este recurso é vantajoso por oferecer uma excelente qualidade de impressão e muitas opções de configurações como por exemplo, espessura de linha, tracejado, flechas, letras, expressões matemáticas, etc.
Para inserir uma figura PSTricks carregue o pacote pstricks-add seguido de um reâmbulo mínimo.

```latex
\documentclass[a4paper]{article}
\usepackage{indentfirst}
\usepackage[latin1]{inputenc}
\usepackage[brazil]{babel}
\usepackage[T1]{fontenc}
\usepackage{pstricks-add}

\title{Desenhando com PSTricks}
\date{Junho de 2010}

\begin{document}

\end{document}
```

Entre o ambiente document escreva o seguinte código:

```latex
\begin{document}
\begin{pspicture}
desenho pstricks
\end{pspicture}
\end{document}
```

O desenho ficará dentro do ambiente pspicture.
Vejamos alguns exemplos simples de uma figura desenhada em PSTricks:

![image](http://2.bp.blogspot.com/_nn5BgloqIug/TCpq8M0R3EI/AAAAAAAAACA/kLJ82F-iaIw/s400/figCirc01a.jpg)

Você pode inserir o código direto no seu arquivo .tex principal, digitando:

```latex
\begin{figure}[!htb]
\centering
\begin{pspicture}(0,0)(3,3)
\psline(1.5,1.5)(3,1.5)
\pscircle(1.5,1.5){1.5}
\psdots[linecolor=blue](1.5,1.5)
\end{pspicture}
\caption{Exemplo simples.}\label{figCirc01}
\end{figure}
```

Ou criar uma subpasta chamada figuras e salvar a figura lá dentro, por exemplo, figCirc01.tex. E a partir daí digitar:

```latex
\begin{figure}[!htb]
\centering
\input{figuras/figCirc01}
\caption{Exemplo simples.}\label{figCirc01}
\end{figure}
```

As figuras em PSTricks são salvas no formato .tex e chamadas com o comando \input.
Com o PSTricks podemos desenhar desde elementos primitivos como setor circular, retângulo e losango

![image](http://3.bp.blogspot.com/_nn5BgloqIug/TCqvkG7m7mI/AAAAAAAAACQ/kdLwi-EQLW8/s400/figPrimitivosa.jpg)

até gráficos de funções e figuras mais complexas com opções diversas.

Exemplo de figura com linha tracejada e indicação de ângulos.


![image](http://3.bp.blogspot.com/_nn5BgloqIug/TCqu_svAiII/AAAAAAAAACI/IjVH7hbKBdA/s400/figCirc02a.jpg)

Exemplo de figura com texto e projeção de linha.

![image](http://4.bp.blogspot.com/_nn5BgloqIug/TCqv42Xg-yI/AAAAAAAAACY/soHUSj9C2AM/s400/figCirc03a.jpg)

E, por fim, um exemplo de uma função real, no caso as funções seno e cosseno.

![image](http://3.bp.blogspot.com/_nn5BgloqIug/TCqwBytLJeI/AAAAAAAAACg/8_rZLTcpPcM/s400/figSenoCossenoa.jpg)

Mais informações em:

[Timothy V. Zandt, "PSTricks - PostScript macros for Generic TeX."]

[Herbert Voss e D. Rodriguez, "pstricks-add - additionals Macros for pstricks."]

exemplos de Pstricks.

Veja a apostila [Desenhando com PSTricks.] no scribd.


[Timothy V. Zandt, "PSTricks - PostScript macros for Generic TeX."]:http://ctan.tche.br/graphics/pstricks/base/doc/pstricks-doc.pdf

[Herbert Voss e D. Rodriguez, "pstricks-add - additionals Macros for pstricks."]:http://ctan.org/tex-archive/graphics/pstricks/contrib/pstricks-add/pstricks-add-doc.pdf

[Desenhando com PSTricks.]:http://www.scribd.com/doc/33931231/Desenhando-Com-PSTricks

