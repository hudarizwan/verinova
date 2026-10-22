# VeriNova

VeriNova is an AI-powered fact-checking and evidence analysis platform designed to verify claims, assess the credibility of supporting sources, and produce explainable verification reports. It helps users check whether a statement is supported by credible evidence, whether it conflicts with known information, and how confident the system is in its conclusion.

The project combines natural language processing, web retrieval, source reliability scoring, contradiction analysis, and report generation into a single workflow that can run from a terminal or a lightweight browser-based interface.

## What VeriNova does

VeriNova evaluates user input in a structured way:

- Parses and analyzes a claim or news headline
- Extracts relevant keywords, entities, and linguistic signals
- Searches for public evidence online
- Filters and ranks retrieved content by relevance
- Assesses source credibility and evidence strength
- Detects contradictions and unsupported claims
- Produces a verdict, confidence score, and explainable reasoning report
- Stores verification history and generates analytics

## How the system works

The workflow is designed to mirror a practical verification pipeline:

1. Input capture
   - A user enters a claim, question, or news headline.

2. NLP analysis
   - The system normalizes the text, extracts keywords, identifies entities, and analyzes sentence structure.

3. Retrieval
   - It queries public web sources to find supporting or contradictory material.

4. Evidence ranking
   - Retrieved pages are filtered for relevance and quality before being used as evidence.

5. Credibility scoring
   - Sources are evaluated based on reliability indicators such as institutional origin, domain type, and content quality.

6. Verification and reasoning
   - Evidence is compared against the claim, contradictions are checked, and a final verdict is generated.

7. Reporting
   - The final output includes a confidence score, quality metrics, summary, and detailed reasoning that can be reviewed or exported.

## Key features

- Claim verification for user questions and statements
- News verification mode for headlines and article snippets
- Live web search and document retrieval
- Evidence extraction and ranking
- Source credibility analysis
- Contradiction detection and unsupported-statement checks
- Confidence scoring and verdict generation
- Searchable verification history
- Analytics dashboard for trends and summary metrics
- CSV export for stored history
- Full report export for individual fact checks
- NLP pipeline demo and offline evaluation
- Browser UI for quick online use
- Command-line workflow for local execution

## Project structure

- `main.py` — interactive CLI application
- `web_server.py` — lightweight web backend for the browser interface
- `verifier.py` — main fact-checking workflow
- `query_processor.py` — query parsing and NLP preprocessing
- `search_engine.py` — live public web search
- `web_scraper.py` — content retrieval and extraction
- `credibility.py` — source reliability scoring
- `evidence_extractor.py` — evidence relevance and ranking
- `contradiction_detector.py` — contradiction analysis
- `confidence.py` — confidence calculation logic
- `hallucination_detector.py` — unsupported claim detection
- `database.py` — SQLite persistence and history tracking
- `reporting.py` — text reports, analytics, and exports
- `nlp_pipeline.py` — NLP processing pipeline
- `nlp_evaluation.py` — offline evaluation and demo metrics
- `frontend/` — browser interface assets
- `tests/` — project test cases
- `sample_data/` — evaluation data

## Requirements

- Python 3.10+
- Internet access for live fact-checking and public web retrieval
- A writable project directory for SQLite database storage

This project is intentionally built using the Python standard library where possible, which keeps setup simple and portable.

## Quick start

### 1) Clone the project

```bash
git clone https://github.com/hudarizwan/verinova.git
cd verinova
```

### 2) Create a virtual environment (optional but recommended)

```bash
python -m venv .venv
source .venv/bin/activate
# On Windows:
# .venv\Scripts\activate
```

### 3) Run the CLI application

```bash
python main.py
```

You will see a menu with options such as:

- Verify Claim / Ask Question
- Verify News
- View History
- Search History
- Feedback
- Analytics Dashboard
- Export History CSV
- Export Latest Full Report
- NLP Pipeline Demo / Offline Evaluation

### 4) Run the browser interface

```bash
python web_server.py
```

Then open:

```text
http://127.0.0.1:8001
```

## Deployment notes

For hosting platforms or cloud deployment:

- Use `web_server.py` as the app entry point
- Set the `PORT` environment variable if the platform requires it
- Ensure the project folder is writable so SQLite can create and update the local database
- Allow outbound network access so live verification can fetch public evidence

## Features in detail

### Fact verification

The platform takes a claim or question and evaluates whether it is supported by evidence. It can return a verdict such as supported, contradicted, insufficient evidence, or a confidence-based assessment.

### News verification

The system supports headline-based checking for current information, helping assess whether a claim or story is credible and well supported.

### Retrieval and extraction

It retrieves public web content and extracts relevant passages from sources before scoring them for trustworthiness and usefulness.

### Source credibility analysis

The model distinguishes between more trustworthy and less reliable domains using rule-based source assessment signals.

### Contradiction handling

VeriNova checks whether evidence supports or contradicts the original claim, which is key for real-world verification workflows.

### Reporting and analytics

Each verification produces a structured output and analytics can summarize the project's overall evidence trends, popular categories, and historical activity.

### Offline NLP evaluation

A built-in evaluator enables offline testing with labeled example data, making it possible to demonstrate the NLP pipeline even when internet access is unavailable.

## Example usage

```bash
python main.py
```

From the menu, choose:

```text
1. Verify Claim / Ask Question
```

Then enter a statement such as:

```text
The Earth orbits the Sun once every 24 hours.
```

The system will process the claim, retrieve evidence, score sources, and generate a structured report.

## Testing

```bash
python -m unittest discover tests
```

## Notes

- Live verification depends on public web access and the current state of online sources.
- Some searches may be limited by network conditions or site policy.
- The platform is designed to fail gracefully and report insufficient data when evidence is limited rather than guessing.

## Summary

VeriNova is a practical fact-checking platform for claim verification, evidence analysis, and explainable AI-style reporting. It is built to feel like a usable product rather than a classroom-only demo, with a working CLI, browser interface, retrieval pipeline, reporting layer, and evaluation workflow all integrated into one system.
