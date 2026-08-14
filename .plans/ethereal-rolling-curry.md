<!-- Saved from the cloud session so it survives the container.
     On desktop: cp .plans/ethereal-rolling-curry.md ~/.claude/plans/
     HANDOFF-phase2.md is the compact working version of the same thing. -->

# thehumanorigin.org — recognise & book stress test

> **Phase 1 shipped** as commit `e996201` on `claude/thehumanorigin-refinement-stress-test-qxiayc` — recognition block, booking on all 22 pages, nav rework, offer ladder, structured data. Everything below the "Phase 2" heading is the new work.

---

# Phase 2 — length, flow, and conversion architecture

## Context

A length audit of the English content pages found 6,802 words / 34 minutes, concentrated badly: The Leadership Table alone is 1,605 words (8 min), of which the FAQ is 619 — 48% of the body. Four defects are outright:

- **€617B is printed twice**, seven lines apart (`en/leadership-table/index.html:202` hero deck, `:209` stat strip).
- **Seven statistics across two competing blocks.** The Zak 2017 oxytocin figure is the weakest citation on the site — that literature has known replication problems, and on a page built on scientific grounding one shaky number drags down the credible ones.
- **The AI section (109 words) is redundant twice over** — the new opening block already claims "the one thing no system copies," and The Original page covers it at length.
- **The hero lead repeats near-verbatim 700 words later** ("isn't the plan on the wall — it's what the people can and can't say out loud").

Tom then supplied a 7-part direct-response framework (Hook → False Belief → Mechanism → Root Cause → Cost of Inaction → Proof → CTA) and asked that the copy be refocused on **why clients are stuck now and will stay stuck**. Mapping the framework onto the page shows it already carries five beats and is missing the two that create urgency: it never names what the reader is doing wrong right now, and its cost section is static and EU-wide rather than compounding and theirs.

Answers to the framework's seven questions were derived from Tom's own site and confirmed, except proof: **confidentiality stays absolute** — no logos, no case studies, no names, ever. Step 6 is therefore built from the research base, the film craft, and the confidentiality promise itself, which is reframed as the proof rather than worked around. No client evidence is invented.

Net effect on The Leadership Table: roughly 1,605 → ~1,350 words. The framework does not only shorten — it reallocates, cutting filler and spending the savings on urgency.

---

## Original context (Phase 1)

You asked me to stress-test whether your service is **fast to recognise** and **easy to book**, then refine. I audited all 22 pages (11 EN / 11 DE) at the latest commit (`b47b7c7`, 2026-08-12). The funnel leaks at both ends.

**Recognition — a visitor cannot tell what you do.** The homepage never names the service: it opens with "Where every human pattern begins", then goes straight into biography. Every commercial fact (3–4 weeks, €12,000, the 45-minute entry conversation) lives two clicks deep, ~1,300 words into `/en/leadership-table/`. No `Service`/`Offer` structured data, so search and AI answer engines had nothing to read the offer from.

**Booking — there was almost nowhere to book.** `cal.eu` appeared on **2 of 11 EN pages**, both times as the *secondary* ghost button next to a primary that sent people back into a quiz. **Zero** booking or contact on homepage, Two Doors, Essence, Presence, Inner Pulse, Two Pulses, The Original — 7 of 9 content pages. The Leadership Table's closing CTA, the highest-intent moment on the site, offered only two more quizzes. The whole personal track named its offers — talks, circles, couples work — with no way to enquire at all. No footer contact anywhere.

## Phase 1 changes — SHIPPED in `e996201`

24 files changed, +289/−88. Committed and pushed. The HTML is now the source of truth for all of this; the notes below are the record of intent.

- **All 22 pages:** footer contact row (`.fbook`) with booking link + `tom@thehumanorigin.org`; a nav booking affordance; `@media(min-width:821px) and (max-width:1100px){.nl{gap:18px}}` so the nav never overflows.
- **`leadership-table` / `fuehrungstisch`:** closing CTA now leads with booking (primary), Pulse Check demoted to ghost, mailto fallback beneath.
- **`pulse-check` / `pulscheck`:** results screen promotes booking to primary with "45 minutes, no fee, no pitch" beneath it.
- **`inner-pulse` / `innerer-puls`:** new "If you want it held" route — talks, circles, couples, one-to-one — with a mailto. This track had no exit at all before.
- **`essence`, `presence`, `two-doors`, `original`** (both languages): enquiry line under each closing CTA.
- **`two-pulses` / `zwei-pulse`:** "Rather skip the reading? Book the entry conversation instead."
- **Homepages:** hero recognition line, second CTA, an offer ladder, `Service` + `Offer` JSON-LD, reclaimed hero spacing.
- **`llms.txt`:** new "How to start (booking)" section. **`sitemap.xml`:** 19 `lastmod` bumped to 2026-08-13.

Verified: HTML nesting + JSON-LD clean on 23 files, 0 broken internal links, booking reachable from nav and footer on 22/22, no nav overflow at 1440/1100/960/860/700/390. Horizontal overflow at 960/860 is pre-existing (decorative `.wash w1`, contained by `overflow-x:hidden`) and identical before/after.

---

## Phase 1 detail — ALL SHIPPED, do not redo

### 1. The opening block — one compact statement, adapted per page

Replaces the `.whatis` line now in the hero. One block, no sub-headings, sitting between the subtitle and the poetic lead so it reads before anything else. Voice pulled toward The Original: short declaratives, the survival behaviours named outright, and the incubator/cancer history carried as the credential — the reason the reading is from the inside rather than from a framework.

Six pages: both homepages, `leadership-table` / `fuehrungstisch`, `two-doors` / `zwei-tueren`.

The original/unique power — the capacity the pattern buries, and the one thing no system copies — runs through all three, weighted heaviest on the homepage and reduced to a single clause on the section pages.

#### Homepage — EN
> **Not coaching. Not training. Not therapy.** Under pressure, people and organisations fall back on what once kept them safe — performing, controlling, going quiet. What that costs is the original: the reading of a room before a word is spoken, the making no machine can be trained on, the person the output came from. I see the pattern sitting on top of it, and I work where that pattern runs — in real rooms, real decisions, real bodies. I had to build my own regulation from nothing: incubator, then cancer, before I was two. So I read it from the inside, not from a manual. **For everyone. Especially those who lead, and those brave enough to look at themselves.**

#### Homepage — DE
> **Kein Coaching. Kein Training. Keine Therapie.** Unter Druck fallen Menschen und Organisationen auf das zurück, was sie einmal sicher gehalten hat — inszenieren, kontrollieren, verstummen. Was das kostet, ist das Original: das Lesen eines Raums, bevor ein Wort fällt, das Machen, auf das keine Maschine trainiert werden kann, der Mensch, aus dem das Ergebnis kam. Ich sehe das Muster, das darüberliegt, und ich arbeite dort, wo es läuft — in echten Räumen, echten Entscheidungen, echten Körpern. Meine eigene Regulation musste ich aus dem Nichts bauen: Inkubator, dann Krebs, noch vor meinem zweiten Geburtstag. Deshalb lese ich es von innen, nicht aus einem Handbuch. **Für alle. Besonders für die, die führen, und die mutig genug sind, sich selbst anzusehen.**

The two section pages do **not** repeat this. They get a swift version: the credential compressed to a clause — *"a nervous system I had to build from nothing"* — so it registers without retelling the story, one line of the original power, then a close naming what the reader gets on that page and at what depth.

#### The Leadership Table — EN
> **Not coaching. Not training. Not a workshop.** I read what a leadership table can't say out loud — with twenty-five years of film craft, and a nervous system I had to build from nothing. Underneath the pattern sits the one thing no system copies: people who can read a room and make the real call. **What follows: the cost, the method, and how the work truly runs — a level beneath where meetings usually reach.**

#### Der Führungstisch — DE
> **Kein Coaching. Kein Training. Kein Workshop.** Ich lese, was ein Führungstisch nicht aussprechen kann — mit 25 Jahren Filmhandwerk und einem Nervensystem, das ich mir aus dem Nichts bauen musste. Unter dem Muster liegt das Einzige, was kein System kopiert: Menschen, die einen Raum lesen und die echte Entscheidung treffen. **Was jetzt kommt: die Kosten, die Methode und wie die Arbeit wirklich läuft — eine Ebene unter der, die Meetings sonst erreichen.**

#### Two Doors — EN
> **Not therapy. Not coaching. Not a curriculum.** I read the pattern where it actually lives — in the body that learned it — and I know it's buildable, because I had to build mine from nothing. What the pattern buried is the original you — never lost, only trained out. **What follows: two doors, how to tell which one is yours, and how the way back truly runs — in the body, not the idea of it.**

#### Zwei Türen — DE
> **Keine Therapie. Kein Coaching. Kein Lehrplan.** Ich lese das Muster dort, wo es wirklich lebt — im Körper, der es gelernt hat — und ich weiß, dass es baubar ist, weil ich meines aus dem Nichts bauen musste. Was das Muster verschüttet hat, ist das Original in Ihnen — nie verloren, nur aberzogen. **Was jetzt kommt: zwei Türen, woran Sie erkennen, welche Ihre ist, und wie der Weg zurück wirklich läuft — im Körper, nicht in der Vorstellung davon.**

*"nur aberzogen"* deliberately picks up the line already closing Das Original — *"Es ging nie verloren. Es wurde aberzogen."*

**Styling.** Reuses the existing `.whatis` rule — lime left border, 15px, `line-height:1.6`, max-width 530px — with the opening "Not…" clause in lime bold and the closing sentence in `--cream` so the audience/expectation line carries weight. On the homepage the block runs ~5 lines against ~3 today, so trim hero `padding-top` 168→150 and `.lead` margin-bottom 28→24 to hold the CTA near the fold, then re-measure. On the two section pages it is two lines, so their heroes need no adjustment.

**Preview.** After building it I'll capture the six pages at 1440 and 390 and send the screenshots, so you can see the block in place before anything is committed.

### 2. Nav rework — Pulse Check keeps the pill, Book becomes a text link

Revert the pill to **Pulse Check / Pulscheck** and standardise its target to the chooser (`/en/two-pulses/`, `/de/zwei-pulse/`) on all 22 pages — today imprint and privacy point at `/en/pulse-check/`, and the chooser page self-links. Add booking as a plain nav link before the EN/DE switch.

Width problem: five text links + a pill + logo needs ~1010px, overflowing between 821px (hamburger takeover) and ~1010px. **Fix — drop the redundant "The Human Origin" nav item;** the logo immediately to its left already links to `/en/`. That frees ~105px, landing the nav at ~890px, inside the existing `gap:18px` band, and lets the label keep full brand voice — **"Book a conversation" / "Gespräch buchen"**. Cost: the homepage loses its `.on` nav marker, which is normal when the logo is the home link.

Verify: `nav.scrollWidth === nav.clientWidth` at 821, 860, 900, 950, 1000, 1100, 1440.

### 3. Homepage ladder — free steps only

Cut rows 03 and 04 from "The work, plainly". Keep 01 Pulse Check (3 minutes, online, nothing stored — **Free**) and 02 Entry conversation (45 minutes, one question, the real one — **No fee**). Replace the dropped rows with one line pointing onward to the 3–4 week diagnostic and Origin Work, with costs and scope set out in full on The Leadership Table. Keep the booking button and the "or read the full path" link.

`€12,000` then appears only on the Leadership Table page and in `llms.txt`, as before. Leave the `Offer` nodes in the homepage JSON-LD — machine-readable pricing helps answer engines and is not on-page copy.

### 4. Mobile hero density

The hero CTA sits at 1.54× the fold on a 390×844 phone (1.38× before this work). The mobile rule is `@media(max-width:820px){.hero{padding-top:46vh}}`; reducing to ~40vh restores roughly the pre-change position without disturbing the portrait crop.

### 5. Confirm the booking slugs resolve

`cal.eu/tomwaldek/entry-conversation` and `.../erstgespraech` are your own pre-existing URLs. I could not reach them — this sandbox's proxy returns 403 on CONNECT for `cal.eu` and `cal.com` — though `cal.eu` does resolve via Cloudflare. Worth one manual click before deploy. Every page also carries the `mailto:` fallback, so booking never dead-ends even if a slug is wrong.

### 6. Verify, then commit — done

HTML nesting + JSON-LD across 23 files; zero broken internal links; booking reachable from nav *and* footer on 22/22; nav fits at every width from 821px up; no new horizontal overflow. Screenshots of the six edited pages at 1440 and 390.

Then one commit to `claude/thehumanorigin-refinement-stress-test-qxiayc` (exists locally and on origin, level with `main`) — *"Make the service recognisable and bookable from every page (EN+DE)"*. No PR unless you ask.

---

## One open detail

**Settled: use `Gründer:innen`.** Standing rule for all new German copy wherever the audience is named as a group. It does not currently appear anywhere on the site — the draft that carried it was superseded by the shorter section-page blocks — so this is a forward rule for the Phase 2 German, not a pending edit.

One exception: `de/index.html:153` reads "Tom Waldek · The Human Origin · **Gründer**". That is his own job title, one person, and stays masculine singular.

---

# Phase 2 — the work

## A. The Leadership Table, rebuilt on the seven beats

`en/leadership-table/index.html` and `de/fuehrungstisch/index.html`. Section order follows the framework. Copy below is English; German mirrors beat for beat, in Sie form.

### 1 · Hook — sharpen the h1
*The surprising opener that makes someone stop. If nobody stops, nothing else gets read.*

Current: *"Your strategy is rarely the problem. What goes unsaid across the table is."* — a good claim, but it is about strategy, not about the reader.

> **Your best people already know what's wrong.**
> *They decided months ago it wasn't worth saying.*

Keeps the existing hover-split h1 treatment; the second line takes the `.subtitle` slot. **Trade-off:** the current h1 carries "strategy" search intent. If that matters more than the stop, keep the old h1 and use the new line as the subtitle instead.

### 2 · False Belief — NEW SECTION
*The thing they're doing right now that's making it worse. Without this they keep doing it, even after reading you.*

> **WHAT YOU'VE ALREADY TRIED**
> **The training worked. That's the problem.**
> You ran the engagement survey. You booked the offsite. You brought in someone good, and for three weeks the room was different. Then it went back.
> It went back because none of it touched the thing deciding what gets said. It gave your people better language for what they still can't tell you. The silence didn't break. It got more professional — and harder for you to see.

Placed directly after the hero, before the stats. ~80 words.

### 3 · Mechanism — name it before the six cards
*A vague answer doesn't build trust. A named one does.*

> **THE MECHANISM**
> **Survival architecture — and how to read it.**
> Every room runs one: the hidden operating system it defaults to under pressure and rarely switches off. It decides what can be said, what gets decided, what gets risked — before anyone opens their mouth.
> I read it the way a film set taught me to. Six disciplines, one skill underneath all of them: telling what's true in a room from what's being performed for it.

Then the existing six-discipline grid (144 words) unchanged — it is the differentiator and it earns its space. This intro absorbs the old "Why a film professional reads leadership tables" block (84 words), which is deleted along with its verbatim repeat of the hero lead.

### 4 · Root Cause — tighten
*Makes the solution feel obvious rather than one more opinion.*

> **WHY IT KEEPS COMING BACK**
> **The pattern was in the room before you were.**
> The nervous system decides safe-or-not before anyone is conscious of it. That decision predates the organisation, predates your first day, usually predates your first word. Training reaches the part of a person that reflects. The pattern runs underneath it. **That's why it survives every intervention you've bought.**

~60 words, absorbing the current "The problem no one's measuring" (36) and "The Trust Cascade" (78) sections. The Frankl material (78 words, currently "Why before how") compresses to one line carried into Proof.

### 5 · Cost of Inaction — the big rewrite
*People act when staying still feels expensive. Specific: time lost, money wasted, chances missed.*

> **WHAT ANOTHER YEAR OF THIS COSTS**
> **It doesn't hold still. It compounds.**
> Every quarter the pattern runs, the people most able to tell you the truth get better at not doing it — or they leave, and you inherit the ones who never tried. Ideas reach your table at a third of the rate they could. And you find out about the real problems at the point where they have stopped being cheap to fix.
>
> **56%** — leaders who say their team doesn't surface real problems · *PMI*
> **€617B** — what work-related stress costs the EU each year · *EU-OSHA*
> **66%** — the drop in turnover when the survival pattern lifts · *Gallup*

Three statistics, all cost-framed, replacing seven. Deletes the duplicate €617B, the Zak oxytocin figure, the Gallup 21% profitability figure (generic, any competitor can cite it), and the separate "Positive proof" block (83 words) whose 7× and 3× figures fold into the prose above.

### 6 · Proof — confidentiality as the proof
*Proof removes doubt; a picture of "after" makes them want it.*

> **PROOF**
> **I have no case studies. That is the proof.**
> No logos, no names, no client stories — ever. It is the precondition for anything true getting said in the room, and I won't trade it for marketing. What I can show you is where the reading comes from: twenty-five years on film sets across six disciplines, and a century of research that arrived in the same place — Porges on how a body reads safety, Edmondson on what teams will and won't say, Frankl on meaning as the thing survival replaces, Keltner on what power does to perception. **The science confirms what the room already knew.**
> **What it looks like after:** problems reach you while they are still cheap. The quiet person at the table says the thing. You stop managing the company you wish you had and start running the one you actually have.

~140 words. This is the piece that turns the confidentiality commitment from a marketing liability into the strongest trust signal on the page.

### 7 · CTA — tighten, add the risk reversal
*One action. No hedging.*

> **Start with one question.**
> Forty-five minutes. No fee, no pitch, no follow-up unless you ask. **If the work isn't right for you, I'll tell you first.**
> [Book an entry conversation] · or start the Pulse Check

The Fit Test line currently sits only on the homepage; it belongs here, at the moment of decision.

### FAQ — nine questions to five
Drop *"How do the Pulse Check and the Inner Pulse relate?"* (the Two Pulses page exists for it), *"Is the personal work only for men?"* (belongs on Essence, not the organisational page), *"What languages and regions?"* (one footer line), and *"Do you have evidence this works?"* (now the Proof section). ~619 → ~330 words.

## B. The homepage opening block — same words, four beats

`en/index.html`, `de/index.html`. Currently one 88-word paragraph, the longest single block on the site.

> **Not coaching. Not training. Not therapy.**
> Under pressure, people and organisations fall back on what once kept them safe — performing, controlling, going quiet. It costs them the one thing no machine can copy: someone who reads a room and knows what's true in it.
> I read that pattern for a living. I had to build my own from nothing — incubator, then cancer, before I was two.
> **For everyone. Most of all for those who lead, and those honest enough to look at themselves.**

Four `<p>` beats inside `.whatis` rather than one block. Barely shorter; substantially faster to read.

## C. The differentiator line — three section pages

Approved for The Leadership Table, Two Doors and The Original, each angled to its page. Leadership Table carries the full version inside the Mechanism section (above); the other two get the one-line form:

- **Two Doors:** *One trade's entire job is telling real from performed. I spent twenty-five years in it — and then had to learn it on myself.*
- **The Original:** *One trade's entire job is telling real from performed. Twenty-five years in it is why I can tell you what a machine will never reach.*

## D. Why these choices, in one place

Recorded so the reasoning survives the next edit:

- **Processing fluency.** Text that is easier to process is judged more true and more likeable, and that judgement is made before the content is evaluated. Line breaks buy fluency at zero cost to substance — the homepage rebreak is pure fluency gain.
- **Isolation effect.** A distinctive item among similar ones is remembered; seven similar statistics cancel each other and none survives. Three do.
- **Loss aversion.** Losses weigh roughly twice equivalent gains, so cost-framed numbers move this buyer further than a mixed set of costs and benefits.
- **Concreteness.** Concrete language is recalled far better than abstract language because it recruits sensory processing, not only verbal. Every cut here removes abstraction and keeps the concrete — *incubator*, *the offsite*, *the quiet person at the table*. None of them touch the personal material, which is the site's real strength.
- **Category design.** "Consultants read your numbers. Coaches read your words. I read what a room does before anyone speaks" places the work outside both categories rather than claiming to be better inside one — the only kind of differentiation a competitor can't copy.
- **Costly signalling.** A credential that carried real risk reads as earned. So does refusing to sell case studies you could easily fake.
- **Diminishing returns on repetition.** Past the second beat, restatement stops adding emphasis and starts reading as padding. The current "The work starts there. Before strategy. Before method. At the WHY." says one thing four times.

## E. Verification

Same suite as Phase 1, plus a re-measure:

- HTML nesting and JSON-LD parse clean across 23 files; zero broken internal links; CSS braces balanced.
- Booking reachable from nav and footer on 22/22; nav fits at every width from 821px up.
- Word count per page before/after, and confirmation that no statistic appears twice on a page.
- Screenshots of the rebuilt Leadership Table (both languages) and both homepages at 1440 and 390.
- Commit to the same branch; no PR unless asked.
