# claude-chembl-database-skill

A Claude Code skill for querying bioactive molecule, target, and activity data in the ChEMBL database.

## Overview

ChEMBL is a structured resource for bioactive molecules and their relationships with biological targets. This skill helps researchers and developers retrieve compound records, target information, measured activity values, and related drug-discovery data for exploratory analysis.

It supports medicinal chemistry and cheminformatics workflows such as compound search, activity filtering, target exploration, and structure-based discovery.

## Main Capabilities

- Search compounds by name or identifier.
- Retrieve compound properties and structural information.
- Find biological targets and target metadata.
- Query bioactivity measurements such as IC50, Ki, and EC50.
- Explore compound-target relationships.
- Filter activity records by assay and measurement criteria.
- Perform similarity and substructure search workflows where supported.
- Prepare data for structure-activity relationship (SAR) analysis.
- Export query results for downstream analysis.

## Installation

Install the Python client:

```bash
python -m pip install chembl_webresource_client
```

Install the skill:

```bash
git clone https://github.com/Brajesh31/claude-chembl-database-skill.git ~/.claude/skills/chembl-database
```

## Usage

Invoke the skill for compound or bioactivity research:

```text
/chembl-database
```

Provide the compound name, target identifier, structure, activity type, or research question. Specify units and thresholds when filtering measurements.

## Example Query

```python
from chembl_webresource_client.new_client import new_client

molecule = new_client.molecule
results = molecule.filter(pref_name__icontains="aspirin").only(
    ["molecule_chembl_id", "pref_name"]
)

for item in results:
    print(item["molecule_chembl_id"], item["pref_name"])
```

Use the installed client version's supported query fields and validate the returned records before relying on them.

## Typical Research Workflow

1. Define the compound, target, or biological question.
2. Search for candidate records.
3. Confirm identifiers and record types.
4. Retrieve relevant activity measurements.
5. Filter by assay context, units, and data quality.
6. Compare compounds using consistent criteria.
7. Export the resulting dataset with query parameters.
8. Interpret the findings in the context of experimental evidence.

## Reference Guide

| File | Purpose |
|---|---|
| `references/api_reference.md` | Query operations and data structures |
| `scripts/example_queries.py` | Example query workflows |

## Data Interpretation

Bioactivity values are meaningful only in context. Check the assay type, target organism, target confidence, measurement units, relation operators, and assay conditions. Do not compare values from incompatible experiments as if they were directly equivalent.

A database record is not, by itself, proof of clinical efficacy or safety. Treat retrieved data as research evidence that requires scientific interpretation.

## Repository Contents

- `SKILL.md`: Main skill instructions.
- `references/api_reference.md`: API usage guidance.
- `scripts/example_queries.py`: Example database queries.
- `README.md`: Installation and research workflow.

## Reproducibility Checklist

- Record the query terms and filters.
- Preserve stable compound and target identifiers.
- Retain assay metadata and measurement units.
- Note the retrieval date and client version.
- Keep raw query results before applying downstream filters.
- Document exclusions and normalization decisions.
