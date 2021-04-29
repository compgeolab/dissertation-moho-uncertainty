# Generate supplementary material for the dissertation:
# * a diary from the git log
# * a zip archive of the repository

# CHANGE THIS TO YOUR NAME! It must match what you configured in git.
AUTHOR = AidanHernaman

# Folder where output will be placed
OUTDIR = output
DIARY_SRC = diary.tex
DIARY_PDF = $(patsubst %.tex, %.pdf, $(DIARY_SRC))
LOG_FORMAT = {%ai}%n%n%B%n
AUX_TEX = diary_entries.tex diary_author.tex
ARCHIVE = dissertation-archive.zip
LATEX_COMPILER = latexmk -pdf -outdir=$(OUTDIR)


.PHONY: diary all clean archive


all: diary archive

clean:
	rm -rvf $(OUTDIR) $(AUX_TEX)

archive: $(OUTDIR)/$(ARCHIVE)

diary: $(OUTDIR)/$(DIARY_PDF)

$(OUTDIR)/$(ARCHIVE):
	mkdir -p $(OUTDIR);
	cd .. && git archive --format zip --output supplements/$@ HEAD

$(OUTDIR)/$(DIARY_PDF): $(DIARY_SRC) $(AUX_TEX)
	$(LATEX_COMPILER) $<

$(OUTDIR)/git_log.txt:
	mkdir -p $(OUTDIR);
	git log --pretty=format:"$(LOG_FORMAT)" --author="$(AUTHOR)" --reverse > $@;

diary_entries.tex: $(OUTDIR)/git_log.txt
	# Remove some Markdown syntax from the file and clean it up
	cat $< | \
	sed -E "s/[\\](.*)/\\\\texttt\{\\\\textbackslash\{\}\1\}/g" | \
	sed "s/ (#\([0-9]\+\))//g" | \
	sed "s/\r//g" | \
	sed -E "s/\[([^]]*)\]\(([^)]*)\)/\\\\href\{\2\}\{\1\}/g" | \
	sed "s/&/and/g" | \
	sed "s/%/\\\\%/g" | \
	sed "s/\* //g" | \
	sed "s/[_]/\\\\textunderscore\{\}/g" | \
	cat	> $@;

diary_author.tex:
	echo "\newcommand{\Name}{$(AUTHOR)}" > $@
