# CV Conversion Workflow

This project provides a GitHub Actions workflow to convert a CV written in Markdown format into various output formats, including HTML, PDF, DOCX, and LaTeX. The conversion is handled using Pandoc, a powerful document converter.

## Project Structure

```text
cv-conversion-workflow
├── .github
│   └── workflows
│       └── convert-cv.yml  # GitHub Actions workflow for conversion
├── cv
│   └── cv.md                # Source CV in Markdown format
├── outputs
│   ├── cv.html              # Generated CV in HTML format
│   ├── cv.pdf               # Generated CV in PDF format
│   ├── cv.docx              # Generated CV in DOCX format
│   └── cv.tex               # Generated CV in LaTeX format
└── README.md                # Project documentation
```

## Getting Started

To use this workflow, follow these steps:

1. **Clone the Repository**: Clone this repository to your local machine.

   ```bash
   git clone https://github.com/yourusername/cv-conversion-workflow.git
   cd cv-conversion-workflow
   ```

2. **Modify Your CV**: Edit the `cv/cv.md` file to update your CV content as needed.

3. **Push Changes**: Commit and push your changes to the GitHub repository.

   ```bash
   git add cv/cv.md
   git commit -m "Update CV"
   git push origin main
   ```

4. **Trigger the Workflow**: The workflow will automatically trigger on push events to the main branch. You can check the progress in the "Actions" tab of your GitHub repository.

5. **Access Outputs**: Once the workflow completes, the generated files will be available in the `outputs` directory.

## Outputs

The following formats will be generated:

- `cv.html`: Your CV in HTML format.
- `cv.pdf`: Your CV in PDF format.
- `cv.docx`: Your CV in DOCX format.
- `cv.tex`: Your CV in LaTeX format.

## Requirements

- Ensure that you have a GitHub account and access to GitHub Actions.
- The workflow uses Pandoc, which will be installed automatically during the workflow execution.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.
