# Enhanced Data Sessions article prepared with Manubot

<!-- usage note: edit the H1 title above to personalize the manuscript -->

[![HTML Article](https://img.shields.io/badge/latest--article-HTML-blue.svg)](https://quivirr.github.io/Enhanced-Data-Sessions/)
[![PDF article](https://img.shields.io/badge/latest--article-PDF-blue.svg)](https://quivirr.github.io/Enhanced-Data-Sessions/manuscript.pdf)
[![DOI](https://img.shields.io/badge/DOI-10.5278/ojs.quivirr.v1.2020.a0001-blue.svg)](https://doi.org/10.5278/ojs.quivirr.v1.2020.a0001)
![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/QUIVIRR/Enhanced-Data-Sessions)
![GitHub Release Date](https://img.shields.io/github/release-date/QUIVIRR/Enhanced-Data-Sessions)
![GitHub repo size](https://img.shields.io/github/repo-size/QUIVIRR/Enhanced-Data-Sessions)
![GitHub last commit](https://img.shields.io/github/last-commit/QUIVIRR/Enhanced-Data-Sessions)
![GitHub issues](https://img.shields.io/github/issues/QUIVIRR/Enhanced-Data-Sessions)
![GitHub pull requests](https://img.shields.io/github/issues-pr/QUIVIRR/Enhanced-Data-Sessions)

<!-- usage note: delete CI badges above for services not used by your manuscript -->

## Manuscript description

<!-- usage note: edit this section. -->

This repository contains all versions and revisions made to the complete text of an article by Paul McIlvenny.
- A first draft of the article was written in October 2019.
- A second draft was prepared in July and August 2020 using Manubot and a private GitHub repository, as well as Pandoc, GitKraken, VScode and other open source software.
- The final draft was made public on @QUIVIRR in a GitHub repository using Manubot, and a preprint PDF was uploaded to [SocArXiv](https://doi.org/10.31235/osf.io/eu7yw).
- Some of the figures are archived on FigShare and the video is available on YouTube and archived on Zenodo.
- The article was published (December 2020) in the [QUIVIRR: Qualitative Video Research Reports](https://journals.aau.dk/index.php/QUIVIRR/index) journal in [RICH HTML and PDF formats](https://journals.aau.dk/index.php/QUIVIRR/article/view/a0001).
- Updates and corrections to the raw article in markdown [see the `content` folder] will be version controlled in this GitHub repository.
- The latest (not yet formatted for _QuiViRR_) versions of the article are available here ([HTML](https://quivirr.github.io/Enhanced-Data-Sessions/) or [PDF](https://quivirr.github.io/Enhanced-Data-Sessions/manuscript.pdf)).
These versions are updated automatically every time a commit with changes is made to the repository.

## What is Manubot?

<!-- usage note: do not edit this section -->

Manubot is a system for writing scholarly manuscripts via GitHub.
Manubot automates citations and references, versions manuscripts using git, and enables collaborative writing via GitHub.
An [overview manuscript](https://greenelab.github.io/meta-review/ "Open collaborative writing with Manubot") presents the benefits of collaborative writing with Manubot and its unique features.
The [rootstock repository](https://git.io/fhQH1) is a general purpose template for creating new Manubot instances, as detailed in [`SETUP.md`](SETUP.md).
See [`USAGE.md`](USAGE.md) for documentation how to write a manuscript.

Please open [an issue](https://git.io/fhQHM) for questions related to Manubot usage, bug reports, or general inquiries.

### Repository directories & files

The directories are as follows:

+ [`content`](content) contains the manuscript source, which includes markdown files as well as inputs for citations and references.
  See [`USAGE.md`](USAGE.md) for more information.
+ [`output`](output) contains the outputs (generated files) from Manubot including the resulting manuscripts.
  You should not edit these files manually, because they will get overwritten.
+ [`webpage`](webpage) is a directory meant to be rendered as a static webpage for viewing the HTML manuscript.
+ [`build`](build) contains commands and tools for building the manuscript.
+ [`ci`](ci) contains files necessary for deployment via continuous integration.

### Local execution

The easiest way to run Manubot is to use [continuous integration](#continuous-integration) to rebuild the manuscript when the content changes.
If you want to build a Manubot manuscript locally, install the [conda](https://conda.io) environment as described in [`build`](build).
Then, you can build the manuscript on POSIX systems by running the following commands from this root directory.

```sh
# Activate the manubot conda environment (assumes conda version >= 4.4)
conda activate manubot

# Build the manuscript, saving outputs to the output directory
bash build/build.sh

# At this point, the HTML & PDF outputs will have been created. The remaining
# commands are for serving the webpage to view the HTML manuscript locally.
# This is required to view local images in the HTML output.

# Configure the webpage directory
manubot webpage

# You can now open the manuscript webpage/index.html in a web browser.
# Alternatively, open a local webserver at http://localhost:8000/ with the
# following commands.
cd webpage
python -m http.server
```

Sometimes it's helpful to monitor the content directory and automatically rebuild the manuscript when a change is detected.
The following command, while running, will trigger both the `build.sh` script and `manubot webpage` command upon content changes:

```sh
bash build/autobuild.sh
```

### Continuous Integration

Whenever a pull request is opened, CI (continuous integration) will test whether the changes break the build process to generate a formatted manuscript.
The build process aims to detect common errors, such as invalid citations.
If your pull request build fails, see the CI logs for the cause of failure and revise your pull request accordingly.

When a commit to the `master` branch occurs (for example, when a pull request is merged), CI builds the manuscript and writes the results to the [`gh-pages`](https://github.com/manubot/rootstock/tree/gh-pages) and [`output`](https://github.com/manubot/rootstock/tree/output) branches.
The `gh-pages` branch uses [GitHub Pages](https://pages.github.com/) to host the following URLs:

+ **HTML manuscript** at https://manubot.github.io/rootstock/
+ **PDF manuscript** at https://manubot.github.io/rootstock/manuscript.pdf

For continuous integration configuration details, see [`.github/workflows/manubot.yaml`](.github/workflows/manubot.yaml) if using GitHub Actions or [`.travis.yml`](.travis.yml) if using Travis CI.

## License

<!--
usage note: edit this section to change the license of your manuscript or source code changes to this repository.
We encourage users to openly license their manuscripts, which is the default as specified below.
-->

[![License: CC BY 4.0](https://img.shields.io/badge/License%20All-CC%20BY%204.0-lightgrey.svg)](http://creativecommons.org/licenses/by/4.0/)
[![License: CC0 1.0](https://img.shields.io/badge/License%20Parts-CC0%201.0-lightgrey.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License%20Parts-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

Except when noted otherwise, the entirety of this repository is licensed under a CC BY 4.0 License ([`LICENSE.md`](LICENSE.md)), which allows reuse with attribution.
Please attribute by linking to https://github.com/manubot/rootstock.

Since CC BY is not ideal for code and data, certain repository components are also released under the CC0 1.0 ([`LICENSE CC0`](LICENSE-CC0.md)) and the CC BY 4.0 ([`LICENCE CC BY-NC-SA 4.0`](LICENSE-CC-BY-NC-SA-4.0.md)) public domain dedication.
All files matched by the following glob patterns are dual licensed under CC BY 4.0 and CC0 1.0:

+ `*.sh`
+ `*.py`
+ `*.yml` / `*.yaml`
+ `*.json`
+ `*.bib`
+ `*.tsv`
+ `.gitignore`

All other files are only available under [`LICENSE CC BY-NC-SA 4.0`](LICENSE-CC-BY-NC-SA-4.0.md), including:

+ `*.md`
+ `*.html`
+ `*.pdf`
+ `*.docx`

