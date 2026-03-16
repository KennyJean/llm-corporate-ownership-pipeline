# LLM-Based Corporate Ownership Data Pipeline

An automated **LLM-driven data extraction pipeline** designed to support applied academic research on corporate ownership structures.

The system uses large language models to recursively query and extract structured corporate ownership information, enabling researchers to construct deeper corporate relationship datasets from publicly available sources.

The pipeline integrates multiple LLM providers, supports bilingual queries, and standardizes structured outputs to create reproducible datasets for downstream analysis.

---

# Overview

Many academic research projects require gathering structured corporate ownership data across large sets of firms. Manually collecting this information is time-consuming and difficult to scale.

This project implements an automated pipeline that:

- queries LLMs for corporate ownership information  
- recursively traces parent company relationships  
- standardizes outputs into structured JSON  
- caches results to minimize redundant API calls  
- produces analysis-ready datasets in Excel/CSV format  

The pipeline was designed to support large-scale corporate data collection workflows while ensuring reproducibility and efficient token usage.

---

# Key Features

### Recursive Ownership Tracing

The pipeline automatically detects parent companies in responses and recursively queries for additional ownership layers, enabling deeper exploration of corporate hierarchies.

### Multi-LLM Integration

The system supports parallel execution across multiple LLM providers, enabling comparative experimentation and improved reliability.

### Token-Efficient Query Design

Queries were optimized to minimize input/output token usage through structured prompts and standardized output formats.

### Caching System

A caching layer stores previous query results, preventing repeated token consumption for previously processed entities.

### Structured Output Schema

All LLM responses are normalized into a consistent JSON schema, ensuring outputs remain comparable across models and runs.

### Bilingual Query Support

Queries can be executed in both English and Chinese to improve extraction reliability across multilingual sources.

---
## Pipeline Architecture

```text
Input Companies
      │
      ▼
LLM Query Engine
(OpenAI / DeepSeek)
      │
      ▼
Structured Response Parsing
      │
      ▼
Recursive Parent Company Query
      │
      ▼
Caching Layer
      │
      ▼
Standardized JSON Output
      │
      ▼
Excel / CSV Export
```


---

# Output

The pipeline produces structured datasets containing corporate ownership information such as:

- company name  
- parent company  
- ownership relationships  
- metadata from the query run  

Outputs are automatically exported into analysis-ready formats including:

- CSV  
- Excel  
- JSON  

Each run includes metadata such as timestamps and version identifiers to support reproducible research workflows.

---

# Implementation Highlights

- Python-based modular pipeline  
- OpenAI and DeepSeek API integration  
- recursive querying logic for ownership tracing  
- caching system to reduce token consumption  
- standardized JSON response schemas  
- automated dataset export with metadata and versioning  

---

# Contributions

This project was developed collaboratively as part of an applied academic research effort.

### Albert Wu

- Designed the primary pipeline architecture  
- Implemented the core ChatGPT-based querying system  
- Developed the main data extraction workflow  
- Led the final unified implementation of the pipeline  

### Kenny Gao

- Developed an alternative DeepSeek-based pipeline during the exploration phase  
- Contributed to query optimization, caching logic, and structured output design  
- Implemented the **single-run execution system**, allowing the pipeline to run all parameter configurations in one execution rather than requiring multiple manual runs  
- Contributed to bilingual query support and schema standardization  

The final pipeline represents a merged implementation incorporating elements from both approaches.

---

# Data Availability

The full dataset used in the associated academic research project is not included in this repository.

To protect research integrity and comply with project constraints, only the pipeline code and example schemas are provided.

---

# Technologies Used

- Python  
- OpenAI API  
- DeepSeek API  
- JSON Schema  
- Pandas  
- Excel / CSV data export  

---

# Potential Applications

Although developed for academic research, this pipeline architecture can be adapted for:

- corporate ownership mapping  
- economic research data collection  
- automated knowledge extraction  
- large-scale corporate network analysis  
- multilingual LLM data pipelines  
