# This makefile is for making a StarDust PDF combining the wiki's of
# the four repositories of the StarDust constellation.
#
# All four project wikis are submodules of this repo.
# A PDF suitable for publication of a book via Createspace is made using
# a top-level tex file (StarDust.tex) which includes the individual .md
# files directly using the LaTeX markdown package.
# Outputs are placed in build/ to keep submodules clean.
#
# To pull in changes from the submodules:
#
# git submodule update --recursive --remote

# List of .md files needed for locmdfiles target
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
MDFILES+= HoLoTruth.wiki/The-Problem-and-The-Method.md
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

OUTPUT_DIR = build
PDF = $(OUTPUT_DIR)/StarDust.pdf

default:
	@echo "StarDust wikibook makefile"
	@echo "=========================="
	@echo "StarDust.pdf\tmake pdf of wikibook"
	@echo "locmdfiles\tcopy the wiki files to the docs folder for the website"
	@echo "all\tStarDust.pdf and locmdfiles"

$(PDF): StarDust.tex sdhead.tex
	mkdir -p $(OUTPUT_DIR)
	lualatex -output-directory=$(OUTPUT_DIR) StarDust
	lualatex -output-directory=$(OUTPUT_DIR) StarDust
	lualatex -output-directory=$(OUTPUT_DIR) StarDust
	cp $(PDF) ../docs

locmdfiles: $(MDFILES)
	rm -rf ../docs/*.wiki
	cp -r *.wiki ../docs
	rm ../docs/*.wiki/.git
	touch locmdfiles

clean:
	rm -rf $(OUTPUT_DIR)/*

all: $(PDF) locmdfiles
