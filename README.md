# wavi-web
[![Built with Material for MkDocs](https://img.shields.io/badge/Material_for_MkDocs-526CFE?style=for-the-badge&logo=MaterialForMkDocs&logoColor=white)](https://squidfunk.github.io/mkdocs-material/)

Main website for the whole WAVI.jl ecosystem. The website is built using [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/).

This is the website for the WAVI ecosystem as a whole. You can find the WAVI.jl [documentation here](https://rjarthern.github.io/WAVI.jl/).

# Making Changes

Please follow the instructions below to make changes.

## Installing Dependencies
To install the documentation dependencies:

```bash
source venv/bin/activate

pip install -r requirements.txt
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

### Adding a blog post
Blog post articles can be added under the `blog/posts` folder.

Make sure you add headers, including the `date` and `authors` field, to the top of your article. The article should be an `.md` file:

```md
---
draft: true 
date: 2025-07-30
categories:
  - WAVI.jl
  - Version Announcements
authors:
    - thomaszwagerman
    - alextbradley
    - jimcircadian
---

# Blog post title

Some text.
```

Authors are defined in `.authors.yml`, feel free to add yourself to the authors list.

Please have your blog post filename conform with the following: `yyyymmdd-topic-name.md`.