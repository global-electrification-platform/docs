# GEP - Advanced Documentation Website

This is the repository for GEP's Advanced Documentation Website, which covers complex topics about the platform like performing data ingests, writing model configurations and running the platform locally.

If you have any questions, please [open an issue](https://github.com/global-electrification-platform/docs/issues/new) or [contact the maintainers](http://gep-explorer.surge.sh/about).


A [static site generator](https://github.com/developmentseed/doc-seed) is used to transform markdown files into the live website. The following sections will give an overview on how to edit content.


## Editing content - via browser

[Prose.io](https://prose.io/#about) editor can be used to make changes to the website via browser, at this link:

- https://prose.io/#global-electrification-platform/docs

## Editing content - offline

If you prefer to check changes locally before committing them, [clone this repository](https://help.github.com/en/articles/cloning-a-repository) and follow the steps:

### 1) Install [nvm](https://github.com/creationix/nvm)

### 2) Active required node version

    nvm install

### 3) Install yarn

    nvm install -g yarn

### 4) Install node modules

    yarn install

### 5) Start the app

    yarn run serve

### 6) Access the website at http://localhost:3000


The system will watch files looking for changes, and the website will automatically refresh since it is bundled with livereload.    

## Markdown files

The posts are written in [markdown](https://daringfireball.net/projects/markdown/syntax) but `html` is also supported if needed.
For a post to be processed by Doc Seed it needs to include the `YAML frontmatter` which is the information between the `---` (triple dashes).

Example:
```
---
title: The post title
date: 2012-12-07
layout: post.html
---

Content of the post goes here
```

The properties defined in the `frontmatter` allow us to control how the post is rendered.

**title**  
Title of the post displayed in the navigation and as a heading in the post page.

**date**  
Publication date.

**layout**  
Used by Doc Seed to know which layout to use. **Must always be `post.html`**

**permalink**
Allows us to override the default generated url for a post. To set a page as the entry point for the documentation site use `permalink: '/'` 

#### Using variables
It is possible to used variables defined in the config directly in the markdown file.
To render a variable just use the following syntax `{{varName}}`. This is very useful when including images which should always have the full url:
```
![]({{baseurl}}/assets/graphics/content/docseed.png)
```

