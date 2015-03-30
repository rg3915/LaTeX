Preview em tempo real
=====================

Com o [Texmaker 2.1][] é possível compilar e visualizar em tempo real. Baixe Texmaker [aqui][] em seguida faça uma configuração em 

Opções, Configurar TexMaker e em PdfLaTeX digite

```
pdflatex -synctex=1 -interaction=nonstopmode %.tex
```

O [KTikZ][] também faz um preview em tempo real. É um programa ideal para a produção de figuras com TikZ. Mas atenção: somente para figuras com TikZ dentro do ambiente tikzpicture.