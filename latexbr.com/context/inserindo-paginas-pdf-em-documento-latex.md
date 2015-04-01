Inserindo páginas PDF em documento LaTeX
========================================

Inserindo páginas PDF em documento LaTeX
----------------------------------------

Com o pacote [pdfpages] é possível inserir páginas PDF existentes em documentos LaTeX dentro do arquivo.tex.

Veja o exemplo abaixo:

```latex
\documentclass[a4paper]{article}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage[brazil]{babel}
\usepackage{pdfpages}

\title{Inserindo páginas PDF em documento \LaTeX}
\date{}

\begin{document}
\maketitle

%inserindo apenas uma página
\includepdf[pages=16]{arquivo01.pdf}

%inserindo algumas páginas: 1 até 7, depois 50 e 57
\includepdf[pages={1-7,50,57}]{arquivo02.pdf}

%inserindo uma página em branco depois da página 1
\includepdf[pages={1,{},2-10}]{arquivo03.pdf}

%inserindo todas as páginas
\includepdf[pages=-]{arquivo04.pdf}

%inserindo múltiplas páginas numa única página
\includepdf[pages={286-291},nup=2x3]{arquivo05.pdf}

%inserindo páginas em landscape
\includepdf[pages=-,landscape]{arquivo06.pdf}

\end{document}
```

![image](http://1.bp.blogspot.com/-HuyGXjXHuA8/UFZlndjBePI/AAAAAAAAAis/Vjg4Pai5j3c/s400/inserindopdf.png)


[pdfpages]:http://www.ctan.org/pkg/pdfpages