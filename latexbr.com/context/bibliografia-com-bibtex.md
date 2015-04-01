Bibliografia com BibTEX
-----------------------

##Bibliografia com BibTEX
Para usar bibliografia no LaTeX precisamos de um arquivo com o nome refs.bib, por exemplo. Veja um exemplo do conteúdo deste arquivo:

@book{knuth,
  title={The texbook},
  author={Knuth, D.E. and Bibby, D. and Makai, I.},
  volume={1993},
  year={1986},
  publisher={Addison-Wesley}
}
@misc{lamport,
  title={Document Preparation System},
  author={Lamport, L. and LaTEX, A.},
  year={1994},
  publisher={Addison-Wesley}
}


##Usando BibTeX
Para usar a BibTeX digite no final do documento, antes de \end{document}.
```latex
\bibliographystyle{abbrv}
\bibliography{refs}
```

Um documento mínimo seria

```latex
\documentclass[a4paper]{article}
\usepackage{lipsum}
\begin{document}
\lipsum[1] %texto
\cite{knuth} %citacao
% estilo da bibliografia
\bibliographystyle{abbrv}
% chamando o arquivo refs.bib
\bibliography{refs}
\end{document}
```

Adicionando itens a bibliografia
Pesquise as referências em Google Acadêmicos. Clique em Configurações (lado superior direito da tela) e marque ’Mostre links para importar citações para o BibTEX’.

![image](http://4.bp.blogspot.com/-8Ywch6-Usu0/UE1DwMd9E-I/AAAAAAAAAh4/R-qEdRc5_R8/s400/google_academicos01.png)

![image](http://2.bp.blogspot.com/-uLIoeoWtpBA/UE1DyfHeIpI/AAAAAAAAAiA/LW0yq9twfsk/s400/google_academicos02.png)

A partir dai pesquise a referência e clique em ’Importe para o BibTEX’.

![image](http://1.bp.blogspot.com/-jvd-TT9bv_s/UE1D5a9cD0I/AAAAAAAAAiI/UgrfcLSc6yQ/s400/google_academicos03.png)

Copie a referência no seu arquivo refs.bib.

![image](http://4.bp.blogspot.com/-oztRK8OR0B4/UE1D--u8qFI/AAAAAAAAAiQ/qR5WOBJOm3Y/s400/google_academicos04.png)

É necessário que a referência seja citada no documento, para isso digite
\cite{}. Exemplo, \cite{knuth}. Veja em refs.bib algumas referências.

Para compilar com referência abra o terminal e digite:
```
pdflatex exemplo
bibtex exemplo
pdflatex exemplo
pdflatex exemplo
```
