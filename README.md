# Website Documentation with MkDocs and Magic

Static website using MkDocs, hosted on GitHub Pages, managed by Magic.

## Setup

1. **Install Dependencies**
   - Install Magic.
   - Run `magic init`.

2. **Configure MkDocs**
   - Ensure `mkdocs.yml` is in the root directory with the following content:
     ```yaml
     site_name: Create Development Systems
     docs_dir: docs_src
     site_dir: docs
     theme:
       name: material
       custom_dir: overrides
     nav:
       - Home: index.md
       - About: about.md
     ```
   - Create `docs_src` directory for source files.
   - Place `index.md` and `about.md` in `docs_src`.

3. **Update mojoproject.toml**
   - Ensure `mojoproject.toml` includes:
     ```toml
     [project]
     authors = ["Peter Alexander <makeroftools@creativedevelopment.systems>"]
     channels = ["https://conda.modular.com/max-nightly", "https://conda.modular.com/max", "https://repo.prefix.dev/modular-community", "conda-forge"]
     name = "website"
     platforms = ["linux-64"]
     version = "0.1.0"

     [tasks]
     build_docs = "mkdocs build"

     [dependencies]
     max = "*"
     python = ">=3.13.5,<3.14"
     mkdocs = "*"
     mkdocs-material = "*"
     ```

4. **Build Documentation**
   - Run `magic run build_docs`.

5. **Commit and Push**
   - Commit `docs`:
     ```
     git add .
     git commit -m "Update docs"
     git push
     ```

6. **GitHub Pages**
   - Ensure Pages are set to the "main" branch and "/docs" folder.

## Notes
- Update the `nav` section in `mkdocs.yml` to include all pages.
- Customize the theme further in `mkdocs.yml` if needed (e.g., colors, fonts).
- For advanced customization, use the `overrides` directory to modify templates.