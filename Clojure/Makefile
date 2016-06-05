# Copyright © 2015-2016 Ekaitz Zarraga <ekaitzzarraga@gmail.com>
# This work is free. You can redistribute it and/or modify it under the
# terms of the Do What The Fuck You Want To Public License, Version 2,
# as published by Sam Hocevar. See http://www.wtfpl.net/ for more details.

# Makefile for easy documentation in HTML and PDF

C 	= pandoc

# Set default to all
.DEFAULT_GOAL := all

# Numbered sections and subsections
FLAGS	= -N

# Add table of contents
FLAGS	+= --toc

# Standalone output
FLAGS	+= -s

# Add some flag shit
#FLAGS	+=



# SPANISH TARGET
#-------------------------------------------------------------------------
TARGET_ES = Clojure-ES.pdf
CONTENTS_ES = $(sort $(wildcard Contents-ES/*.md))

# Add PDF related FLAGS
PDF_FLAGS 	= --latex-engine=xelatex

.PHONY: spanish
spanish: $(TARGET_ES)

$(TARGET_PDF): $(SECTIONS)
	$(C) $(FLAGS) -o $@ $(CONTENTS_ES) $(PDF_FLAGS)


# ALL TARGET
#-------------------------------------------------------------------------
.PHONY: all
all: spanish


# CLEAN TARGET
#-------------------------------------------------------------------------
.PHONY: clean
clean:
	rm -f $(TARGET_ES)
