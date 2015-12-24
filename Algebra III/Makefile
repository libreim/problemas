EXE=$(addsuffix .pdf, $(basename $(wildcard *.md)))

default: $(EXE)

%.pdf: %.md
	pandoc $< -o $@ --filter pandoc-eqnos

%.tex: %.md
	pandoc $< -o $@ -s --filter pandoc-eqnos
