# Documentation for RuyiAgent

This is the documentation for RuyiAgent. It is built using MkDocs and Material for MkDocs, which can directly convert Markdown files to HTML pages and deploy them to the GitHub Pages.

## Installation for MkDocs and Material for MkDocs

``` bash
pip install mkdocs
pip install mkdocs-material
pip install mike
pip install mkdocs-rss-plugin
pip install mkdocs-minify-plugin
pip install mkdocs-static-i18n
pip install mkdocstrings-python
```

## Commands for MkDocs

``` bash
# You need cd to the mkdocs.yml directory first
cd mkdoc

# Local preview, need to cd to mkdocs directory, will start a local server on port 8000
mkdocs serve

# Deployment, need to cd to mkdocs directory, will automatically deploy the latest documentation to the gh-pages branch of the github repo
mkdocs gh-deploy --force

# Update the latest version alias
mike deploy --push --update-aliases x.x latest
```
