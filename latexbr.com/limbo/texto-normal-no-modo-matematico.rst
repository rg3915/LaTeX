Texto normal no modo matemático
===============================

:date: 2014-12-03 23:59
:tags: dicas, matemática
:category: Dicas, Matemática
:slug: texto-normal-no-modo-matematico
:author: Regis da Silva
:email: regis.santos.100@gmail.com
:github: rg3915
:summary: Para escrever um texto no modo matemático é necessário usar o comando...

Para escrever um texto no modo matemático é necessário usar o comando ``$\textrm{texto normal}$``.

Ou usando o pacote `amsmath <http://ctan.tche.br/help/Catalogue/entries/amsmath.html>`_ .

.. code-block:: latex

	\usepackage{amsmath}
	\begin{document}
		$\text{texto normal}$
	\end{document}

Veja a diferença entre um texto no modo matemático e no modo normal.

.. code-block:: latex

	\documentclass[a4paper]{article}
	\usepackage{amsmath}
	\begin{document}
		\begin{align*}
			fra\c c\~ao &= \frac{numerador}{denominador}\\
			&\\
			\text{fra\c c\~ao} &= \frac{\text{numerador}}{\text{denominador}}
		\end{align*}
	\end{document}


image TODO

Um outro exemplo interessante é

.. code-block:: latex

	\documentclass[a4paper]{article}
	\usepackage{amsmath}
	\begin{document}
		\[
		f(x) = 
		\begin{cases}
			0 & \text{se $x=0$}\\ REVER
			\frac{1}{x} & \text{caso contr\'ario}
		\end{cases}
		\]
	\end{document}