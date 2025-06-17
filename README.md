# Markdown CV Formatting Workflow

[![Render CV](https://github.com/thrly/md-cv/actions/workflows/convert-cv.yml/badge.svg)](https://github.com/thrly/md-cv/actions/workflows/convert-cv.yml)

Keep your markdown CV up to date with version control and various common formats: HTML, PDF, DOCX, and LaTeX. The conversion is handled using GitHub actions with Pandoc via official Docker images.

## Project Structure

```bash
md-cv/
├── .github/
│   └── workflows/
│       └── convert-cv.yml     # GitHub Actions workflow for conversion
├── cv/
│   ├── cv.md                  # Your CV in Markdown format
│   └── templates/
│       ├── cv-template.tex    # LaTeX template
│       ├── cv-template.html   # HTML template
│       ├── cv-template.docx   # DOCX reference
│       └── style.css          # Custom CSS for HTML output
├── outputs/
│   ├── cv.html                # Generated CV in HTML format
│   ├── cv.pdf                 # Generated CV in PDF format
│   ├── cv.docx                # Generated CV in DOCX format
│   └── cv.tex                 # Generated CV in LaTeX format
└── README.md                  # Project docs
```

## How It Works

- On every push to the [cv.md](/cv/cv.md) file or `cv/templates/`, the workflow runs and:
  - Converts `cv/cv.md` to PDF, LaTeX, DOCX, and HTML using Pandoc Docker images.
  - Saves all generated files in the `outputs/` directory.
  - Uploads the `outputs/` directory as a workflow artifact.
  - Commits and pushes the updated `outputs/` directory back to the repository (on GitHub Actions only).

## Getting Started to trigger renders

1. **Fork this repository**
2. **Clone to your local machine**

   ```bash
   git clone https://github.com/yourusername/md-cv.git
   cd md-cv
   ```

3. **Edit Your CV**

   Update `cv/cv.md` with your latest information. You can also edit templates in `cv/templates/`.

4. **Push Changes**

   ```bash
   git add cv/cv.md
   git commit -m "Update CV"
   git push origin main
   ```

5. **Workflow Execution**

   - The workflow triggers automatically on push.
   - You can monitor progress in the "Actions" tab on GitHub.

6. **Accessing Outputs**

   - The latest generated files are always available in the `outputs/` directory in the repository.
   - You can also download them as workflow artifacts from the GitHub Actions run summary.

## Notes

- The workflow uses official Pandoc Docker images for reproducible builds.
- The `outputs/` directory is committed back to the repository automatically (only on GitHub Actions, not when running locally with `act`).

> [!CAUTION]
> If you run the workflow locally with [`act`](https://github.com/nektos/act), the commit/push step is skipped to avoid hangs or errors.

## Requirements

- A GitHub account with Actions enabled.
- No local Pandoc or TeX installation is required; all conversion is handled in the workflow.
