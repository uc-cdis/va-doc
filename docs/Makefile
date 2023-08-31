# Minimal makefile for Sphinx documentation
#

# You can set these variables from the command line, and also
# from the environment for the first two.
SPHINXOPTS    ?=
SPHINXBUILD   ?= sphinx-build
SOURCEDIR     = source
BUILDDIR      = build

# Put it first so that "make" without argument is like "make help".
help:
	@$(SPHINXBUILD) -M help "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

.PHONY: help Makefile copy

# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant as a shortcut for $(SPHINXOPTS).
%: Makefile
	@$(SPHINXBUILD) -M $@ "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

# Set SRC_DIR to the directory containing the files to be copied
SRC_DIR := ./build/html

# Set DEFAULT_DEST_DIR to a default destination directory in case none is provided by the user
DEFAULT_DEST_DIR := ../../gitops-qa/qa-mickey.planx-pla.net/dashboard/Public/documentation

# If DEST_DIR is not provided by the user, use DEFAULT_DEST_DIR
DEST_DIR ?= $(DEFAULT_DEST_DIR)

copy:
	@if [ ! -d "$(DEST_DIR)" ]; then\
		echo "Destination directory $(DEST_DIR) does not exist";\
		exit 1;\
	fi
	@echo "Copying files from $(realpath $(SRC_DIR)) to $(realpath $(DEST_DIR))..."
	rm -rf $(DEST_DIR)/*
	rm -rf $(DEST_DIR)/.[!.]*
	cp -r $(SRC_DIR)/* $(DEST_DIR)
