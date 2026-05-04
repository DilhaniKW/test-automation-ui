# test-automation-ui

Comprehensive UI test automation for image-preview features with screenshot-based visual checks and CI-friendly CSV/HTML reports.

## Overview

`test-automation-ui` is a focused, maintainable UI automation suite for validating image preview and viewer functionality. It provides an organized test harness (Pytest) and helpers to capture deterministic screenshots for visual-regression comparisons, record test outcomes to `execution_results.csv`, and produce human-readable HTML reports suitable for CI pipelines.

## Key features

- End-to-end image-preview tests (open, zoom, pan, format handling)
- Screenshot capture and pixel-level visual regression support
- Test result export to `execution_results.csv` and HTML reports
- Configurable browsers and headless mode for CI
- Reusable fixtures/helpers for setup, teardown, and test data
- Sample `pytest` harness with param-driven cases

## Getting started

1. Create and activate a Python virtual environment (recommended).
2. Install dev dependencies:

```bash
pip install -r requirements.txt
```

3. Run tests with `pytest`:

```bash
pytest -q
```

4. Generate HTML report (example):

```bash
pytest --html=report.html
```

## CI integration

This project is designed to integrate into CI systems such as GitHub Actions or Azure Pipelines. Run tests in headless mode, upload screenshots/artifacts, and include `execution_results.csv` as a test result artifact.

## Contributing

Extend tests under `image_preview_test.py` or add new modules under a `tests/` folder. Follow the fixtures and helper patterns for consistent, stable tests.

---
This repository was prepared to provide a clear starting point for UI image-preview automation.
# Test Automation UI – Assignment 1 Option 2

This project uses **Playwright** (Python) to automate a UI test that verifies the **image preview functionality** of the [PixelsSuite](https://www.pixelssuite.com/) website — specifically the **Image Format Conversion (Convert to PNG)** feature.

---

## Prerequisites

- Python 3.11 or 3.12 — [Download here](https://www.python.org/downloads/)
- Google Chrome — [Download here](https://www.google.com/chrome/) (recommended)
- Visual Studio Code (VS Code) — [Download here](https://code.visualstudio.com/)

---

## Setup Instructions (Using VS Code)

### 1. Extract the ZIP file

Extract the ZIP file to a folder. For example:
```
D:\test_automation_ui
```

### 2. Open the folder in VS Code

- Open VS Code
- Click **File → Open Folder**
- Select the extracted `test_automation_ui` folder

### 3. Open the Terminal in VS Code

- In VS Code, click **Terminal → New Terminal** (or press `` Ctrl+` ``)
- The terminal should open at the bottom of VS Code

### 4. Install dependencies (one-time only)

Run the following commands one by one in the VS Code terminal:

```bash
pip install -U pip
pip install playwright openpyxl
playwright install
```

---

## Running the Test

In the VS Code terminal, run this command:

```bash
python image_preview_test.py --url "https://www.pixelssuite.com/convert-to-png" --slow-mo-ms 2000
```

> A Chrome browser window will open automatically and run the test. Wait for it to finish.

---

## Checking Results

After the script finishes:

1. Open the **`execution_results.csv`** file — it should contain **one data row** (plus the header).
2. Check the **`results`** folder — it should contain a screenshot named `preview_pass.png`.

---

## Test Description

| Field | Value |
|-------|-------|
| Feature Tested | Image Format Conversion (Convert to PNG) |
| Test Type | Positive – Preview Functionality |
| Input | `sample.png` (valid PNG image) |
| Expected Output | Image preview is displayed after upload |
| Tool | Playwright (Python) |
