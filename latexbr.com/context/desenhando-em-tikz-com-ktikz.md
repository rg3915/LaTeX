Desenhando em TikZ com KTikZ
============================

Desenhando em TikZ com KTikZ
----------------------------

Vimos anteriormente que existem alguns programas que fazem [preview em tempo real].

O [KTikZ] também faz um preview em tempo real, e é o programa ideal para produção de figuras TikZ.

#####Instalando QTikZ no Win 7

Existe uma versão para Windows chamada [QTikZ]. Baixe-o e instale-o.

#####Instalando QTikZ no Linux (Ubuntu)

Para Linux existem dois programas: [QTikZ 0.10 binary package for Ubuntu Lucid] e [KTikZ 0.10 binary package for Ubuntu Lucid]. A diferença é que o segundo roda no ambiente KDE. Mas os dois funcionam de forma similar. Baixe o arquivo e execute-o, que ele instalará automaticamente pelo gerenciador de pacotes.

Lembre-se: ele só roda dentro de um único ambiente tikzpicture, e não precisa usar documentclass, nem usepackage (mas ele aceita usetikzlibrary). Digite este exemplo:

```latex
\begin{tikzpicture}[inner sep=0,>=latex]
\node (O) at (0,0) {};
\draw (O) circle (1);
\draw[->] (O) -- node[blue,above,rotate=45] {1cm} (45:1);
\end{tikzpicture}
```

![image](http://4.bp.blogspot.com/_nn5BgloqIug/TT9SGtVcWoI/AAAAAAAAAEs/kf-pj3w4PV0/s400/63188-1.jpg)

Aguardem mais tutoriais sobre TikZ, onde usaremos muito o KTikZ.






[preview em tempo real]:http://latexbr.blogspot.com/2010/12/preview-em-tempo-real.html

[KTikZ]:http://kde-apps.org/content/show.php/ktikz?content=63188

[QTikZ]:http://www.hackenberger.at/blog/ktikz-editor-for-the-tikz-language

[QTikZ 0.10 binary package for Ubuntu Lucid]:http://www.hackenberger.at/blog/ktikz-editor-for-the-tikz-language

[KTikZ 0.10 binary package for Ubuntu Lucid]:http://www.hackenberger.at/blog/ktikz-editor-for-the-tikz-language