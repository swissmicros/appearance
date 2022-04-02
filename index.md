---
layout: page
title: Technical Directory listing

descriptions: 
  - name: "README.md"
    text: "This is a README file in markdown."
  - name: "favicon.gif"
    text: "<span style='color: red'>favicon appears in the browser tab</span>"
---

# Default for all public repositories 

## Clone this repository as a base for a new public repository.


This repository shares common files and folders responsible for the appearance of the SwissMicros website hosted on GitHub Pages.

This repository is meant as a submodule in any SwissMicros repositories:

```
git submodule add https://github.com/swissmicros/appearance.git 
```

This will add the following to .gitmodules
```
[submodule "appearance.git"]
  path = appearance
  url = https://github.com/swissmicros/appearance.git
```

Add the two last lines to _config.yml in the root folder of your new repository
```
layouts_dir     : ./appearance/_layouts
includes_dir     : ./appearance/_includes
```