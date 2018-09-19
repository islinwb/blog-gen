+++
title = "Host hugo website on github pages"
description = ""
tags = [
    "website",
    "hugo",
    "github",
]
date = "2018-09-19"
categories = [
    "website",
]
menu = "main"
+++

## Step 1. Install Hugo
```shell
# env
# NAME="Ubuntu"
# VERSION="16.04.3 LTS (Xenial Xerus)"
wget https://github.com/gohugoio/hugo/releases/download/v0.48/hugo_0.48_Linux-64bit.deb
dpkg -i hugo_0.48_Linux-64bit.deb

hugo new site <YOUR-PROJECT>
cd <YOUR-PROJECT>
# web browser's not in the same machine
hugo server --bind "192.168.0.1"
# browse the content

# add content
# the field `draft`
hugo new post/demo.md
```

## Step 2. Github repo and Pages
Create github repo `<YOUR-PROJECT>` and `<USERNAME>.github.io`

```shell
cd <YOUR-PROJECT>
git init
git remote add origin https://github.com/<USERNAME>/`<YOUR-PROJECT>.git

# if the `public/` exists
rm -rf public
git submodule add -b master https://github.com/<USERNAME>/<USERNAME>.github.io.git

# (re)generate `public/`

```