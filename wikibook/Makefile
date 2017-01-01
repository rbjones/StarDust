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
MDFILES+= DA-Value.wiki/Refining-and-Effecting-Value-Systems.md
MDFILES+= SensAct.wiki/Sense,-Model,-Plan,-Action.md
MDFILES+= DA-Hol.wiki/Language-Truth-and-Logic.md
MDFILES+= DA-Hol.wiki/The-Philosophy.md
MDFILES+= DA-Hol.wiki/Some-Philosophical-Background.md
MDFILES+= DA-Hol.wiki/What-Carnap?s-Philosophy-was-not.md
MDFILES+= DA-Hol.wiki/The-Problem-and-the-Method.md
MDFILES+= DA-Hol.wiki/Preliminary-Discussion.md
MDFILES+= DA-Hol.wiki/Metaphysics-and-Ontology.md
MDFILES+= DA-Hol.wiki/The-Architecture.md
MDFILES+= DA-Hol.wiki/The-Logical-Kernel.md
MDFILES+= DA-Hol.wiki/Distributed-Theory-Hierarchy.md
MDFILES+= DA-Hol.wiki/Logical-Contexts.md
MDFILES+= DA-Hol.wiki/HOL-for-Knowledge-Representation.md
MDFILES+= DA-Hol.wiki/Language-and-Logic.md
MDFILES+= DA-Hol.wiki/Strategy-and-Plan.md
MDFILES+= DA-Hol.wiki/The-Plan.md

LOCMDFILES=$(MDFILES:%=../doc/%)

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
	cp -r *.wiki ../docs
	rm ../docs/*.wiki/.git
	touch locmdfiles
