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
MDFILES+= StarDust.wiki/_Footer.md
MDFILES+= DA-Hol.wiki/Home.md
MDFILES+= DA-Hol.wiki/Deductive-Cloud.md
MDFILES+= DA-Hol.wiki/Deductive-Smart-Contracts.md
MDFILES+= DA-Hol.wiki/Distributed-Theory-Hierarchy.md
MDFILES+= DA-Hol.wiki/Formal-Mathematics.md
MDFILES+= DA-Hol.wiki/General-Deductive-Intelligence.md
MDFILES+= DA-Hol.wiki/HOL-for-Knowledge-Representation.md
MDFILES+= DA-Hol.wiki/How-Deduction-Trumps-Computation.md
MDFILES+= DA-Hol.wiki/Language-and-Logic.md
MDFILES+= DA-Hol.wiki/Logical-Contexts.md
MDFILES+= DA-Hol.wiki/Metaphysics-and-Ontology.md
MDFILES+= DA-Hol.wiki/Preliminary-Discussion.md
MDFILES+= DA-Hol.wiki/Some-Philosophical-Background.md
MDFILES+= DA-Hol.wiki/Strategy-and-Plan.md
MDFILES+= DA-Hol.wiki/The-Ambition.md
MDFILES+= DA-Hol.wiki/The-Architecture.md
#MDFILES+= DA-Hol.wiki/The-DA?Hol-Manifesto.md
MDFILES+= DA-Hol.wiki/The-Deductive-Paradigm-Shift.md
MDFILES+= DA-Hol.wiki/The-Logical-Kernel.md
MDFILES+= DA-Hol.wiki/The-Philosophy.md
MDFILES+= DA-Hol.wiki/The-Plan.md
MDFILES+= DA-Hol.wiki/The-Problem-and-the-Method.md
MDFILES+= DA-Hol.wiki/What-Carnap?s-Philosophy-was-not.md
MDFILES+= DA-Hol.wiki/_Footer.md
MDFILES+= DA-Hol.wiki/_Sidebar.md
MDFILES+= DA-Hol.wiki/full-content-listing.md
MDFILES+= DA-Hol.wiki/hype-cycles.md
MDFILES+= DA-Value.wiki/Home.md
MDFILES+= DA-Value.wiki/The-DA?Value-Manifesto.md

StarDust.md:$(MDFILES)
	cat $(MDFILES) > StarDust.md

StarDust.tex: StarDust.md
	pandoc -f markdown -i StarDust.md -o StarDust.tex -s	\
		--toc --toc-depth=3 --number-sections        	\
		--latex-engine=xelatex				\
		-V papersize=b5		\
		-V documentclass=book	\
		-V fontsize=12pt

StarDust.pdf: StarDust.tex
	xelatex StarDust
