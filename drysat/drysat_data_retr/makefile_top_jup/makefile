.ONESHELL:
SHELL = /bin/bash
.PHONY: help setup clean

REPO_URL = https://github.com/julinke/drysat_ascat_retr.git
REPO_NAME = drysat_ascat_retr
GIT_BRANCH = main
ROOT = $(HOME)/$(REPO_NAME)

help:
	@echo "Top-level Makefile to clone and set up the Jupyter environment"
	@echo ""
	@echo "Usage:"
	@echo "  make setup  - Clone repo and install environment + kernel"
	@echo "  make clean  - Remove repo, environment, and kernel"

setup:
	if [ ! -d "$(ROOT)" ]; then \
		git clone --branch $(GIT_BRANCH) $(REPO_URL) $(ROOT); \
	else \
		echo "$(ROOT) already exists, skipping clone."; \
	fi
	if [ -f "$(ROOT)/Makefile" ]; then \
		cd $(ROOT) && make kernel || echo "make kernel failed (but repo cloned)."; \
	else \
		echo "Makefile not found in repo, skipping kernel setup."; \
	fi
	@echo "Setup complete."

clean:
	if [ -d "$(ROOT)" ]; then \
		cd $(ROOT) && make teardown || echo "make teardown failed or not present."; \
		rm -rf $(ROOT); \
	else \
		echo "$(ROOT) not found. Nothing to clean."; \
	fi
	@echo "Cleanup complete."

