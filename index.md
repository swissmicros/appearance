---
layout: page
title: Technical Directory listing

descriptions: 
  - name: "README.md"
    text: "This is a README file in markdown."
  - name: "favicon.gif"
    text: "<span style='color: red'>favicon appears in the browser tab</span>"
---

# Common public repositories 


## This repository gets cloned as a base for a new public repository.

This repository shares common files and folders responsible for the appearance of the SwissMicros website hosted on GitHub Pages.

Add the two last lines to _config.yml in the root folder of your new repository
```
layouts_dir     : ./appearance/_layouts
includes_dir     : ./appearance/_includes
```

Add this file to a repository for GitHub Pages:

/.github/workflows/asciidoctor-ghpages.yml

```
name: asciidoctor-ghpages

# Controls when the action will run. Triggers the workflow on push or pull request
# events but only for the master branch
on:
  push:
    branches: [ master, main ]
  pull_request:
    branches: [ master, main ]
  workflow_dispatch:

# A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs:
  # This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
    # Checks-out your repository under $GITHUB_WORKSPACE, so your job can access it
    - uses: actions/checkout@v2
    # Checkout submodules recursive
    - name: Checkout submodules Remote
      run: git submodule add -b main https://github.com/swissmicros/appearance.git
    # Includes the AsciiDoctor GitHub Pages Action to convert adoc files to html and publish to gh-pages branch
    - name: asciidoctor-ghpages
      uses: manoelcampos/asciidoctor-ghpages-action@v2
      with:
        asciidoctor_params: --attribute=nofooter
```
