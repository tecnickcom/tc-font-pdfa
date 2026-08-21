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

### Glyph naming

Glyph names in the `.pfb` encoding vectors and CharStrings dictionaries, and in the `.afm` metrics, follow the Adobe Glyph List, so that `/Encoding /WinAnsiEncoding` resolves every code the fonts define.

GNU FreeFont uses three pre-AGL names. Regenerating any of the 12 text fonts requires renaming them in the encoding vector and the CharStrings dictionary of the `.pfb`, and in the `N` and `KPX` records of the `.afm`:

| FreeFont name | AGL name | WinAnsi code |
| --- | --- | --- |
| `ssharp` | `germandbls` | 223 |
| `micro` | `mu` | 181 |
| `middot` | `periodcentered` | 183 |

`PDFASymbol` and `PDFAZapfDingbats` are excluded: they declare FontSpecific encoding and are consumed through their built-in encoding.

### Symbol coverage

`PDFASymbol` carries the Adobe Symbol extensible delimiter pieces at codes 230-239, 244 and
246-254, taken from FreeSerif at U+239B-U+23AE, plus `Euro` at 160. FontForge's built-in Symbol
re-encoding does not reach that block, so a regeneration has to add them explicitly.

Codes 226-228 (`registersans`, `copyrightsans`, `trademarksans`) reuse the regular `®`, `©` and `™`
outlines, since FreeSerif has no sans-serif variants. Codes 96 `radicalex`, 189 `arrowvertex` and
190 `arrowhorizex` stay unencoded: they are Adobe private use area glyphs with no FreeSerif
equivalent.

---

## Packaging

Distributed as source assets via Git and Composer.
