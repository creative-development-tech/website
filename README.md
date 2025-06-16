Website Documentation with MkDocs and Magic
Static website using MkDocs, hosted on GitHub Pages, managed by Magic.
Setup

Install Dependencies

Install Magic.
Run magic init.


Configure MkDocs

Move Markdown files from docs to docs_src.
Create mkdocs.yml in root:site_name: Your Website Name
docs_dir: docs_src
site_dir: docs
theme: readthedocs
nav:
  - Home: index.md
  - About: about.md




Update mojoproject.toml

Add:[tasks]
build_docs = "mkdocs build"

[dependencies]
mkdocs = "*"




Build Documentation

Run magic run build_docs.


Commit and Push

Commit docs:git add .
git commit -m "Update docs"
git push




GitHub Pages

Ensure Pages set to "main" branch, "/docs" folder.



Notes

Update nav in mkdocs.yml for all pages.
Customize theme in mkdocs.yml if needed.

