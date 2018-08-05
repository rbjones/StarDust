# This makefile is for making a StarDust PDF combining the wiki's of
# the four repositories of the StarDust constellation.
#
# All four project wikis are submodules of this repo.
# The .md files from the wiki repos are converted to .tex files using pandoc.
# A PDF suitable for publication of a book via Createspace is made using
# a top-level tex file (StarDust.tex) which includes the individual tex
# as required.  At present this is a book of four parts, one for each repo
# with a preface specific to the book in the top level file. 
#
# To pull in changes from the submodules:
#
# git submodule update --recursive --remote

MDFILES=
MDFILES+= StarDust.wiki/The-StarDust-Constellation.md
MDFILES+= StarDust.wiki/The-Aims-of-StarDust.md
MDFILES+= StarDust.wiki/Context-for-StarDust.md
MDFILES+= StarDust.wiki/Hybrid-Deductive-Intelligence.md
MDFILES+= StarDust.wiki/Universal-Fulfillment.md
MDFILES+= StarDust.wiki/Philosophical-Fundamentals.md
MDFILES+= StarDust.wiki/Language-Development-and-Knowledge-Representation.md
MDFILES+= StarDust.wiki/Three-Kinds-of-Proposition.md
MDFILES+= StarDust.wiki/The-Architecture-of-StarDust.md
MDFILES+= StarDust.wiki/The-Ambition.md
MDFILES+= StarDust.wiki/The-Cognitive-Cosmos.md
MDFILES+= StarDust.wiki/The-Deductive-Paradigm-Shift.md
MDFILES+= StarDust.wiki/How-Deduction-Trumps-Computation.md
MDFILES+= StarDust.wiki/Formal-Mathematics.md
MDFILES+= StarDust.wiki/Deductive-Cloud.md
MDFILES+= StarDust.wiki/General-Deductive-Intelligence.md
MDFILES+= StarDust.wiki/Deductive-Smart-Contracts.md
MDFILES+= StarDust.wiki/hype-cycles.md
MDFILES+= StarDust.wiki/The-Architecture.md
MDFILES+= StarDust.wiki/The-Strategy.md

MDFILES+= HoLoTruth.wiki/Language-Truth-and-Logic.md
MDFILES+= HoLoTruth.wiki/The-Philosophy.md
MDFILES+= HoLoTruth.wiki/Some-Philosophical-Background.md
MDFILES+= HoLoTruth.wiki/What-Carnap's-Philosophy-was-not.md
MDFILES+= HoLoTruth.wiki/The-Problem-and-the-Method.md
MDFILES+= HoLoTruth.wiki/Preliminary-Discussion.md
MDFILES+= HoLoTruth.wiki/Metaphysics-and-Ontology.md
MDFILES+= HoLoTruth.wiki/The-Architecture.md
MDFILES+= HoLoTruth.wiki/The-Logical-Kernel.md
MDFILES+= HoLoTruth.wiki/Distributed-Theory-Hierarchy.md
MDFILES+= HoLoTruth.wiki/Logical-Contexts.md
MDFILES+= HoLoTruth.wiki/HOL-for-Knowledge-Representation.md
MDFILES+= HoLoTruth.wiki/Language-and-Logic.md
MDFILES+= HoLoTruth.wiki/Strategy-and-Plan.md
MDFILES+= HoLoTruth.wiki/The-Plan.md

MDFILES+= HoLoMod.wiki/Sense,-Model,-Plan,-Action.md

MDFILES+= HoLoVal.wiki/Refining-and-Effecting-Value-Systems.md

LOCMDFILES=$(MDFILES:%=../doc/%)

default:
	@echo "StarDust wikibook makefile"
	@echo "=========================="
	@echo "StarDust.pdf\tmake pdf of wikibook"
	@echo "locmdfiles\tcopy the wiki files to the docs folder for the website"
	@echo "all\tStardust.pdf and locmdfiles"

TEXFILES=$(MDFILES:%.md=%.tex)

$(TEXFILES): %.tex: %.md
	pandoc -f markdown -i "$*.md" -o "$@"	\
		--number-sections        	\
		--latex-engine=xelatex

cleantexs:
	-rm $(TEXFILES)

#StarDust.tex: StarDust.md header.tex includebefore.tex
#	pandoc -f markdown -i StarDust.md -o StarDust.tex -s	\
#		--toc --toc-depth=4 --number-sections        	\
#		--latex-engine=xelatex				\
#		-V documentclass=book	\
#		-V fontsize=10pt	\
#		-V title="{\\bf StarDust}\\\\ \\ \\\\ {\\Large Cosmic Cognitive Architecture}"	\
#		-V subtitle="Cosmic Cognitive Architecture" \
#		-V author="Roger Bishop Jones" \
#		-V geometry:"twoside,paperwidth=5in,paperheight=8in,hmargin={0.75in,0.5in},vmargin={0.5in,0.5in},includehead,includefoot" \
#		-V meta-json="author='Roger Bishop Jones'" \
#		--data-dir=. \
#		-H header.tex \
#		--include-before=includebefore.tex

StarDust.pdf: StarDust.tex texhdfile.tex $(TEXFILES)
	xelatex StarDust
	xelatex StarDust
	xelatex StarDust
	cp StarDust.pdf ../docs

locmdfiles: $(MDFILES)
	rm -rf ../docs/*.wiki
	cp -r *.wiki ../docs
	rm ../docs/*.wiki/.git
	touch locmdfiles

all: StarDust.pdf locmdfiles
