Espaçamento entre linhas
========================

:date: 2014-12-03 23:59
:tags: dicas, pacotes
:category: Dicas
:slug: espacamento-entre-linhas
:author: Regis da Silva
:email: regis.santos.100@gmail.com
:github: rg3915
:summary: Com o pacote ``setspace`` podemos controlar o espaçamento entre linhas para as opções...

Com o pacote `setspace <http://ctan.tche.br/help/Catalogue/entries/setspace.html>`_ podemos controlar o espaçamento entre linhas para as opções, linha simples, 1.5, duplo ou qualquer outra medida definida pelo usuário. Veja um exemplo abaixo.

.. code-block:: latex

	\documentclass[a4paper]{article}
	\usepackage[utf8]{inputenc}
	\usepackage[T1]{fontenc}
	\usepackage[brazil]{babel}
	\usepackage{indentfirst,lipsum}
	\usepackage{setspace} % espacamento entre linhas

	% padrao 1.5 de espacamento entre linhas
	\setstretch{1.5}

	\begin{document}

		\section*{Espaçamento de 1.5}

		\begin{onehalfspace}
			\lipsum[1]
		\end{onehalfspace}

		\section*{Espaçamento simples}

		\begin{singlespace}
			\lipsum[1]
		\end{singlespace}

		\section*{Espaçamento duplo}

		\begin{doublespace}
			\lipsum[1]
		\end{doublespace}

		\section*{Novo espaçamento definido de 2.5}

		\begin{spacing}{2.5}
			\lipsum[1]
		\end{spacing}

		\section*{Espaçamento padrão definido}

		Espaçamento padrão definido por \verb|\setstretch{1.5}|.

		\lipsum[1]

	\end{document}

Baixe o exemplo linki TODO