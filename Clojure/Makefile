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
FLAGS	+= --standalone

# SPANISH TARGET
#-------------------------------------------------------------------------
TARGET_ES = Clojure-ES.pdf
CONTENTS_ES = $(sort $(wildcard Contents-ES/*))

# Add PDF related FLAGS
PDF_FLAGS 	= --latex-engine=xelatex

.PHONY: spanish
spanish: $(TARGET_ES)

$(TARGET_ES): $(CONTENTS_ES)
	$(C) \
		$(FLAGS) 			\
		-f markdown			\
		--template=template.latex	\
		-o $@				\
		$(CONTENTS_ES)			\
		--data-dir=.			\
		$(PDF_FLAGS)


# ALL TARGET
#-------------------------------------------------------------------------
.PHONY: all
all: spanish


# CLEAN TARGET
#-------------------------------------------------------------------------
.PHONY: clean
clean:
	rm -f $(TARGET_ES)
