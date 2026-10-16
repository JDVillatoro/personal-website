# personal-website

Joel Villatoro's personal website, https://www.joelvillatoro.com/, moving from
Google Sites to GitHub Pages. Repo: https://github.com/JDVillatoro/personal-website (public).

Pages are Markdown; GitHub builds them into HTML with Jekyll on every push to
`main`.

## Layout

| Path | What it is |
|---|---|
| `index.md` (about, employment, education), `research.md` (overview, papers, talks) | The pages. `permalink` in the front matter is the page's address. |
| `_config.yml` | Site title, top menu (`nav`), settings. |
| `_layouts/default.html` | The HTML around every page (header, menu, MathJax). |
| `assets/css/style.css` | Styles. |
| `files/` | PDFs and images (CV, papers, slides, photo). |
| `CNAME` | The custom domain (added at the switch-over step below). |

**Adding a page:** create `name.md` with front matter `layout: default`,
`title:` and `permalink: /name/`, and add it to `nav` in `_config.yml` if it
should be in the menu. Link to files with
`{{ '/files/x.pdf' | relative_url }}` so links work at both the github.io
address and the custom domain.

**Bands:** pages are built from full-width stripes, like the old Google
Site. Wrap a part of a page in `<section class="band" markdown="1">` (white)
or `<section class="band dark" markdown="1">` (slate), closed by
`</section>`, with blank lines around the Markdown inside.

**Math:** `$$...$$` (see the comment in `_config.yml`).

## Previewing

Open the folder in VS Code and choose "Reopen in Container", then in the
container terminal run:

    bundle exec jekyll serve --livereload

and open http://localhost:4000. Or just push: GitHub rebuilds in about a
minute (progress under the repo's Actions tab).

## Moving from Google Sites

1. Copy each page's text into the `.md` files, and download PDFs/images from
   the Google Site into `files/`.
2. Create the GitHub repo (public: Pages on a private repo needs a paid
   plan), push, and turn on Pages: Settings → Pages → Source "Deploy from a
   branch", branch `main`, folder `/ (root)`. The site appears at
   https://jdvillatoro.github.io/personal-website/. Check it there.
3. Verify the domain with GitHub (account Settings → Pages → Add a domain),
   which stops anyone else's repo from claiming it.
4. Switch over: add a `CNAME` file containing just `www.joelvillatoro.com`,
   push, and change DNS at the registrar (remove Google Sites' records first):
   - apex (`joelvillatoro.com`): four `A` records to `185.199.108.153`,
     `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `www`: a `CNAME` record to `jdvillatoro.github.io`
5. After DNS updates (minutes to hours), tick "Enforce HTTPS" under
   Settings → Pages. Then unpublish the Google Site.

The domain is set on this repo only, so other Pages sites (e.g.
`jdvillatoro.github.io/m106-websites`) keep their github.io addresses. Don't
create a `JDVillatoro.github.io` repo with the domain on it: that would move
all of them under the domain.
