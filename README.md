# data-store-ux-knowledge-docs
A repository containing the curated notes of the JF UX for the BAM Data Store.


## Launching locally the docs page

Create a virtual environment. You can use `conda` or `venv` for this:

- **Using venv**:
  ```bash
  python3 -m venv uxdocs
  source uxdocs/bin/activate 
  ```
- **Using conda**:
  ```bash
  conda create --name uxdocs pip
  conda activate uxdocs
  ```

**NOTE:** these commands are written in Linux. For Windows OS, the `venv` environment is activated by running:
```bash
uxdocs\Scripts\activate
```

In both cases, you should see your terminal with `(uxdocs)` at the beginning.

Now, install the `zensical` package:
```bash
pip install zensical
```

Once the installation finishes,you can run locally the Zensical docs:
```bash
zensical serve
```

In the terminal, you will see:
```
serving <path-to-your-clone-repo>/data-store-ux-knowledge-docs/site on http://localhost:8000
Build started
No issues found
```

Click on `http://localhost:8000` to open the docs page.

### Adding new pages

You need to do 2 things:
1. Create a markdown file in `docs/`. You can create subfolders and structure the `docs/` folder as you wish.
2. Add the new documentation page in the `zensical.toml` file, in the `nav` block.

For example, imagine I create a `docs/newdoc.md` file. Then, I also change:
```
nav = [
  { "Get started" = "index.md" },
  { "Markdown in 5min" = "markdown.md" },
  { "New documentation page" = "newdoc.md" },
]
```

When saving the `zensical.toml`, the localhost page will be automatically updated, so you do not need to click again on `http://localhost:8000`.

Note that the paths are relative to `docs/`. If you created a subfolder, e.g. `docs/subfolder/newdoc.md`, then in `zensical.toml`:
```
nav = [
  { "Get started" = "index.md" },
  { "Markdown in 5min" = "markdown.md" },
  { "New documentation page" = "subfolder/newdoc.md" },
]
```