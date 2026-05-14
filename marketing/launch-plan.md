# Statedoku — Launch plan (May 25 → June 1, 2026)

> **Reality check first.** You'll likely have 0–10 visits per day during the first
> week. That's normal. The point of this week is not traffic — it's to seed
> credibility, capture early emails on `/launch/`, and have your accounts/posts
> ready so that **launch day** (Monday June 1) compounds.

---

## 🎯 The two pages

- **`/launch/`** — coming-soon page with email signup. Bot tweets link here.
  Marketing posts (Twitter, Reddit) link here during prelaunch week.
- **`/`** — full game (already live). "Sneak peek" link in `/launch/` header
  for the curious. The bot will switch to linking here on June 1.

---

## 📅 Daily orders

### Mon May 25 — D-7 · Soft teaser
- **9:00 ET**: Bot auto-posts (✅ already configured, no action)
- **Manual (5 min)**: Follow 30 niche accounts from `strategic-accounts.md`. Like 5 of their recent tweets.
- **Goal**: 0–5 followers. That's success.

### Tue May 26 — D-6 · Format viral test
- **9:00 ET**: Bot auto-posts
- **Manual (5 min)**: Post manually an emoji-grid screenshot, **no link**, just:
  ```
  Statedoku 🗺️ 26/05
  🟩🟩🟩
  🟩🟥🟩
  🟩🟩🟩
  ```
  Reply to any comment with "June 1 ↗".
- **Goal**: Spark curiosity. 1 reply = win.

### Wed May 27 — D-5 · Visual quiet day
- **9:00 ET**: Bot auto-posts (now in "NEAR" tone — hints we're close)
- **Manual (10 min)**: Post one US-geography fun fact in a punchy tweet:
  > "Only 4 states begin with the letter A. Can you name them?"

  No link. Pure engagement bait. Reply to anyone who tries.
- **Goal**: 50+ impressions, 5 replies.

### Thu May 28 — D-4 · Reddit awareness (manual, no automation)
- **9:00 ET**: Bot auto-posts
- **Manual (30 min)**: Post the **prelaunch Reddit drafts** (`reddit-drafts.md`):
  - 1 post in **r/SideProject** ("Daily US-states puzzle launching June 1 — coming-soon page open")
  - 1 post in **r/geography**
- **Stagger** posts 3+ hours apart. Link → `/launch/` (not `/`)
- **Reply** to the first 5 comments on each within the first hour.
- **Goal**: 20–100 email signups if a post catches. Otherwise 0. Both are fine.

### Fri May 29 — D-3 · DM round
- **9:00 ET**: Bot auto-posts
- **Manual (15 min)**: DM every account that liked/replied to your posts this week. Just:
  > "Hey — coming-soon page is up if you want first dibs Monday. statedoku.com/launch"
- **Goal**: 10 DMs out, 3 signups back.

### Sat May 30 — D-2 · Visual proof
- **9:00 ET**: Bot auto-posts (countdown — explicit "June 1")
- **Manual (10 min)**: Post a constraint pair as a teaser:
  > "Today's intersection: Pacific coast × Borders Mexico = California. There are 99 more like this. June 1."
- **Goal**: 1 quote-tweet from a micro-influencer would be huge.

### Sun May 31 — D-1 · Final assets
- **9:00 ET**: Bot auto-posts ("LAUNCH TOMORROW")
- **Manual (30 min)**:
  - Draft your **Show HN** post in a doc (title: `Show HN: Statedoku – daily US states puzzle`)
  - Draft your **Product Hunt** submission
  - Verify Twitter Card preview of `statedoku.com` with `https://cards-dev.twitter.com/validator`
- **Goal**: All assets ready to fire Monday morning.

### Mon June 1 — D-0 · LAUNCH 🚀

**8:00 ET** — Flip the bot to launch phase:
```bash
cd bot
# Edit src/worker.js → change PHASE = 'launch'
wrangler deploy
```

**8:30 ET** — Submit **Show HN** post to Hacker News
**8:30 ET** — Submit to **Product Hunt**
**8:45 ET** — Post the launch tweet (one tweet, not a thread — clean direct message):
> "Day #1 of @Statedoku is live 🇺🇸 Daily US-states puzzle. Free, no signup, daily reset. statedoku.com"
**9:00 ET** — Post your **3 Reddit launch posts** (different from D-4 ones, see `reddit-drafts.md`)
**Throughout the day** — Reply to every comment, tweet, DM in <15 min.
**End of day** — Post a "thanks for Day #1 — Day #2 drops at midnight" recap tweet.

**Goals (realistic)**:
- 100–500 page visits
- 20–100 puzzles completed
- 3–10 emoji-grid shares
- 5–20 new email subscribers (on top of those captured at `/launch/` pre-launch)

---

## ⚙️ Setup checklist (do BEFORE May 25)

- [ ] **Bot Twitter deployed** with `PHASE = 'prelaunch'` and `LAUNCH_DATE = '2026-06-01'` (✅)
- [ ] **Bot cron**: 2 posts/day in prelaunch (`0 13 * * *` + `0 23 * * *`) (✅)
- [ ] **Test a bot post manually** before May 25:
  ```bash
  cd bot
  wrangler deploy
  curl "https://statedoku-twitter-bot.YOUR_ACCOUNT.workers.dev/?key=YOUR_KEY&dry=1"
  ```
- [ ] **Email worker deployed** (✅ done)
- [ ] **`/launch/` page live** — check https://statedoku.com/launch/ renders, the form submits, you receive yourself a test email tomorrow at noon NYC.
- [ ] **OG image** renders in Twitter Card Validator + Facebook Sharing Debugger for BOTH `/` and `/launch/`
- [ ] **Search Console** has the sitemap submitted

---

## 🎯 What NOT to do

- ❌ **No "I built this" thread**. The story-of-the-build angle is not the play. Lead with the product, not the journey.
- ❌ Don't run paid ads.
- ❌ Don't post identical text on multiple subreddits — Reddit shadowbans for that.
- ❌ Don't tag huge accounts (>1M followers).
- ❌ Don't change the puzzle algorithm during launch week. Whatever ships May 25 = what ships June 1.

---

## 📊 Honest expectations

| Day | Visits | Signups (/launch/) | Followers |
|---|---|---|---|
| May 25 | 0–5 | 0–2 | 0–3 |
| May 26 | 0–10 | 0–3 | 0–5 |
| May 27 | 5–20 | 1–5 | 2–10 |
| May 28 | 10–200 *if Reddit hits* | 5–50 | 5–30 |
| May 29 | 5–30 | 2–10 | 2–10 |
| May 30 | 10–50 | 3–15 | 5–15 |
| May 31 | 20–80 | 5–25 | 10–25 |
| **June 1 LAUNCH** | **100–1000** *if HN hits* | 10–80 | 30–200 |

Plan for 30 days, not 1 day. Day 1 traction matters less than whether you keep posting on day 30.
