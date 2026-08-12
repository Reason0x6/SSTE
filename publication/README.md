# PDF publication build

Canonical repository: <https://github.com/Reason0x6/SSTE>

The GitHub workflow builds `SSTE-1.0.md` as an A4 standards-style PDF. It embeds
fonts, metadata, bookmarks, numbered clauses, a table of contents, running
headers, page numbers, and a SHA-256 checksum.

The PDF declares PDF/A-2b conformance. The workflow validates that declaration
against the PDF/A-2b profile with veraPDF. A failed validation fails the job.
PDF/A-2b is defined by ISO 19005-2.

Run the workflow from the GitHub Actions page, or push a relevant change to
`main`. Download the `SSTE-1.0-PDF-A-2b` artifact after the job succeeds.

## Scope of the claim

The layout is inspired by common ISO standards-document conventions. It is not
an official ISO template, and the build does not make SSTE an ISO-published or
ISO-certified standard. The machine-checked claim applies only to PDF/A-2b
archival conformance.

The workflow pins the document toolchain and veraPDF release. Review and update
these versions through a pull request when necessary.

`pandoc-pdfa.tex` is the pinned Pandoc 3.10 LaTeX template with the PDF/A-2b
document declaration added before `documentclass`. Update it when the pinned
Pandoc version changes.
