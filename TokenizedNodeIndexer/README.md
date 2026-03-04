# Tokenized Node Indexer

A lightweight Python preprocessing module for building structured, tokenized document nodes from HTML archives.

This tool is designed as a foundational layer for semantic analysis systems, digital archive exploration, and research-oriented text indexing pipelines.

## What It Does

The script recursively scans a folder containing HTML files and converts each document into a structured `Node` object with extracted text tokens and metadata.

Each node can later be used for:

* semantic search
* similarity matching
* clustering
* highlighting engines
* OCR post-processing workflows

## Core Features

* Recursive HTML file discovery
* Robust text extraction with encoding fallback
* Normalized tokenization (lowercase, word-only)
* Structured node-based data model
* Minimal dependencies and clear architecture

## Node Model

Each document is represented as a `Node` with the following fields:

* `id` — document identifier (derived from filename)
* `language` — list of supported or detected languages
* `date` — optional document date
* `keywords` — optional curated keywords
* `token_set` — unique set of normalized word tokens
* `path` — full filesystem path to the source file

## How It Works

1. Recursively locate all `.html` files in a given folder
2. Extract visible text using BeautifulSoup
3. Normalize and tokenize the text content
4. Build a list of structured `Node` objects

## Usage

Edit the folder path in the `__main__` section:

```python
folder = r"PATH_TO_YOUR_HTML_ARCHIVE"
```

Then run:

```bash
python build_nodes.py
```

The script will output:

* number of processed HTML files
* number of created nodes
* a sample of extracted tokens

## Intended Scope

This module is **not an end-user application**.
It is intended to be embedded as a component within larger systems, such as:

* digital archive platforms
* semantic indexing engines
* research data pipelines

## License

This software is provided under a commercial license.
See `LICENSE.txt` for full terms and conditions.
