#  MHier-RAG: Multi-Modal RAG for Visual-Rich Document Question-Answering via Hierarchical and Multi-Granularity Reasoning

## Introduction

This is the source code of "MHier-RAG: Multi-Modal RAG for Visual-Rich Document Question-Answering via Hierarchical and Multi-Granularity Reasoning".

This manuscript has been submitted to ICIC 2026.

## Requirements

```linux
pip install -e . -r requirements.txt
```

## Description

- pipeline.py: main program

- pdf_parsing.py: document parsing

  Pdf documents can be converted into jsons. These jsons store raw output of docling and contain a lot of metadata.

- parsed_reports_merging.py: data processing

  Jsons from the previous step can be converted into much simpler jsons, that is a list of pages.

- text_splitter.py: text splitting

  Parsed documents can be split into flattened in-page chunks and topological cross-page chunks, that are used for the construction of hierarchical index.

- ingestion.py: vectorization

  Vector databases can be created from the chunked reports.

- questions_processing.py: process questions and answers

- retrieval.py: multi-granularity retrieval with page-level parent page retrieval and document-level summary retrieval

- reranking.py: llm-based reranking for parent page

- prompts.py: prompt setting

- api_request.py: api setting

- raptor/: summary retrieval with topological cross-page index

- evaluation_mmlongbench/: evaluate metrics for MMLongBench-Doc

- evaluation_longdocurl/: evaluate metrics for LongDocURL

- results_qa/: our experimental results of Doc-QA tasks on MMLongBench-Doc and LongDocURL datasets

## Data

Public data can be downloaded from MMLongBench-Doc and LongDocURL.

## Usage

You can run any part of pipeline  in `pipeline.py` and executing:

```python
python pipeline.py

```

