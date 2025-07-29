# wavi-web
[![Built with Material for MkDocs](https://img.shields.io/badge/Material_for_MkDocs-526CFE?style=for-the-badge&logo=MaterialForMkDocs&logoColor=white)](https://squidfunk.github.io/mkdocs-material/)

Main website for the whole WAVI.jl ecosystem. The website is built using [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/).

# Making Changes

Please follow the instructions below to make changes.

## Installing Dependencies
To install the documentation dependencies:

```bash
source venv/bin/activate

pip install -e requirements.txt
```

### Building the Docs
To preview the documentation locally:
```bash
mkdocs serve
```

To build the documentation:
```bash
mkdocs build
```

### Navigation
The navigation is handled in `mkdocs.yml`:
```yaml
nav:
  - Overview: index.md
```
If you create a new page, do not forget to add in to the `nav:`.
