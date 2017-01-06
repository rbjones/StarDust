# This makefile is for making a StarDust PDF combining the wiki's of
# the four repositories of the StarDust constellation.
#
# This is pretty straightforward, and is done by concatenating the
# constituent .md files in the right order, feeding them through
# pandoc to make a tex file and then contatenating that with an
# appropriate beginning and end.
#
# The main task is simply to list the files in the required order.

MDFILES=
MDFILES+= StarDust.wiki/Home.md
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
MDFILES+= HoLoVal.wiki/Refining-and-Effecting-Value-Systems.md
MDFILES+= HoLoMod.wiki/Sense,-Model,-Plan,-Action.md
MDFILES+= HoLoTruth.wiki/Language-Truth-and-Logic.md
MDFILES+= HoLoTruth.wiki/The-Philosophy.md
MDFILES+= HoLoTruth.wiki/Some-Philosophical-Background.md
MDFILES+= HoLoTruth.wiki/What-Carnap?s-Philosophy-was-not.md
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

LOCMDFILES=$(MDFILES:%=../doc/%)

default:
	@echo "StarDust wikibook makefile"
	@echo "=========================="
	@echo "StarDust.pdf\tmake pdf of wikibook"
	@echo "locmdfiles\tcopy the wiki files to the docs folder for the website"


StarDust.md:$(MDFILES) Makefile
	cat $(MDFILES) > StarDust.md

StarDust.tex: StarDust.md
	pandoc -f markdown -i StarDust.md -o StarDust.tex -s	\
		--toc --toc-depth=5 --number-sections        	\
		--latex-engine=xelatex				\
		-V papersize=b5		\
		-V documentclass=book	\
		-V fontsize=12pt

StarDust.pdf: StarDust.tex
	xelatex StarDust
	xelatex StarDust
	xelatex StarDust
	cp StarDust.pdf ../docs

locmdfiles: $(MDFILES)
	rm -rf ../docs/*.wiki
	cp -r *.wiki ../docs
	rm ../docs/*.wiki/.git
	touch locmdfiles
