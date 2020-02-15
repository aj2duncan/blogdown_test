---
title: Hosting xaringan slides using github pages
date: '2020-02-15'
slug: hosting-xaringan-slides-using-github-pages
categories:
  - R
tags:
  - xaringan
description: 'Guide to hosting xaringan slides online using github pages'
---

This is a quick guide to hosting [xaringan](https://github.com/yihui/xaringan) slides online using [github pages](https://pages.github.com/). 

To start with I create an RStudio project (initialising a git repository) and then `slides.Rmd` using the xaringan R markdown template. At this point we could modify the R markdown file but I'm going to make sure it works online first. 

Having created `slides.html` by *knitting* the R markdown file, we can commit everything we've got.

```sh
git add .
git commit -m "Initial commit, creating slides."
```

Now (if it hasn't already happened) we need to add the remote repo. Presuming we have SSH keys set up then we can add the remote from the command line 

```sh
git remote add origin git@github.com:user/repo_name.git
```

and push what we've got. 

```sh
git push -u origin master
```

We now have a couple of choices. If you are happy working with multiple branches in a repo then we can create a `gh-pages` branch and everything will happen automatically. This has the advantage that you can update other branches and only publish the `gh-pages` branch when you are happy for the slides to be live.

We can create and move to the new branch 

```sh
git checkout -b gh-pages
```

and push. 

```sh
git push origin gh-pages
```

The alternative is to change settings on github and use the `master` branch. To do this got to *Settings*, scroll down to *Github Pages* section and choose the *Source* to be the `master` branch. 

Either way, if we now wait a few minutes the slides will be available at [https://user.github.io/repo_name/slides.html](#).
