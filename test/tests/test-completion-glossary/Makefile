.PHONY: test $(TARGETS)

MYVIM ?= nvim --headless

MAKE := 1
export MAKE

TARGETS := glossaries glossaries-extra

test: $(TARGETS)

glossaries: glossaries.aux
	@nvim --headless -u $@.vim
	@latexmk -C $@.tex &>/dev/null

glossaries-extra:
	@TEXFILE=$@-1.tex nvim --headless -u $@.vim
	@TEXFILE=$@-2.tex nvim --headless -u $@.vim

%.aux: %.tex
	@latexmk $< &>/dev/null
