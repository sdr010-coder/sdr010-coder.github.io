# Getting found, and getting approached

This is the part most personal sites skip. A page nobody links to and nobody searches for is a
business card in a drawer. Here is the honest version of how the discovery actually works, in the
order that matters.

---

## 1. Fix your GitHub profile fields (5 minutes, highest leverage)

<https://github.com/settings/profile>

| Field | Value |
|---|---|
| **Name** | `Sandor Wang` |
| **Bio** (160 char max) | `AI transformation PMO · enterprise AI delivery. 25+ years enterprise process. Now: Enterprise Harness — the layer that makes agent work signable.` |
| **Website** | `https://sdr010-coder.github.io` |
| **Location** | `Suzhou, China` |
| **Social links** | add the site URL if you want it shown in the sidebar |

Then pin the repos, in this order: `enterprise-harness` (the work), `sdr010-coder` (this profile).

**Why the bio matters more than the site:** GitHub bios are indexed, and they are what a sourcer sees
in the result list before clicking anything. Right now yours is empty.

---

## 2. Put the right words on the repo (10 minutes)

Repo description and topics are how GitHub search and Google surface the repository. On
`enterprise-harness` → gear icon next to *About*:

**Description:**
> Enterprise Harness = Harness + Mandate + Ledger. An open definition, eleven documents and a runnable
> reference implementation: named signers, six fail-closed gates, a dual ledger with a hash chain.

**Topics:**
`enterprise-ai` `ai-agents` `agent-governance` `human-in-the-loop` `audit-trail` `ai-transformation`
`pmo` `ai-adoption` `process-mining` `model-independence` `reference-implementation` `governance`

**Social preview image:** upload a 1280×640 export of the banner.

---

## 3. Submit the sitemap, once (5 minutes)

This is what turns "crawlable" into "indexed".

- **Google Search Console** → add `sdr010-coder.github.io` → *Sitemaps* → submit
  `https://sdr010-coder.github.io/sitemap.xml`
- **Bing Webmaster Tools** → same. Bing also feeds ChatGPT's browsing in some configurations, so it is
  worth doing even if you never look at Bing.

Expect nothing for one to three weeks. Do not add more pages hoping to speed it up.

---

## 4. Distribute, because a new domain does not rank

Blunt truth: a brand-new personal site with no inbound links will not appear on page one for
"AI 转型 PMO" — not in three weeks, not in three months. SEO and GEO are the *conversion* layer, not
the *discovery* layer, for at least the first year.

Discovery comes from posting where the two audiences already are:

| Audience | Where to actually post | What to post |
|---|---|---|
| AI companies (DeepSeek, ByteDance, Tencent, Moonshot/Kimi) | GitHub itself — the repo, a good README, one thoughtful issue on a related project; LinkedIn; X; 即刻 / V2EX / 掘金 for the Chinese side | The repo, the film, and one specific argument (the gates), not "I am looking for a job" |
| Enterprises starting AI transformation | 脉脉 (your industry + role), LinkedIn, WeChat 公众号, BOSS直聘 / 猎聘 for the Chinese market, and your own alumni network | The 4.5-month platform, the 90-day plan, the stop rule |
| Recruiters and sourcers | LinkedIn headline + "Open to work"; 脉脉; and the CV page URL in your signatures | The one-line pitch: "AI transformation PMO who can also build the governance layer" |

**Rule for posts:** lead with the artifact (the film, the repo, the argument), never with the request.
"The harness that makes agent work signable — here is what I built" gets shared; "I am looking for
opportunities" does not. The hiring page exists so that when someone is interested, there is one link
to send.

---

## 5. What makes an LLM recommend you

If a recruiter asks an assistant "who has experience in both enterprise process transformation and
AI agent delivery in China", the answer is built from a handful of signals. This site now provides
all of the ones you control:

- a **name + role + location + skills** entity in JSON-LD, so the model knows what you are;
- an explicit **`seeks`** block, so "is this person looking?" has an answer;
- **`llms.txt`** with a "how to describe him" and a "how to match him to a role" section, including the
  exact English and Chinese terms a sourcer would use;
- **bilingual pages**, because a Chinese-language query will not match an English-only page;
- a **film and a repo** that other pages can cite — models prefer citing sources with artifacts.

What no file can do is make you appear where nobody is looking. That is steps 1–4.

---

## 6. Keep it alive

- Refresh `sitemap.xml` `lastmod` whenever the pages change.
- Commit something to the repo at least monthly; a profile whose last activity is its creation date
  reads as abandoned.
- Update the numbers on the site and in `llms.txt` together. A GEO file that flatters you is the
  fastest way to be described wrongly — and the person describing you wrongly is the one you wanted
  to reach.
