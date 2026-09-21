# McK Work

This repository contains three related engineering-document extraction projects built as exploratory Python and Jupyter Notebook workflows. Together, they investigate how to turn technical drawings, wiring diagrams, tables, symbols, and related PDF content into structured data that can be reviewed or consumed by downstream systems.

## Projects

### 1. Data Extraction Smart Tool

**Location:** [`Data Extraction Smart Tool/`](Data%20Extraction%20Smart%20Tool/)

The main project for extracting structured information from engineering drawings. It is organized by extraction capability and keeps source notebooks, test inputs, and generated outputs together.

Current extraction areas include:

- **Table extraction:** connector tables, pin data, wire details, gauges, colors, and related tabular information.
- **Symbol identification:** legend and symbol recognition from drawing content.
- **Connection extraction:** wires, junctions, endpoints, and connection relationships from harness or schematic-style drawings.
- **Local source experiments:** supporting calculations and processing experiments used during development.

The project has progressed through local testing, migration to a Linux VM, deployment through the McK gateway, and table-detail extraction. Connection-detail extraction is currently in progress.

Useful folders:

```text
Data Extraction Smart Tool/
├── Inputs/
│   ├── Test Inputs/
│   └── ...
├── Outputs/
│   ├── Connection Ext/
│   ├── Symbol Ext/
│   ├── Table Ext/
│   └── Test Outputs/
└── Src/
	├── Connection Extraction/
	├── Symbol Ideintification/
	├── Table Extraction/
	└── Src - Local/
```

> Note: `Symbol Ideintification` is retained with its existing directory spelling.

### 2. PDF Extraction

**Location:** [`PDF extraction/`](PDF%20extraction/)

A set of foundational notebooks for working with PDF drawings and extracted page content. The notebooks cover PDF extraction, spatial understanding, and focused experiments for splitting or processing calculations, legends, and tables.

This folder is useful for testing image and document-processing ideas before incorporating them into the more structured Smart Tool workflows.

### 3. QB Help

**Location:** [`QB Help/`](QB%20Help/)

An independent document-extraction workflow focused on extracting information from QB-related input documents. Multiple implementation versions are preserved so that approaches and results can be compared over time.

The current project notes record:

- single-page extraction completed;
- multi-page extraction completed and producing satisfactory output.

The latest work is under [`QB Help/Src/Version -5 (Cladue)/`](QB%20Help/Src/Version%20-5%20(Cladue)/), with earlier versions retained for reference.

## Repository Layout

```text
.
├── Data Extraction Smart Tool/   # Structured drawing-data extraction
├── PDF extraction/               # PDF and spatial-understanding experiments
├── QB Help/                      # QB document-extraction workflow
├── LICENSE
└── README.md
```

## Working With the Notebooks

These projects are notebook-based prototypes and experiments rather than packaged Python applications. To work with them:

1. Open the relevant project folder in VS Code or JupyterLab.
2. Select a Python environment with the dependencies required by the notebook.
3. Start with the notebook version that matches the desired workflow. Versioned folders are kept to preserve development history and test approaches.
4. Place test documents in the corresponding `Inputs` or notebook-specific test-data folder.
5. Run the notebook cells in order and inspect the generated results in the matching `Outputs` folder when available.

Because dependencies and deployment configuration are not centralized in this repository, each notebook may require its own environment setup. Review the imports and input paths at the top of a notebook before running it.

## Project Status

| Project | Status |
| --- | --- |
| Data Extraction Smart Tool | Table extraction complete; connection-detail extraction in progress |
| PDF extraction | Active research and supporting extraction experiments |
| QB Help | Single-page and multi-page extraction completed |

## Development Notes

- Keep source notebooks, test inputs, and generated outputs in their existing project folders.
- Preserve versioned notebooks when introducing a new approach; create a new version instead of overwriting an earlier experiment.
- Avoid committing sensitive or unnecessarily large source documents and generated artifacts.
- Update the project-specific `Readme.txt` files when milestones or supported workflows change.
