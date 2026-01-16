# Automated Data Quality Pipeline

Reusable Python pipeline for automated data quality validation, schema checks, and transformation of real-world healthcare and operational datasets.

---

## Project Overview

Real-world datasets, especially in healthcare and public-sector reporting, frequently contain missing values, duplicate records, inconsistent data types, or logical errors that can compromise downstream analysis.

This project implements a **reusable, defensive data quality pipeline** that ingests CSV-based datasets, validates their structure, performs systematic quality checks, and outputs an analysis-ready dataset alongside a structured quality report.

Although demonstrated using healthcare admissions data, the pipeline is **industry-agnostic** and applicable to any operational dataset requiring automated quality validation prior to analysis.

---

## Problem Statement

Data analysts often receive datasets that:

* Contain missing or incomplete records
* Include duplicate rows
* Violate logical constraints (e.g., negative counts)
* Vary slightly between reporting periods

Without automated validation, these issues can lead to unreliable insights and poor business decisions.

This project addresses that challenge by implementing a **single reusable pipeline** that surfaces data quality issues before analysis begins.

---

## Key Objectives

* Automate ingestion of CSV datasets
* Validate required schema and structure
* Detect common data quality issues:

  * Missing values
  * Duplicate records
  * Logical violations
* Produce a clean, analysis-ready output
* Return a transparent quality report for auditability

---

## Pipeline Design

The pipeline is implemented as a reusable function:

```python
run_data_quality_pipeline(csv_path)
```

### High-Level Workflow

1. **Ingestion**

   * Reads CSV input with defensive error handling

2. **Schema Validation**

   * Confirms required columns are present

3. **Data Quality Checks**

   * Missing values per column
   * Duplicate row detection
   * Logical validation of numeric values
   * Data type inspection

4. **Transformation**

   * Reshapes data into a wide, analysis-friendly format

5. **Output**

   * Pipeline execution status
   * Structured data quality report
   * Processed dataset ready for downstream analysis

---

## Design Philosophy

The pipeline is intentionally designed **not to silently modify data**.

* Missing values are reported, not imputed
* Duplicate records are flagged, not dropped
* Logical violations cause pipeline failure
* Data type issues are surfaced as warnings

This mirrors best practices in regulated and data-sensitive environments such as healthcare, finance, and public-sector reporting.

---

## Reusability & Automation

The same pipeline function was executed across multiple datasets without internal code changes, demonstrating:

* Automation
* Reusability
* Scalability across reporting periods

---

## Tools & Technologies

* Python
* Pandas
* Jupyter Notebook

---

## Author

Oluwasemilogo Akinlo
