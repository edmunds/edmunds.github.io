# The Edmunds Technology Blog

If this is your first time looking through a Jekyll site, start at the 
`_config.yml` file.  Then check out `index.html` and `_layouts/default.html`.
Next, look any of the files in `_posts/` and the `_layouts/post.html` file.

There is also a template post in the `_drafts/` directory, which has examples of
markdown syntax for many basic html elements.

## Directory Structure

* `_includes/` - reusable chunks of html included with the following syntax:
```
{% include foo.html %}
```
* `_layouts/` - reusable markup (jekyll layouts) used by including the following metadata at the top of file:
```
---
layout: bar
---
```
* `_posts/` - .md or .html files containing the a post's content
* `_sass/` - .scss files containing the css for the site
* `_sass/` - .scss files containing the css for the site
* `public/` - a directory containing public assets (currently images, icons, and fonts)
* `tag/` - a directory that contains the html files for each 'tag' on the site (ie. big-data, tips-and-tricks)

## Other Files in the Root Directory
* `.gitignore` - the project's .gitignore file
* `404.html` - the 404 file for the site
* `_config.yml` - contains jekyll variables and options
* `about.md` - the `/about/` page (not to be confused with `_includes/about.html` that is used throughout the site) 
* `atom.xml` - the template for generating the [Atom](https://en.wikipedia.org/wiki/Atom_(standard)) file 
* `index.html` - the homepage for the site 
* `README.md` - readme document for the blog (you're reading it now!) 
* `styles.scss` - the sass file defining the imports for the site 

## Official Jekyll Documentation

[Jekyll Documentation](https://jekyllrb.com/)

## Running Jekyll Locally

```bash
jekyll serve --watch
```

```bash
jekyll serve --watch --drafts
```

