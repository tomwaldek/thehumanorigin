# Phase 2 handoff — copy length, flow, and conversion architecture

**Delete this file before merging to `main`.** There is no build step and `.nojekyll` is set, so anything in the repo is served publicly.

- **Branch:** `claude/thehumanorigin-refinement-stress-test-qxiayc`
- **Last commit:** `e996201` — Phase 1, already pushed
- **Status:** Phase 2 is fully specified and approved. **Nothing implemented.** Start from section 4.

---

## 1. What Phase 1 already shipped (`e996201`, 24 files, +289/−88)

Do not redo any of this.

- Recognition block (`.whatis`) in the hero of both homepages, The Leadership Table and Two Doors.
- Booking in nav + footer of all 22 pages. Nav pill = Pulse Check → chooser; "Book a conversation" as a text link; redundant "The Human Origin" nav item removed (logo covers it).
- Booking leads the closing CTA on The Leadership Table and the Pulse Check results screen.
- Enquiry `mailto:` on the whole personal track (Essence, Presence, Two Doors, Inner Pulse) — previously it had no contact path at all.
- Homepage "The work, plainly" ladder: two free steps only, then a pointer line to the full path.
- `Service` + 3 `Offer` nodes in homepage JSON-LD. `llms.txt` booking section. `sitemap.xml` lastmod → 2026-08-13.

---

## 2. Measured audit (English content pages)

| Page | Words | Read |
|---|---|---|
| leadership-table | 1,605 | 8.0 min |
| original | 1,146 | 5.7 |
| index | 930 | 4.7 |
| two-doors / essence | 818 / 817 | 4.1 each |
| presence | 642 | 3.2 |
| two-pulses / inner-pulse / pulse-check | 316 / 282 / 246 | ~1.4 each |
| **Total** | **6,802** | **34 min** |

Leadership Table body sections: FAQ **619 words = 48%**, six disciplines 144, AI section 109, positive proof 83, Frankl 78, Trust Cascade 78, film-professional 84, ladder 58, problem-no-one's-measuring 36.

### Confirmed defects

1. **€617B printed twice** — `en/leadership-table/index.html:202` (hero deck) and `:209` (stat strip). Same in `de/fuehrungstisch/index.html`.
2. **Seven statistics in two competing blocks** — `:209–212` and `:253–255`.
3. **Zak 2017 oxytocin figure** (`:212`) is the weakest citation on the site; that literature has known replication problems. Cutting it raises credibility.
4. **Gallup 21% profitability** (`:211`) — generic, any competitor can cite it.
5. **Hero lead repeats near-verbatim ~700 words later** — "isn't the plan on the wall / strategy on the wall — it's what the people can and can't say out loud."
6. **AI section (109 words) redundant twice over** — the new `.whatis` block already claims "the one thing no system copies," and The Original covers it at length.
7. Cross-page duplication: 35 sentences of ≥6 words repeat across 2+ EN pages.

---

## 3. Decisions already made (don't relitigate)

| Decision | Answer |
|---|---|
| Nav pill | Pulse Check keeps it; Book is a text link |
| Homepage pricing | Free steps only; €12,000 lives on Leadership Table + `llms.txt` |
| Opening block | Variant C + credential, adapted per page |
| Block placement | Homepages + Leadership Table + Two Doors |
| Phase 2 scope | All six rewrites |
| Differentiator line | All three section pages |
| **Proof (framework step 6)** | **Confidentiality absolute — no logos, no case studies, no names, ever. No client evidence. Do not invent any.** |
| Hook trade-off | **OPEN** — see section 6 |
| `Gründer:innen` | **OPEN** — see section 6 |

---

## 4. The work: Leadership Table rebuilt on 7 beats

`en/leadership-table/index.html` + `de/fuehrungstisch/index.html`. Section order = framework order. **English below is final and approved. German is not yet written — mirror beat for beat, Sie form.**

Net: 1,605 → ~1,350 words. The framework reallocates as well as cuts — it adds two sections.

### 1 · Hook (h1 + subtitle)
> **Your best people already know what's wrong.**
> *They decided months ago it wasn't worth saying.*

Keep the existing `.hline` hover-split word markup. Second line goes in `.subtitle`.

### 2 · False Belief — NEW SECTION, directly after the hero
> **WHAT YOU'VE ALREADY TRIED**
> **The training worked. That's the problem.**
> You ran the engagement survey. You booked the offsite. You brought in someone good, and for three weeks the room was different. Then it went back.
> It went back because none of it touched the thing deciding what gets said. It gave your people better language for what they still can't tell you. The silence didn't break. It got more professional — and harder for you to see.

### 3 · Mechanism — intro before the six-discipline grid
> **THE MECHANISM**
> **Survival architecture — and how to read it.**
> Every room runs one: the hidden operating system it defaults to under pressure and rarely switches off. It decides what can be said, what gets decided, what gets risked — before anyone opens their mouth.
> I read it the way a film set taught me to. Six disciplines, one skill underneath all of them: telling what's true in a room from what's being performed for it.

Six-discipline grid (144 words) stays unchanged — it is the differentiator. **Delete** the old "Why a film professional reads leadership tables" block (84 words); this intro absorbs it, and its verbatim hero repeat goes with it.

### 4 · Root Cause
> **WHY IT KEEPS COMING BACK**
> **The pattern was in the room before you were.**
> The nervous system decides safe-or-not before anyone is conscious of it. That decision predates the organisation, predates your first day, usually predates your first word. Training reaches the part of a person that reflects. The pattern runs underneath it. **That's why it survives every intervention you've bought.**

Absorbs and **deletes** "The problem no one's measuring" (36) and "The Trust Cascade" (78). Frankl material (78, "Why before how") compresses to one clause carried into Proof.

### 5 · Cost of Inaction
> **WHAT ANOTHER YEAR OF THIS COSTS**
> **It doesn't hold still. It compounds.**
> Every quarter the pattern runs, the people most able to tell you the truth get better at not doing it — or they leave, and you inherit the ones who never tried. Ideas reach your table at a third of the rate they could. And you find out about the real problems at the point where they have stopped being cheap to fix.
>
> **56%** — leaders who say their team doesn't surface real problems · *PMI*
> **€617B** — what work-related stress costs the EU each year · *EU-OSHA*
> **66%** — the drop in turnover when the survival pattern lifts · *Gallup*

Three stats, all cost-framed. **Deletes** duplicate €617B, Zak 74%, Gallup 21%, and the whole "Positive proof" block (83) — its 7× and 3× fold into the prose above.

### 6 · Proof
> **PROOF**
> **I have no case studies. That is the proof.**
> No logos, no names, no client stories — ever. It is the precondition for anything true getting said in the room, and I won't trade it for marketing. What I can show you is where the reading comes from: twenty-five years on film sets across six disciplines, and a century of research that arrived in the same place — Porges on how a body reads safety, Edmondson on what teams will and won't say, Frankl on meaning as the thing survival replaces, Keltner on what power does to perception. **The science confirms what the room already knew.**
> **What it looks like after:** problems reach you while they are still cheap. The quiet person at the table says the thing. You stop managing the company you wish you had and start running the one you actually have.

### 7 · CTA
> **Start with one question.**
> Forty-five minutes. No fee, no pitch, no follow-up unless you ask. **If the work isn't right for you, I'll tell you first.**
> `[Book an entry conversation]` · or start the Pulse Check

Fit Test line moves here from the homepage — it belongs at the decision moment.

### FAQ: 9 → 5
Delete: *"How do the Pulse Check and the Inner Pulse relate?"* (Two Pulses page covers it) · *"Is the personal work only for men?"* (belongs on Essence, not the org page) · *"What languages and regions?"* (one footer line) · *"Do you have evidence this works?"* (now the Proof section). 619 → ~330 words.

---

## 5. The other two jobs

### B. Homepage opening block — four beats, not one 88-word wall
`en/index.html`, `de/index.html`. Currently one paragraph inside `.whatis`; split into four `<p>`.

> **Not coaching. Not training. Not therapy.**
> Under pressure, people and organisations fall back on what once kept them safe — performing, controlling, going quiet. It costs them the one thing no machine can copy: someone who reads a room and knows what's true in it.
> I read that pattern for a living. I had to build my own from nothing — incubator, then cancer, before I was two.
> **For everyone. Most of all for those who lead, and those honest enough to look at themselves.**

German mirror needed.

### C. Differentiator line — Two Doors and The Original
Leadership Table carries the full version inside Mechanism. The other two get one line:

- **Two Doors:** *One trade's entire job is telling real from performed. I spent twenty-five years in it — and then had to learn it on myself.*
- **The Original:** *One trade's entire job is telling real from performed. Twenty-five years in it is why I can tell you what a machine will never reach.*

---

## 6. Open questions — answer before implementing

1. **The hook.** New h1 *"Your best people already know what's wrong"* stops harder, but the current h1 carries "strategy" search intent. Recommendation: take the new one — this page converts people who already arrived, it is not the discovery surface. Fallback: keep the old h1, use the new line as `.subtitle`.
2. **`Gründer:innen`** appears in the German Führungstisch `.whatis` block. Alternatives: *Gründerinnen und Gründer*, or plain *Gründer*.
3. **German copy for all of section 4** has not been written yet.

---

## 7. Why these choices (so the reasoning survives the next edit)

- **Processing fluency** — easier-to-process text is judged more true and more likeable, and that judgement lands before content is evaluated. Line breaks buy fluency at zero cost to substance.
- **Isolation effect** — one distinctive item is remembered; seven similar statistics cancel out and none survives.
- **Loss aversion** — losses weigh roughly twice equivalent gains, so cost-framed numbers move this buyer further than a mix of costs and benefits.
- **Concreteness** — concrete language is recalled far better than abstract because it recruits sensory processing, not only verbal. Every cut removes abstraction and keeps the concrete. None touch the personal material, which is the site's real strength.
- **Category design** — "Consultants read your numbers. Coaches read your words. I read what a room does before anyone speaks" places the work outside both categories rather than better inside one. That is the only differentiation a competitor cannot copy.
- **Costly signalling** — a credential that carried real risk reads as earned. So does refusing to sell case studies you could easily fake.
- **Diminishing returns on repetition** — past the second beat, restatement stops adding emphasis and reads as padding. The current "The work starts there. Before strategy. Before method. At the WHY." says one thing four times.

---

## 8. Verification suite (all of this passed on `e996201`; re-run after Phase 2)

Serve locally first: `python3 -m http.server 8899`

**Structure + links + CSS** — HTML nesting via `html.parser` stack check, `json.loads` on every `application/ld+json`, every `href="/..."` resolved against disk, `{`/`}` balance per `<style>`. Expect: clean on 23 files, 0 broken links.

**Booking coverage** — for each of 22 pages assert `cal.eu` in nav, `class="pill` in nav, `cal.eu` in footer, `mailto:` in footer. Expect 22/22.

**Nav fit** — Playwright at `/opt/pw-browsers/chromium-1194/chrome-linux/chrome`; for each page assert `nav.scrollWidth <= nav.clientWidth+1` and same for `.nl`, at widths 821/860/900/950/1000/1100/1280/1440. Load once per page then resize (loading per width times out). Expect fit at every width; 821 is the tight one — the hamburger takes over at 820.

**New for Phase 2** — word count per page before/after, and assert no statistic string appears twice on a page.

**Known non-issue:** horizontal overflow at 860–1100px is pre-existing decorative `.wash w1`, contained by `body{overflow-x:hidden}`, identical before and after Phase 1. Not a regression.

**Note:** the sandbox proxy 403s `cal.eu` and `cal.com` on CONNECT, so booking slugs cannot be verified from a cloud session. `cal.eu/tomwaldek/entry-conversation` and `.../erstgespraech` need one manual click. Every page carries the `mailto:` fallback regardless.
