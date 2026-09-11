# Biomedical-Research-Bank

Compiling my research from various new innovations in the biomedical/computational biology industry.

## Structure

```
research/
├── topics/      # research organized by topic (e.g. gene therapy, CRISPR delivery)
├── companies/    # research organized by company
└── products/     # research organized by product

linkedinposts/
├── topics/
├── companies/
└── products/
```

Subfolders within `topics/`, `companies/`, and `products/` are created as content accumulates (e.g. `research/topics/gene-therapy/`).

## File conventions

- **Filename:** `YYYY-MM-DD-title-slug.md` — date is when the item was logged, not necessarily its publish date.
- **Format:** every file is Markdown, with a short header:

  ```markdown
  # Title

  **Date logged:** YYYY-MM-DD HH:MM
  **Category:** research/topics | research/companies | research/products | linkedinposts/...
  **Source:** (URL or original filename, if given)

  ---

  (formatted content)
  ```

- Pasted text is formatted into clean Markdown; PDFs have their text extracted and converted to the same format.
