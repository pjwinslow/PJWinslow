# Updating your website

Everything on the site comes from a few text files. You can edit them directly on GitHub: open the file, click the pencil icon, make your change, and click **Commit changes**. Once the site is live, each change you commit to the `main` branch goes live in about two minutes.

## "Coming soon" sections

Unpublished work is kept out of this repository, because the repository is public. While `publications_coming_soon: true` is set in `hugo.yaml`, the Publications section shows blurred lines with "Coming soon". A research project with `coming_soon: true` in `data/research.yaml` does the same for its description.

When a paper is out, add it to `data/papers.yaml` (below), change `publications_coming_soon` to `false`, and give the research project its `points` again in place of `coming_soon` and `lines`.

## Add a new paper

Open `data/papers.yaml` and copy an existing entry. For example:

```yaml
- title: "Your paper title"
  authors: ["Winslow P.J.", "Seelig B."]
  year: 2027
  status: "under review"
  venue: ""
  pdf: "files/your-paper.pdf"
  link: ""
  abstract: ""
  job_market_paper: false
```

To attach a PDF, upload it to `static/files/` (on GitHub: open the folder, then **Add file → Upload files**) and set `pdf` to `files/` plus the file name. To link to a journal page instead, put the address in `link`. Write *de novo* as `*de novo*` to make it italic.

The `status` field controls which heading the paper appears under:

| status | Shown under |
|---|---|
| `published`, `accepted` | Publications |
| `revise and resubmit`, `under review`, `working paper` | Working papers |
| `in preparation`, `work in progress` | In preparation |

## Mark a paper as published

In `data/papers.yaml`, change its `status` to `"published"` and fill in `venue` (the journal name), `year`, and `link` (the DOI address).

## Add a job market paper

Set `job_market_paper: true` on that paper and add its `abstract`. It will appear in a highlighted box at the top of the Publications section.

## Update your bio

The About text is in `content/_index.md`, below the line with `---`. Your name, title, department, tagline, interests, advisor, affiliation, education, and email are in `hugo.yaml` under `params`.

## Add a presentation

Open `data/talks.yaml` and add an entry at the top. Use `type: oral` or `type: poster`.

## Add a teaching or service entry

Edit `data/teaching.yaml` (teaching and mentoring) or `data/service.yaml` (service and outreach). Newest first.

## Add an award

Add a line to `data/awards.yaml`, newest first.

## Add a news item

There is no news section yet. Ask your assistant to add one from a `data/news.yaml` file, with entries like:

```yaml
- date: 2026-11
  text: "Gave a talk at ..."
```

## Add a blog post

Ask your assistant to add a blog section. Each post then lives in its own folder, `content/blog/your-post-name/index.md`, starting with:

```yaml
---
title: "Post title"
date: 2026-11-01
description: "One-sentence summary."
---
```

## Update your CV

Upload the new PDF to `static/files/` with the same name, `cv.pdf`, replacing the old one. This is the public web version, so leave out anything not ready to share (GPAs, unpublished titles).

## Change your photos

- **Headshot** (top of the page): replace `static/images/headshot.jpg`.
- **Lab photo** (beside your bio): replace `static/images/lab.jpg`.
- **PJW initials** (above your name, made from three protein structures): replace `static/images/pjw-monogram.webp`. Use an image with a transparent background and light-coloured shapes, since it sits on the dark band.

Keep the same file names, or change the matching `photo`, `lab_photo`, or `monogram` line in `hugo.yaml`. The descriptions read by screen readers are the `_alt` lines next to them.

## Add social links

In `hugo.yaml`, replace `social: []` with, for example:

```yaml
  social:
    - name: "Google Scholar"
      url: "https://scholar.google.com/citations?user=..."
    - name: "ORCID"
      url: "https://orcid.org/0000-0000-0000-0000"
```

## Change the address of the site

The site's address is `baseURL` in `hugo.yaml`. If you rename the repository to `pjwinslow.github.io`, set `baseURL` to `https://pjwinslow.github.io/`, and update the addresses in `static/robots.txt` and `static/llms.txt` to match.

## Change the look of the site

The current design is modelled on the Sears Lab website; this is recorded in `hugo.yaml` under `params.mysite.design`. To change the look of the site, ask your assistant to run the design quest at https://gking.harvard.edu/mysite/files/QUEST_DESIGN.md and show you three options. Colours and fonts are set at the top of `assets/css/style.css`.

## Preview locally (optional)

Install Hugo (extended), then run `hugo server` in this folder and open the address it prints.
