# personal-website

Joel's personal site, Jekyll on GitHub Pages. Read README.md for layout,
previewing, and the Google Sites migration steps.

- No theme: `_layouts/default.html` + `assets/css/style.css` are the whole
  design. Keep it that way unless Joel asks for a theme. The style copies the
  old Google Site (white/slate bands, Roboto + Open Sans); see README "Bands".
- Only plugins in the `github-pages` gem work (GitHub builds the site, no
  custom build step).
- Internal links and file links use the `relative_url` filter: the site is
  served under `/personal-website/` until the custom domain is set.
- Jekyll/Ruby exist only in the dev container. From WSL, Claude can't build or
  preview; ask Joel to run `bundle exec jekyll serve` in the container.
- The Google Site isn't reachable from Claude's sandbox; Joel pastes text or
  downloads files.
- The custom domain goes on this repo only (`CNAME` file), never on a
  `JDVillatoro.github.io` repo.
- `cv.md` is a hand copy of `~/jobs/applications_2026/master/cv/CV.tex`, and
  `files/cv.pdf` is that CV's PDF. When the CV changes, update both together.
