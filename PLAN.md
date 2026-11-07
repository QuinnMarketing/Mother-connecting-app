# Mother Connecting App — Product & Build Plan

_Working title: "Village" (placeholder — naming TBD)_

## 1. Vision

A safe, judgement-free space where mothers can ask anything about their children — skin rashes, conditions, sleep, feeding, development, behaviour, or "is this normal?" — and get answers from other mothers who have **been through the same thing**.

The product's core differentiator is **tone**. Facebook groups, Reddit and forums already have the information; what they lack is safety. Mothers get shamed, lectured, or piled on. This app is designed from the ground up so that hostility is hard to post, easy to remove, and never rewarded.

### Guiding principles
1. **Kindness by design** — the product mechanics (not just the rules) discourage judgement.
2. **Lived experience first** — answers are framed as "what worked for us", not "what you should do".
3. **Safe, not medical** — the app supports and connects; it never replaces a GP, nurse or emergency services, and says so clearly at the right moments.
4. **Privacy for mothers and children** — anonymity is available, children's photos are protected.

---

## 2. Target users

| Persona | Need |
|---|---|
| **New mum (0–12 months)** | Overwhelmed, many "is this normal?" questions, often at 3am. Fears judgement most. |
| **Experienced mum** | Has been through it; wants to help and feel valued. Becomes the core answerer. |
| **Mum of a child with a condition** (eczema, allergies, reflux, ADHD, autism, etc.) | Wants to find others on the same journey; long-term community. |
| **Expecting mum** | Preparing; light usage until birth, then becomes a new mum. |

Initial market: **Australia**, then English-speaking markets (NZ, UK).

---

## 3. Core features

### MVP (v1)

**Onboarding**
- Sign up (email / Apple / Google), verified phone number to deter trolls and duplicate accounts.
- Optional profile: display name or **anonymous mode**, children's age ranges (not names/birthdates), topics of interest, rough region (state only).
- Mandatory "Community Promise" acceptance — short, human, 4–5 points (e.g. "I share experience, not judgement").

**Ask a question**
- Title + description, topic tag (Skin, Sleep, Feeding, Health & Conditions, Development, Behaviour, Mum's wellbeing, Other), child age range.
- **Post anonymously** toggle per question.
- **Similar questions** shown while typing, so mums find existing answers instantly.
- Optional photos (see Photo Safety, §5).

**Answer**
- Answers prompted with "Share your experience…" framing.
- **"Been there" badge** — answerer marks that they experienced the same situation.
- **Kindness check** (AI) before posting — if a reply reads as harsh, shaming or preachy, the user gets a gentle nudge: _"This might come across as judgemental. Want to rephrase?"_ with a suggested softer version. They can still edit; flagrant abuse is blocked.

**Reactions — positive only**
- "Helpful", "Hugs", "Same here". **No downvotes, no public dislike counts.**
- Question asker can mark answers "This helped me".

**Feed & discovery**
- Home feed filtered by child's age and chosen topics.
- Search across all questions.
- "Unanswered" tab to channel experienced mums to people who need help.

**Safety**
- Report / block / mute on every post and profile.
- Health red-flag detection (see §5) surfaces urgent-care guidance.
- Clear "Not medical advice" banner on Health & Skin topics.

**Notifications**
- Answers to my question, replies to my answer, "someone found your answer helpful".

### Phase 2

- **Circles** — ongoing groups by condition (e.g. "Eczema Mums", "Reflux Babies") or life stage ("Born March 2026").
- **Opt-in private messaging** between mums (off by default, request-to-chat only).
- **Verified experts** — maternal & child health nurses, GPs, lactation consultants, psychologists get a verified badge; "Expert answered" highlighting.
- **Expert Q&A sessions** (scheduled AMAs).
- **Saved / bookmarked** answers and personal "journey" notes.
- Local area connections (suburb-level meetups) — opt-in only.

### Phase 3

- Curated resource library, built from top-rated answers and expert content.
- Premium tier / partnerships (see §9).
- Web app version for SEO (public, anonymised, text-only Q&A pages).

---

## 4. The anti-hostility system

This is the heart of the product, so it gets its own section.

| Layer | Mechanism |
|---|---|
| **Design** | No downvotes; no follower counts; no "top commenter" leaderboards that reward hot takes; experience-framed answer prompts. |
| **Before posting** | AI kindness check nudges rewording; hard-blocks slurs, abuse, harassment. |
| **After posting** | One-tap reporting; auto-hide after N reports pending review; AI flags borderline content to the moderation queue. |
| **Human moderation** | Small paid moderation team + trusted volunteer "Village Guides" (long-standing, high-helpfulness members). |
| **Consequences** | Graduated: gentle warning → temporary posting pause → removal. Transparent to the user. |
| **Positive reinforcement** | Helpful badges, "thank you" notifications, monthly "kindest answers" highlights. |
| **Asker controls** | Question asker can hide replies on their own post and close their question. |

---

## 5. Safety, privacy & health guardrails

### Medical / urgent-care guardrails
- AI scans questions for red-flag symptoms (e.g. difficulty breathing, non-blanching rash, fever in a baby under 3 months, unresponsiveness, dehydration signs). If detected, show a prominent banner **before** the post goes live: _"This could need urgent attention — call 000 or Healthdirect on 1800 022 222."_
- Mental-health detection for mums (postnatal depression, self-harm language) → gentle surfacing of **PANDA (1300 726 306)**, Lifeline (13 11 14), and moderator alert.
- Permanent, friendly disclaimers on health topics. The app does not diagnose.

### Photo safety (critical for skin questions)
Children's photos are the highest-risk content in the app.
- Photos only visible to **logged-in, verified members** — never public, never indexed.
- Strip EXIF/location metadata on upload.
- In-app **crop & blur tool** encouraged before upload; guidance to show only the affected area, no faces or nudity.
- Automated scanning for nudity / child sexual abuse material (e.g. a hash-matching service such as PhotoDNA, plus a nudity classifier); any nudity blocked before publication.
- Screenshot deterrence where the OS allows; watermark with viewer ID is an option.
- Photos auto-expire or can be deleted by the poster at any time.

### Privacy
- Health information about children is **sensitive information** under the Australian Privacy Act 1988 — explicit consent, minimal collection, clear privacy policy.
- Store data in an Australian region (e.g. Sydney).
- No children's names, birthdates or schools collected. Age ranges only.
- Anonymous posts are anonymous to other users (moderators can still see the account for safety).
- Account deletion and data export available in-app.
- Comply with eSafety Commissioner obligations under the Online Safety Act (complaints handling, removal of harmful content) and app store child-safety policies.

### Who can join
The brief describes a space for women/mothers. **Get legal advice before restricting membership by sex or gender.** In Australia, _Tickle v Giggle for Girls_ (Federal Court, 2024) found a women-only app had unlawfully discriminated on the basis of gender identity. A safer framing is **"a community for mothers and primary carers"** with behaviour-based moderation, rather than identity-based gatekeeping.

---

## 6. Recommended tech stack

| Area | Choice | Why |
|---|---|---|
| Mobile app | **React Native + Expo** (TypeScript) | One codebase for iOS & Android; fast iteration; web later via Expo web. |
| Backend | **Supabase** (Postgres, Auth, Storage, Realtime, Edge Functions) — Sydney region | Fast to build, row-level security for privacy, scales to Phase 2. |
| Search | Postgres full-text search → later pgvector for "similar questions" semantic search | No extra service at MVP. |
| AI moderation & kindness check | LLM API (e.g. Claude Haiku for fast, low-cost classification + rewrite suggestions) via Edge Functions | Nuanced tone detection beyond keyword filters. |
| Image safety | Hash-matching + nudity detection service, EXIF stripping on upload | Protect children. |
| Push notifications | Expo Notifications | Built-in. |
| Analytics | PostHog (privacy-friendly, can self-host/EU) | Product analytics without selling data. |
| Admin / moderation dashboard | Next.js web app on Vercel, reading the same Supabase DB | Moderators work from a browser. |
| Error monitoring | Sentry | Standard. |

### Core data model (MVP)

```
users            id, display_name, is_verified, role (member|guide|expert|moderator|admin), region_state, created_at
children         id, user_id, age_range            -- no names/DOB
topics           id, name, slug, is_health_topic
questions        id, author_id, is_anonymous, topic_id, child_age_range, title, body, status (open|closed|hidden), created_at
question_photos  id, question_id, storage_path, scan_status, expires_at
answers          id, question_id, author_id, is_anonymous, body, been_there (bool), marked_helpful_by_asker (bool), status
reactions        id, target_type, target_id, user_id, kind (helpful|hugs|same_here)
reports          id, reporter_id, target_type, target_id, reason, status, resolved_by
moderation_events id, target_type, target_id, source (ai|user|moderator), action, notes
blocks           blocker_id, blocked_id
notifications    id, user_id, type, payload, read_at
```

---

## 7. Key screens (MVP)

1. Welcome → Sign up → Community Promise → Set up profile (children's ages, topics, anonymity default)
2. **Home feed** (For you / Unanswered / Topics)
3. **Ask** — compose, topic, age, anonymous toggle, photo + blur tool, similar-questions panel
4. **Question detail** — question, answers sorted by helpfulness & "been there", reply box with kindness check
5. Search
6. Notifications
7. Profile & settings — privacy, anonymity default, blocked users, delete account
8. Report flow
9. Urgent-care / support resources screen
10. _(Web)_ Moderation dashboard — queue, user history, actions

---

## 8. Delivery roadmap

| Phase | Duration (est.) | Outcomes |
|---|---|---|
| **0. Discovery** | 2–3 weeks | 10–15 interviews with mums; name & brand; community guidelines drafted; legal review (privacy, membership, health disclaimers); clickable Figma prototype. |
| **1. MVP build** | 10–12 weeks | Features in §3 MVP; moderation dashboard; AI kindness check + red-flag detection; photo safety pipeline. |
| **2. Closed beta** | 4–6 weeks | 100–300 hand-picked mums (seed with experienced "Village Guides" so every question gets answered quickly); iterate on tone and moderation. |
| **3. Public launch (AU)** | — | App Store / Google Play; marketing via mum influencers, maternal & child health networks, parenting pages. |
| **4. Phase 2 features** | +3–4 months | Circles, DMs, verified experts, AMAs. |

**Team (lean):** 1 product/design lead, 2 full-stack/mobile engineers, 1 part-time community manager/moderator (scales up at launch), legal/privacy advisor (contract), medical advisor (e.g. MCH nurse or GP, contract) to review health guardrails.

---

## 9. Business model options

- **Free core forever** — asking and answering must never be paywalled.
- **Premium (optional):** expert Q&A access, unlimited saved journeys, ad-free.
- **Partnerships:** trusted, vetted brands and health services (clearly labelled, never disguised as advice).
- **Grants / health partnerships:** perinatal mental-health and child-health organisations.
- Avoid: selling data, targeted ads based on health info.

---

## 10. Success metrics

- **Time to first helpful answer** (target: < 2 hours median at launch).
- % questions with ≥1 answer marked helpful.
- **Hostility rate:** reports per 1,000 posts; % of content removed; kindness-nudge acceptance rate.
- Member sentiment survey: "I feel safe asking questions here" (target ≥ 90% agree).
- D30 retention; % of members who have both asked and answered.

---

## 11. Key risks & mitigations

| Risk | Mitigation |
|---|---|
| Harmful medical misinformation | Red-flag escalation, health disclaimers, expert badges, moderators remove dangerous advice (e.g. anti-medical claims). |
| Children's images misused | Members-only, scanning, blur tool, no faces/nudity, EXIF strip, expiry. |
| Community turns hostile as it grows | Design-level anti-hostility, AI pre-check, Village Guides, graduated sanctions. |
| Empty community at launch ("cold start") | Seed with Guides in closed beta; launch in one region/niche first (e.g. eczema & skin). |
| Legal / regulatory | Early legal review of privacy, eSafety obligations, membership rules. |
| Moderation cost | AI triage first, human review for edge cases; volunteer Guides program. |

---

## 12. Open questions for the team

1. App name and brand feel?
2. Membership: mothers only, or mothers and primary carers? (see §5 legal note)
3. Launch niche: broad from day one, or start with a focused topic (e.g. skin & eczema)?
4. Budget and target launch date?
5. Do we have medical/expert partners already?
6. Is a web version needed at launch, or mobile-only?

---

## Next steps

1. Answer the open questions above.
2. Run discovery interviews and draft community guidelines.
3. Build the clickable prototype of the Ask → Answer → Kindness check flow.
4. Set up the repo (Expo + Supabase) and start the MVP build.
