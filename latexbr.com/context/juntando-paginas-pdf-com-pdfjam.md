Juntando páginas PDF com PdfJam
===============================

Juntando páginas PDF com PdfJam
-------------------------------


O [pdfjam] é um programa que junta páginas PDF de vários arquivos transformando num só. O programa roda via terminal, sua sintaxe é:

```
pdfjam arquivo01.pdf arquivo02.pdf arquivo03.pdf -o arquivosaida.pdf
```

Veja alguns exemplos:

```
pdfjam arquivo01.pdf '{},2-' arquivo02.pdf '10,3-6' -o arquivosaida.pdf
```

{} insere uma página em branco.

2- insere as páginas de 2 até o final do documento.

10,3-6 insere a página 10 seguida das páginas de 3 até 6, nesta ordem.

```
pdfjam arquivo01.pdf '2-' arquivo02.pdf '-' --papersize '{16cm,9cm}' -o arquivosaida.pdf
```

'-' insere todas as páginas do documento.

Mais informações em [pdfjam].


#####Rotacionando páginas PDF

Para rotacionar um página PDF digite:

```
pdfjam arquivo01.pdf --angle '180' -o arquivosaida.pdf
```



[pdfjam]:http://manpages.ubuntu.com/manpages/maverick/man1/pdfjam.1.html