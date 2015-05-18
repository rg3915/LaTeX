Dica: Símbolo de 1/2 (meio) e outras frações com xfrac
======================================================

Dica: Símbolo de 1/2 (meio) e outras frações com xfrac
------------------------------------------------------


O símbolo de fração mais utilizado pelos digitadores, 1/2 (meio) pode ser escrito no LaTeX com o pacote [xfrac]. É claro que pode ser usada qualquer outra fração.

```latex
\documentclass{article}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{xfrac}

\begin{document}

\sfrac{1}{2}, $\sfrac{1}{2}$

$\mathbf{3\times\sfrac{1}{2}}$

\fontfamily{ppl}\selectfont Palatino: \sfrac{1}{2}

\fontfamily{ptm}\selectfont Times: \sfrac{1}{2}

\end{document}
```

![image](http://3.bp.blogspot.com/-jXZ-kyN1Ac8/UDxA5tNeVgI/AAAAAAAAAhU/miZsgzLB5u8/s320/xfrac.png)


Veja o exemplo em [ShareLaTeX].

Experimente também o pacote [nicefrac].


[xfrac]:http://dante.ctan.org/tex-archive/macros/latex/contrib/l3packages/xfrac.pdf




[ShareLaTeX]:https://www.sharelatex.com/project/503b9d0e7bf7b9e47a011fb4

[nicefrac]:http://www.ctex.org/documents/packages/special/units.pdf