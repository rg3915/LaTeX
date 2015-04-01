Recortando páginas PDF com PdfCrop ou PDF-Shuffler
==================================================

Recortando páginas PDF com PdfCrop ou PDF-Shuffler
--------------------------------------------------


O [pdfcrop] é um programa que 'recorta' páginas pdf via terminal. Veja sua sintaxe:

```
pdfcrop --margins 'left top right bottom'
```

E um exemplo:

```
pdfcrop --margins ’-10 -50 -10 -40’ --clip exemplo.pdf exemplo-crop.pdf
```

Experimente também o PDF-Shuffler. __Importe__ um arquivo pdf e clique com o botão direito escolhendo a opção __Crop Page(s)__.

![image](http://www.linuxinsider.com/images/article_images/72288_620x580.jpg)

Para finalizar __exporte__ o resultado.




[pdfcrop]:http://manpages.ubuntu.com/manpages/oneiric/en/man1/pdfcrop.1.html