# Github.io

## Table of Contents

- [Get Start](#get-start)
    - [SSH key](#ssh-key)
    - [Installation](#installation)
- [Quickstarts](#quickstarts)
- [Communication](#communication)
- [Releases and Contributing](#releases-and-contributing)
- [The Team](#the-team)

---


## Get Start

For full documentation visit [mkdocs.org](https://www.mkdocs.org).

### SSH key

open your repository and copy your `SSH key`

### Installation

with git

```
git clone <your SSH key>
```

activate virtual environment

```py linenums="1"
cd <your repository name>
python -m venv venv
source venv/bin/activate
```

Next, install the theme and its dependencies with:

```
pip install -e mkdocs-material
```

final, open vscode

```
code .
```

### Create new M.K.:
on terminal

```py linenums="1"
mkdocs new .
// create index.md
```

This will create the following structure:
```
.
├─ docs/
│  └─ index.md
└─ mkdocs.yml
```
### preview your serve
you can preview your changes as you write your documentation. The server will automatically rebuild the site upon saving. Start it with:
```
mkdocs serve
```

---

## Configuration

Minimal:
``` py linenums='1'
site_name: My site
site_url: https://mydomain.org/mysite
theme:
  name: material
```

other configuration:

Material for MkDocs comes with many configuration options, these options can refer to this website<br>
[creating-your-site](https://squidfunk.github.io/mkdocs-material/creating-your-site/).

other example:
``` py linenums='1'
site_name: Github.io
site_url: https://mydomain.org/mysite
theme:
  name: material
  features:
    - navigation.tabs
    - navigation.sections
    - toc.integrate
    - navigation.top
    - search.suggest
    - search.highlight
    - content.tabs.link
    - content.code.annotation
    - content.code.copy
  language: en
  palette:
    - scheme: default
      toggle:
        icon: material/toggle-switch-off-outline 
        name: Switch to dark mode
      primary: teal
      accent: purple 
    - scheme: slate 
      toggle:
        icon: material/toggle-switch
        name: Switch to light mode    
      primary: teal
      accent: lime

extra:
  social:
    - icon: fontawesome/brands/github-alt
      link: https://github.com/
    - icon: fontawesome/brands/linkedin-in
      link: https://www.linkedin.com/in/your-linkedin-profile
    - icon: fontawesome/brands/twitter
      link: https://twitter.com/your-twitter-handle

markdown_extensions:
  - pymdownx.highlight:
      anchor_linenums: true
  - pymdownx.inlinehilite
  - pymdownx.snippets
  - admonition
  - pymdownx.arithmatex:
      generic: true
  - footnotes
  - pymdownx.details
  - pymdownx.superfences
  - pymdownx.mark
  - attr_list
  # - pymdownx.emoji:
  #     emoji_index: !!python/name:materialx.emoji.twemoji
  #     emoji_generator: !!python/name:materialx.emoji.to_svg

copyright: |
  &copy; 2024 <a href=""  target="_blank" rel="noopener"></a>
```
>  Configuration Breakdown:<br>
>  site_name: The name of your website, specified as "Github.io".<br>
>  site_url: The URL of your website, set to "https://mydomain.org/mysite".<br>
>  theme: Specifies the theme used for your site, which is Material. It includes various features such as navigation tabs, section  > > > >  navigation, integrated table of contents (TOC), top navigation, search suggestions, search highlighting, linkable content tabs, code  。>  annotation, and code copying.<br>
>  language: Indicates the language used on the website, which is English ("en").<br>
>  palette: Defines the color scheme for the theme. It includes two schemes: default and slate. Each scheme specifies toggle icons and >  >  names for switching between dark and light modes, primary colors, and accent colors.<br>

## Publishing
Using GitHub Actions you can automate the deployment of your project documentation. At the root of your repository, create a new GitHub Actions workflow, e.g. .github/workflows/ci.yml, and copy and paste the following contents:
```
name: ci 
on:
  push:
    branches:
      - master 
      - main
permissions:
  contents: write
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Configure Git Credentials
        run: |
          git config user.name github-actions[bot]
          git config user.email 41898282+github-actions[bot]@users.noreply.github.com
      - uses: actions/setup-python@v5
        with:
          python-version: 3.x
      - run: echo "cache_id=$(date --utc '+%V')" >> $GITHUB_ENV 
      - uses: actions/cache@v4
        with:
          key: mkdocs-material-${{ env.cache_id }}
          path: .cache
          restore-keys: |
            mkdocs-material-
      - run: pip install mkdocs-material 
      - run: mkdocs gh-deploy --force
```



## Conclusion
This quickstart demonstrates how easy to use our package for native Python users.
More usage detail on document.
[![doc](https://img.shields.io/badge/docs%20-passing-orange.svg?style=for-the-badge)](https://squidfunk.github.io/mkdocs-material/getting-started/)


