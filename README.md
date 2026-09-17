# shitianl.github.io

Source for my personal academic website, published at
**[shitianl.github.io](https://shitianl.github.io)**.

I am a PhD candidate in Biological Sciences at UC San Diego, working in
[Diana Hargreaves' lab](https://www.salk.edu/scientist/diana-hargreaves/) at the
Salk Institute. My research looks at how chromatin regulation — particularly the
SWI/SNF complex — shapes tumor immunity and responses to cancer immunotherapy.

## How the site is built

The site is a single page generated from R Markdown using the
[postcards](https://github.com/seankross/postcards) package (`trestles` template).

| Path | Purpose |
| --- | --- |
| `index.Rmd` | Source of truth — all page content lives here |
| `index.html` | Rendered output, committed so GitHub Pages can serve it |
| `profile.png` | Portrait used by the template |
| `.nojekyll` | Tells GitHub Pages to serve the HTML as-is |
| `ShitianLi.Rproj` | RStudio project file |

`index.html` is self-contained: postcards inlines the CSS and JavaScript, which
is why the file is large. Do not edit it by hand — it is overwritten on every
render.

## Building locally

```r
install.packages(c("rmarkdown", "postcards"))
rmarkdown::render("index.Rmd")
```

Or click **Knit** in RStudio with `ShitianLi.Rproj` open.

## Deploying

GitHub Pages serves the `main` branch from the repository root, so deploying is
just committing the re-rendered output:

```sh
git add index.Rmd index.html
git commit -m "Update site content"
git push
```

Changes appear at the live URL within a minute or so. A `.nojekyll` file tells
Pages to serve `index.html` as-is rather than running it through Jekyll.

## License

Site content (text, publication list, portrait) © Shitian Li. The build
configuration may be reused freely.
