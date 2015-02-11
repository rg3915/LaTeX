pdf:
	latexmk -pdf -shell-escape uml02
	latexmk -c
	rm *.pyg
preview:
	subl uml02.tex &
	evince uml02.pdf &
	latexmk -pdf -shell-escape -pvc uml02
view:
	acroread uml02.pdf &