# tc-font-pdfa

> Type1 core fonts for PDF/A workflows.

[![License](https://img.shields.io/badge/license-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0.en.html)

[![Sponsor on GitHub](https://img.shields.io/badge/sponsor-github-EA4AAA.svg?logo=githubsponsors&logoColor=white)](https://github.com/sponsors/tecnickcom)

> 💖 Part of the [tc-lib-pdf / TCPDF](https://github.com/tecnickcom/tc-lib-pdf) ecosystem (100M+ installs). [Sponsor its maintenance →](https://github.com/sponsors/tecnickcom)

---

## Overview

`tc-font-pdfa` contains 14 Type1 PDF core font files generated from GNU FreeFont to support PDF/A-compatible embedding scenarios.

This package targets compliance-oriented workflows where predictable, embeddable base fonts are required for archival documents. By shipping generated assets in a dedicated repository, PDF toolchains can keep runtime dependencies lightweight while preserving consistent rendering across platforms.

---

## Features

### Core Font Set
- Courier, Helvetica, Times (regular/bold/italic variants)
- Symbol and ZapfDingbats support
- Binary Type1 (`.pfb`) and metrics (`.afm`) assets

### PDF/A-Oriented Distribution
- Deterministic file naming for automation
- Suitable for embedding in PDF/A production pipelines
- Includes conversion notes and provenance details

---

## Requirements

- No runtime PHP requirements
- A PDF engine or conversion tool that consumes Type1 assets

---

## Installation

Install with Composer to make assets available in vendor paths:

```bash
composer require font/pdfa
```

---

## Quick Start

Use files from the `pfb/` and `afm/` directories in your PDF/font import workflow.

```text
afm/
pfb/
```

---

## Development

This project is asset-centric. Typical contributions include regenerating fonts, validating metadata, and documenting conversion steps.

---

## Packaging

Distributed as source assets via Git and Composer.
