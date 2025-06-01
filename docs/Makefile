BUILDDIR=build
FILENAME=freepbx

pdf:
	mkdir -p $(BUILDDIR)  # Creates the BUILDDIR if it doesn't already exist.
	pandoc $(FILENAME).md \
		--citeproc \
		--from=markdown+tex_math_single_backslash+tex_math_dollars+raw_tex \
		--to=latex \
		--output=$(BUILDDIR)/$(FILENAME).pdf \
		--pdf-engine=xelatex \
		--variable mainfont="DejaVu Serif" \
		--variable monofont="DejaVu Sans Mono" \
		--variable geometry:top=2cm,left=1cm,right=1cm,bottom=1cm \
		--bibliography=/home/kk/Markdown-Templates/documents/bibliography.bib

html:
	mkdir -p $(BUILDDIR)
	pandoc $(FILENAME).md \
		--citeproc \
		--from=markdown+tex_math_single_backslash+tex_math_dollars \
		--to=html5 \
		--output=$(BUILDDIR)/$(FILENAME).html \
		--mathjax \
		--embed-resources --standalone \
		--css=style.css
		--bibliography=bibliography.bib

epub:
	mkdir -p $(BUILDDIR)
	pandoc $(FILENAME).md \
		--citeproc \
		--from=markdown+tex_math_single_backslash+tex_math_dollars \
		--to=epub \
		--output=$(BUILDDIR)/$(FILENAME).epub \
		--epub-cover-image=<cover-image> \
		--toc \
		--bibliography=bibliography.bib
