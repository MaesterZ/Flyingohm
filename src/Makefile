SHELL := /bin/bash
.DEFAULT_GOAL := help

.PHONY: help
## help| Makefile| Prints this help message
help:
	@echo "Usage:"
	@sed -n 's/^##//p' ${MAKEFILE_LIST} | column -t -s '|' |  sed -e 's/^/ /'

.PHONY: init
## init| Python| Create virtual environment
init:
	python3 -m venv .venv

.PHONY: lint
## lint| Python| Run linters
lint:
	flake8
	find -name '*.py' | xargs pylint

.PHONY: format
## format| Python| Run formatter
format:
	find -name '*.py' | xargs black --line-length=140

.PHONY: types
## types| Python| Run types linter
types:
	find -name '*.py' | xargs mypy --ignore-missing-imports
