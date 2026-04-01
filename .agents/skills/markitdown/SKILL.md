---
name: markitdown
description: Use this skill when the user asks to parse, perform multi-format document conversion or spatially extract text from an unstructured file (PDF, DOCX, PPTX, XLSX, images, etc.) and convert it into json format.
---

# Markitdown Skill 
Parse unstructured documents (PDF, DOCX, PPTX, XLSX, images, and more) locally with `markitdown` command: fast, lightweight, no cloud dependencies or LLM required.

- 1. **Input**: Take a pdf or docx as input extract the data using  `markitdown` command.
- 2. **Conversion**:Convert the extracted data into json format. 


## Step 0 — Install Markitdown (if needed)

### Verify if `markitdown` is installed:
'
If `markitdown` is not yet installed, install it:

```bash
pip install 'markitdown[all]'
```

-----

## Step 1 — Produce the CLI Command or Script

### Parse a Single File

```bash
markitdown path-to-file.pdf > document.md
#Or use -o to specify the output file:

markitdown path-to-file.pdf -o document.md
#You can also pipe content:

cat path-to-file.pdf | markitdown
```

## Step 3 — Key Options Reference

### OCR Options

| Option | Description |
|--------|-------------|
| (default) | Tesseract.js — zero setup, built-in |
| `--ocr-language fra` | Set OCR language (ISO code) |
| `--ocr-server-url <url>` | Use external HTTP OCR server (EasyOCR, PaddleOCR, custom) |
| `--no-ocr` | Disable OCR entirely |

### Output Options

| Option | Description |
|--------|-------------|
| `--format json` | Structured JSON with bounding boxes |
| `--format text` | Plain text (default) |
| `-o <file>` | Save output to file |

### Performance / Quality Options

| Option | Description |
|--------|-------------|
| `--dpi <n>` | Rendering DPI (default: 150; use 300 for high quality) |
| `--max-pages <n>` | Limit pages parsed |
| `--target-pages <pages>` | Parse specific pages (e.g. `"1-5,10"`) |
| `--no-precise-bbox` | Disable precise bounding boxes (faster) |
| `--skip-diagonal-text` | Ignore rotated/diagonal text |
| `--preserve-small-text` | Keep very small text that would otherwise be dropped |


---

## Supported Input Formats

| Category | Formats |
|----------|---------|
| PDF | `.pdf` |
| Word | `.doc`, `.docx`, `.docm`, `.odt`, `.rtf` |
| PowerPoint | `.ppt`, `.pptx`, `.pptm`, `.odp` |
| Spreadsheets | `.xls`, `.xlsx`, `.xlsm`, `.ods`, `.csv`, `.tsv` |
| Images | `.jpg`, `.jpeg`, `.png`, `.gif`, `.bmp`, `.tiff`, `.webp`, `.svg` |

Markitdown auto-converts these formats to PDF before parsing.
