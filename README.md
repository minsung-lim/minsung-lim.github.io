# Minsung Lim — CV

This repository publishes the English CV for Minsung Lim at
<https://minsung-lim.github.io/>. GitHub reserves that root URL for a public
repository named exactly `minsung-lim.github.io` under the `minsung-lim`
account.

## Updating the CV

Most CV content is maintained in [`_data/cv.yml`](_data/cv.yml). Keep dates in
reverse chronological order, update `last_updated` when public content changes,
use HTTPS for external links, and only publish claims that can be verified.
Public contact details are limited to an email image and profile links. Do not
add a raw email address, private telephone, or location fields.

LinkedIn is a reference source, not an automated data feed. Review profile
changes manually before copying them into the CV so that the published wording
and dates remain intentional.

The ISSRE 2026 publication record is intentionally unlinked until a direct
IEEE proceedings page or DOI becomes available. Add that stable URL without
changing the confirmed title or author order unless the published record
differs.

## Validation and local preview

Run the source checks with:

```sh
python3 -m pip install -r requirements-dev.txt
python3 -m unittest test/test_cv_data.py test/test_site_source.py -v
```

In a Ruby-enabled environment, preview the Jekyll site with:

```sh
bundle install
bundle exec jekyll serve
```

Rendered-page checks run in GitHub Actions after Jekyll builds `_site`:

```sh
python3 -m unittest test/test_rendered_site.py -v
```

## Deployment

For a checkout that still points to an earlier repository name, rename or
create the GitHub repository as `minsung-lim.github.io`, then update and verify
the remote:

```sh
git remote set-url origin https://github.com/minsung-lim/minsung-lim.github.io.git
git remote -v
```

Every push to `main` runs `.github/workflows/pages.yml`. The workflow validates
the source, builds the Jekyll site, tests the rendered HTML, and deploys it with
GitHub Pages. If deployment fails, inspect the latest **Test and deploy GitHub
Pages** run under the repository's Actions tab and confirm that Pages uses
**GitHub Actions** as its build source.

## Project documents

Requirements, decisions, and implementation notes live in `docs/`. New files
must use `{yymmdd}-{xx}-{subject}.md`, where `xx` is the zero-padded revision
number for that calendar day (for example,
`260821-04-publication-update.md`).
