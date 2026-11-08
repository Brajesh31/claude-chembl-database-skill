# Chembl Database

"Query ChEMBL's bioactive molecules and drug discovery data. Search compounds by structure/properties, retrieve bioactivity data (IC50, Ki), find inhibitors, perform SAR studies, for medicinal chemistry."

## Overview

This repository contains the original AITMPL skill instructions and its published companion resources.

## Installation

```bash
git clone https://github.com/Brajesh31/claude-chembl-database-skill.git ~/.claude/skills/chembl-database
```

On Windows, use `%USERPROFILE%\.claude\skills\chembl-database` as the destination.

## Usage

Claude Code can load this skill when a request matches its description. Invoke directly with `/chembl-database` when appropriate.

## Repository structure

```text
chembl-database/
├── SKILL.md
├── references/api_reference.md
├── scripts/example_queries.py
├── README.md
└── LICENSE
```

## Runtime requirements

- Python 3 for included Python scripts
- Check any API credentials, service configuration, and Python package requirements before using examples.
- Scripts and tests have not been executed as part of this import.
