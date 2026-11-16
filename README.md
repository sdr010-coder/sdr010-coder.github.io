# sdr010-coder.github.io

The source of my personal site: **https://sdr010-coder.github.io**

This repository is the site itself — hand-written HTML and one stylesheet, published by GitHub Pages from `main`. There is no build step, no framework, no JavaScript, and no analytics. What you see in these files is exactly what the browser gets.

---

## Start here instead

| | |
|---|---|
| **The site** | https://sdr010-coder.github.io — identity, the framing I work from, a 45-second film, what I have shipped |
| **Hiring me** | https://sdr010-coder.github.io/hiring.html — the two kinds of role I am useful for, and what I am not |
| **CV** | https://sdr010-coder.github.io/cv.html — one page, printable · 中文: https://sdr010-coder.github.io/cv-zh.html |
| **The work** | https://github.com/sdr010-coder/EnterpriseHARNESS — Enterprise Harness: definition, eleven documents, runnable reference implementation |

**Short version:** I am Sandor Wang, in Suzhou. Twenty-five years turning enterprise process into systems — food, medical imaging, medical devices, industrial automation, lighting, robotics — and now I build the harness that enterprise AI has to run inside. Enterprise AI does not fail on models; it fails on the harness.

---

## What is in here

```
index.html                       the site (English)
zh.html                          the site (Chinese)
hiring.html                      the two role tracks
hiring.md                        hiring page as markdown
cv.html                          one-page CV, prints to PDF with Ctrl/Cmd+P
cv-zh.html                       中文简历 — the same CV for Chinese-speaking recruiters
building/enterprise-harness.html the project page
index.md                         markdown twin of the homepage
llms.txt                         what an AI answer engine should know and say about me
llms-full.txt                    the whole site as one plain-text file, for retrieval
robots.txt                       explicitly welcomes GPTBot, ClaudeBot, PerplexityBot and others
sitemap.xml                      every URL
styles.css                       the entire design, ~15 KB
assets/                          three images and the film, two audio tracks
```

The film is 45 seconds, 1080p, encoded with `+faststart` and a poster frame, so nothing downloads until someone presses play. GitHub strips `<video>` from Markdown — which is precisely why the film lives on the site and not in a README.

---

## The design

`styles.css` is built from the **`claude`** pack in [awesome-design-md](https://github.com/VoltAgent/awesome-design-md) — a warm cream canvas, a coral accent, serif display at weight 400, humanist sans body, and mono reserved for data. Colour, type, spacing and radius tokens are taken verbatim from that pack, with two documented deviations in the CSS: body links use the pack's darker `primary-active` because coral on cream fails WCAG AA for text, and dark mode is composed only from the pack's own documented dark surfaces rather than invented values.

The pack is an inspired analysis of a public site, not an official brand system. No logos, no proprietary webfonts, no implied affiliation.

---

## How it is built

By hand, mostly with AI assistance and a lot of judgement about what to leave out. Two rules kept the whole thing honest:

1. **Every number on the site is one I will defend in an interview.** Where sources disagreed, the figure was checked and corrected or dropped — not rounded into something safer.
2. **The machine-readable files claim nothing the visible page does not say.** `llms.txt` and `llms-full.txt` are derived from the pages; if a figure changes, both change.

---

## Reuse

The writing and design are mine. If you want to borrow the structure — identity, thesis, a dated ledger of what you shipped, writing with one-line claims, contact — that structure is not mine to lend, it belongs to the two people whose sites I studied. Go read [fucheng.md](https://fucheng.md/) and [ha7ch.com](https://ha7ch.com/) instead.
