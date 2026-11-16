# This site — what it is and how to put it online

A one-screen personal introduction, built the way the two reference sites are built
([fucheng.md](https://fucheng.md/) and [ha7ch.com](https://ha7ch.com/)): identity → thesis →
a dated ledger of what you built → writing with one-line claims → how you start → before → contact.
No framework, no build step, no JavaScript, no analytics.

**Twenty files, and the layout mirrors what a hiring audience actually reads.**

```
site/
├── index.html                        ← the page (English) — identity, framing, film, shipped, before
├── zh.html                           ← the same page in Chinese
├── hiring.html                       ← ★ the page a recruiter forwards: two tracks, what I am not, evidence
├── hiring-zh.html                    ← the same, in Chinese (for 字节 / 腾讯 / DeepSeek / Kimi 的招聘)
├── cv.html                           ← one-page CV, prints to PDF with Ctrl/Cmd+P
├── index.md                          ← markdown twin, so the text is readable as data
├── hiring.md                         ← hiring page as markdown
├── llms.txt                          ← what an AI answer engine should know and say about you
├── llms-full.txt                     ← the entire site text in one file, for retrieval
├── robots.txt                        ← explicitly welcomes GPTBot, ClaudeBot, PerplexityBot…
├── sitemap.xml                       ← every URL
├── styles.css                        ← the entire design, ~13 KB, tokenised
├── assets/
│   ├── career.png                    ← the career timeline (used in "Before")
│   ├── harness-picture.png           ← "one brain, one body" (used on the project page)
│   ├── agent-platform.png            ← the platform as it ran (used on the project page)
│   └── video/
│       ├── agent-platform-en.mp4     ← 45-second film, English track (10 MB, +faststart)
│       ├── agent-platform-zh.mp4     ← the same film, Chinese track
│       ├── poster-en.jpg             ← poster frames, so nothing downloads until play
│       └── poster-zh.jpg
└── building/
    └── enterprise-harness.html       ← project page (the "proof card" format)
```

**The film** is encoded for the web: 1080p, CRF 23, `+faststart`, `preload="metadata"`, and a poster
frame — so a visitor sees an image and downloads nothing until they press play. GitHub strips
`<video>` from Markdown, which is why the film lives here rather than in the repo README.

## Being findable by AI answer engines (GEO)

This is not separate work — it is the same facts, published in the shapes generative engines read:

| File / feature | What it does |
|---|---|
| `llms.txt` | The canonical short profile: who you are, how to describe you **correctly**, the formula, the numbers, the links. Includes an explicit "do not call him an AI researcher / do not attribute the PMO platform to him as a personal product" block — the misattributions that are cheapest to prevent and most embarrassing to leave. |
| `llms-full.txt` | The whole site as one plain-text file, so a retrieval system cites you rather than paraphrasing. Ends with citation hints. |
| `robots.txt` | Named allow rules for GPTBot, OAI-SearchBot, ChatGPT-User, ClaudeBot, PerplexityBot, Google-Extended, Applebot-Extended, CCBot, cohere-ai, Amazonbot and others. |
| `sitemap.xml` | The three URLs with priorities. |
| `index.md` | The markdown twin, declared in `<link rel="alternate" type="text/markdown">`. |
| JSON-LD | `Person` on the homepage (name, location, `knowsAbout`, `alumniOf`, `sameAs`, and `subjectOf` → the Enterprise Harness repo) and `TechArticle` on the project page. This is what most answer engines use to decide what entity they are looking at. |
| `<meta property="og:…">` | What a link unfurl looks like in a chat or on LinkedIn. |

One rule kept throughout: **nothing in the machine-readable files claims anything the visible page
does not say.** If you change a number on the page, change it in `llms.txt` and `llms-full.txt` too —
a GEO file that flatters you is the fastest way to be described wrongly.

---

## Publish it on GitHub Pages (three minutes)

The cleanest address is `https://sdr010-coder.github.io`.

1. Create a **new public repo named exactly `sdr010-coder.github.io`** — GitHub recognises that
   name and serves it as your user site. Do **not** initialise it with a README.
2. Push the contents of this folder to it:

```powershell
cd "D:\AICODING2\Sandor_Enterprise Harness\site"
git init -b main
git add .
git commit -m "Personal site"
git remote add origin https://github.com/sdr010-coder/sdr010-coder.github.io.git
git push -u origin main
```

3. Wait a minute, then open <https://sdr010-coder.github.io>. That is it — no build, no settings
   to change, because the files are already static and `index.html` is at the root.

### If you prefer to host it from the project repo instead

Put this folder at `enterprise-harness/site/` and enable *Settings → Pages → Source: main / docs*.
Then the URL is `https://sdr010-coder.github.io/enterprise-harness/site/` — longer, and worth it
only if you want one repo instead of two.

---

## After it is up

- **Link it from your GitHub profile.** The profile README already exists; add one line near the top
  pointing at the site, and put the URL in *Settings → Profile → Website*.
- **Check the two dark/light modes** (Settings → Appearance) and the page on a phone.
- **The two links that need your input** are in `index.html` → the `Elsewhere` block. Right now it
  points at GitHub and issues only. Add an email or LinkedIn if you want inbound.

---

## The design system

`styles.css` is built from the **`claude`** pack in
[awesome-design-md](https://github.com/VoltAgent/awesome-design-md) (local copy:
`D:/AICODING2/Awesome-Design-md/design-md/claude/DESIGN.md`). Pack slug: `claude`; upstream collection:
<https://github.com/VoltAgent/awesome-design-md>.

The pack is an inspired analysis of a public site, not an official brand system — hence no logos, no
proprietary webfonts, and no claim of affiliation. Tokens are taken verbatim; the substitutions are
documented in the CSS comments:

| From the pack | How it is used here |
|---|---|
| cream canvas `#faf9f5`, ink `#141413` | the page floor and all display text |
| coral `#cc785c` | eyebrows and the single accent rule — **not** body links |
| `#a9583e` (the pack's documented `primary-active`) | body links, because coral on cream is 2.9:1 and fails WCAG AA |
| serif display at weight 400, negative tracking | `h1`, lead, ledger titles, project summaries |
| humanist sans body | all running text |
| mono (JetBrains Mono) | **data only** — the formula, metrics, dates |
| dark surfaces `#181715` / `#252320` | the framing panel, and dark mode is composed from these same documented tokens |

Two deliberate deviations, both recorded in the stylesheet:

1. **Body links use the darker `primary-active`**, not the pack's coral, for contrast.
2. **Dark mode is not in the pack.** It is composed only from that pack's documented dark surfaces, dark
   elevated surface and `on-dark` text tokens — no invented hex values.

The full pack is *not* copied into this folder on purpose: it is a third-party brand analysis, and
shipping it inside a personal site would imply an affiliation that does not exist. The tokens are
attributed in the stylesheet header and in the table above instead.

---

## Why it looks like this

The two reference sites agree on one structure, and it is not a bio:

> one sentence of identity → one short thesis stated as a position → immediately, a dated ledger of
> countable artifacts → writing with a one-line claim per link → how you work → background → contact.

Both also publish a machine-readable twin; `index.md` and `llms.txt` are that.

Three deliberate omissions, copied from their judgement rather than their style:

- **No job title in the first screen.** "Twenty-five years turning enterprise process into systems"
  says more than the title line on a CV.
- **No cards, no icons, no badges, no hero image.** Type does the work; `styles.css` is 7 KB because
  there is nothing to hide.
- **No "About me" prose.** The Building ledger and the Writing list are the about-me, and they are
  checkable.

One thing I did not copy: the reference sites under-sell their background. Yours does not — the
`Before` block is deliberately the second-largest thing on the page, because 25 years across seven
industries is the part a younger candidate cannot fake.
