# EHR Analysis in MIMIC-III  
SQL Exposure–Outcome Analysis
---

## Project Overview

This project analyzes electronic health record (EHR) data from the MIMIC-III database.

SQL-based exposure–outcome analysis using microbiology and diagnosis data  

No patient-level data is included in this repository.

---

## Data Source

MIMIC-III v1.4 critical care database  
Credentialed access via PhysioNet is required.

All analyses were conducted on structured and unstructured EHR tables within MIMIC-III.

---

## Exposure to Microorganism vs Primary Diagnosis

## Objective

To assess the association between exposure to specific microorganisms and a primary diagnosis.

---

## Cohort Definition

- Only **primary diagnoses** were considered.
- Only one microbiology test per admission was considered.
- Admissions were treated as independent observations.

---

## SQL Analysis

The analysis joins microbiology events with diagnosis codes and computes:

- `LONG_TITLE` (diagnosis description)
- `ORG_NAME` (microorganism name)
- `N_DIAG` (number of admissions with diagnosis)
- `N_TESTED` (number of admissions tested for the microorganism)
- `N_EXPOSED` (number of admissions exposed)
- `N_BOTH` (diagnosis + exposure)
- `ODDS_RATIO`

The odds ratio quantifies the association between microorganism exposure and the primary diagnosis.

---

## Interpretation

The odds ratio is interpreted in epidemiological terms:

- OR > 1: positive association  
- OR < 1: negative association  
- OR ≈ 1: no association  

The analysis is purely SQL-based and does not involve predictive modeling.

---

## Methods Used

- SQL cohort construction
- Odds ratio computation

---

## Skills Demonstrated

- Clinical cohort definition in SQL
- Epidemiological association analysis
- Odds ratio interpretation
- Handling structured and unstructured EHR data

---

## Notes

This repository contains only code and documentation.  
No identifiable patient information is shared.
