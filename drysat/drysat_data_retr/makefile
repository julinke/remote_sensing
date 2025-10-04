.ONESHELL:
SHELL = /bin/bash
.PHONY: help environment kernel teardown clean

ENV_NAME = drysat_ascat_retrieval
DISPLAY_NAME = python (drysat_ascat_retrieval)

CONDA_BASE = $(shell conda info --base)
ACTIVATE = source $(CONDA_BASE)/etc/profile.d/conda.sh && conda activate $(ENV_NAME)

help:
	@echo "Repo Makefile for setting up a single Conda env + Jupyter kernel"
	@echo ""
	@echo "Usage:"
	@echo "  make environment  - Create Conda environment from env.yml"
	@echo "  make kernel       - Create Conda env and install Jupyter kernel"
	@echo "  make teardown     - Remove env and kernel"
	@echo "  make clean        - Remove temporary files"

environment:
	conda env create -n $(ENV_NAME) -f env.yml || \
	conda env update -n $(ENV_NAME) -f env.yml

kernel: environment
	$(ACTIVATE) && \
	python -m ipykernel install --user --name $(ENV_NAME) --display-name "$(DISPLAY_NAME)"

teardown:
	@echo "Removing Conda env and Jupyter kernel..."
	-conda env remove -n $(ENV_NAME) -y
	-jupyter kernelspec uninstall -y $(ENV_NAME)

clean:
	find . -type d -name ".ipynb_checkpoints" -exec rm -rf {} +
