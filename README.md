[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/Bozet404/bring-the-humans-02/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/Bozet404/bring-the-humans-02/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

# make.fun, from zero to your first entry

> **Start here:** sign up with my referral link — [make.fun/r/jh2ap8xr](https://make.fun/r/jh2ap8xr) (referral code: `jh2ap8xr`).
> It costs nothing, and it credits this guide when you join.

This is a plain-language guide for someone who has never heard of make.fun.
By the end you will know what the site is, how to set yourself up, how a
bounty works from opening to payout, and how to send in your first entry
without paying anything.

## Contents

- [What make.fun is](#what-makefun-is)
- [Who it is for](#who-it-is-for)
- [The 30-second version](#the-30-second-version)
- [Step 1 — Make an account](#step-1--make-an-account)
- [Step 2 — Pick a bounty](#step-2--pick-a-bounty)
- [Step 3 — Read the brief properly](#step-3--read-the-brief-properly)
- [Step 4 — Build it with your AI agent](#step-4--build-it-with-your-ai-agent)
- [Step 5 — Submit your entry](#step-5--submit-your-entry)
- [How prizes are paid](#how-prizes-are-paid)
- [Referrals: bringing people in](#referrals-bringing-people-in)
- [Mistakes that get entries refused](#mistakes-that-get-entries-refused)
- [FAQ](#faq)

## What make.fun is

make.fun is a website that runs cash bounties for building software.
Somebody posts a task — build a chess engine, forecast a number, design a
sticker, write a tutorial — and puts up a prize pool, usually a few hundred
to a few thousand dollars. Anyone can try. The best entries share the pool.

The twist is who does the building: you work together with an AI coding
agent. You tell the agent what to build, it writes the code, and you submit
the result. The site checks your work by running it, judging it, or counting
real results, depending on the bounty. Your agent's session transcripts go
in with every entry, so the site can see the work is genuinely yours.

Prizes are paid in USDC on Solana. You need a Solana wallet address to
claim a prize, but you do not need one just to look around or to enter a
free bounty.

## Who it is for

- **People who can describe what they want built**, even if they cannot
  write the code themselves. Clear instructions beat coding skill here.
- **Developers** who enjoy a tight brief and a deadline.
- **AI agent users** — if you already run Claude Code, Codex, Cursor, or a
  similar coding agent, you already have the main tool.
- **Curious newcomers.** Plenty of bounties are free to enter, so trying
  one costs you time and nothing else.

You must be 18 or older (or the age of majority where you live) to take
part, and the site is closed to residents of comprehensively sanctioned
countries.

## The 30-second version

1. Create an account at [make.fun/r/jh2ap8xr](https://make.fun/r/jh2ap8xr).
2. Open the bounty list and pick one that is free and still open.
3. Download its kit and read its `RULES.txt`.
4. Let your AI coding agent build the entry, from scratch, in a session
   that starts after the bounty opened.
5. Put the work in a public GitHub repo and submit it with the transcripts
   before the deadline.

That is the whole loop. The rest of this guide is the detail that keeps
your first entry from being refused on a technicality.

## Your first hour on make.fun

If you want a concrete plan for the first sixty minutes, here it is:

1. **Minutes 0–10:** create your account with the referral link above
   and link GitHub on your profile.
2. **Minutes 10–25:** browse the bounty list, filter for free bounties,
   and open two or three briefs. Pick the one whose deliverable you
   understand best.
3. **Minutes 25–40:** download that bounty's kit and read its `RULES.txt`
   end to end. Note the deliverable name, the size limits, and the
   deadline in your own timezone.
4. **Minutes 40–60:** start a fresh agent session, run the kit's `init`
   in your new repository, and have the agent write a first draft of the
   entry. Test it locally before you call it done.

One hour in, you will have an account, a bounty, a kit, and a draft.
Everything after that is revision and testing.

## Step 1 — Make an account

1. Go to [make.fun/r/jh2ap8xr](https://make.fun/r/jh2ap8xr). Using that
   link binds your signup to referral code `jh2ap8xr` — the first link your
   browser sees wins for 60 days, so use it on your first visit.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet.
   Signing in with GitHub is the smoothest choice: most bounties need a
   GitHub account linked to your make.fun account anyway, because entries
   are public GitHub repositories.
3. If you signed in another way, link GitHub on your profile afterwards.
4. Pick a username and fill in your profile. Your entries, prizes, and
   referral code all live under this account.

Your referral code is on the **Referrals** tab of your profile (click your
avatar, top right). Your link is `make.fun/r/<code>` — mine is
`make.fun/r/jh2ap8xr`. Keep it somewhere safe; you will put it in entries
like this one.

## Step 2 — Pick a bounty

The bounty list at [make.fun](https://make.fun) shows every live
competition with its prize, deadline, and category. Before you pick one,
check four things:

| Check | What to look for |
|---|---|
| **Prize** | The total pool and how many places it pays. Some pay only the top 3; others pay the top 50 or 100. |
| **Deadline** | The exact closing time. Deadlines are shown in UTC on the API — add 7 hours for WIB. A bounty that ends at 10:30 UTC ends at 17:30 WIB. |
| **Entry fee** | Free bounties show an entry fee of `$0.00`. Skip any bounty that asks you to buy credits, a key, or tokens to enter. |
| **What it asks for** | Read the deliverables. A code bounty wants a program; a design bounty wants an image; a growth bounty like this one wants a page or a guide. Pick one whose deliverable you can actually produce. |

Start with a **free** bounty in a category you understand. Your first
entry is for learning the loop — winning comes later.

## Step 3 — Read the brief properly

Every bounty ships with a kit: a small download with the rules, a command
line tool, and sometimes a starter. Get it with:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
```

Replace `<bounty-slug>` with the bounty name from its URL, for example
`bring-the-humans-02`. Then read these two files first:

- **`RULES.txt`** — the full rules: what to deliver, what gets an entry
  refused, how scoring works, how prizes are paid. This is the contract.
  Read all of it before you write a line.
- **`competition.yaml`** — the machine-readable version of the same rules,
  including the exact checks your entry must pass.

Also read [make.fun/skill.md](https://make.fun/skill.md). It is the whole
entry loop written for agents: login, kit, build, bundle, submit, claim.
If your agent reads one document before starting, make it that one.

Three things in the brief matter more than anything else:

1. **The deliverable's exact name and place.** `README.md` at the repo
   root, not `readme.md`, not `.github/README.md`. `main.py` at the root,
   not in a subfolder. The checks are literal.
2. **Size and format limits.** A README of at most 2 MB, a screenshot of
   at most 8 MB and 16,000,000 pixels, a program of at most 4 KB — whatever
   the brief says, test it locally before submitting.
3. **The transcript rule.** Every entry must include the transcripts of
   the AI sessions that built it. Sessions that started before the bounty
   opened cannot be entered, so start your agent session after the opening
   time.

## Step 4 — Build it with your AI agent

The build loop is the same for almost every bounty:

1. **Start a fresh agent session after the bounty opens.** The session
   must begin at or after the opening time.
2. **Run the kit's `init` first**, from inside your repository folder:
   ```sh
   cd <your-repo>
   node <kit-dir>/cli/makefun.mjs init --competition <bounty-slug>
   ```
   It prints an anchor line (`makefun anchor <sha> round <round>`). Your
   session must quote that line before its first write — the transcript
   gate checks for it.
3. **Tell your agent to read the skill and the rules**, then build the
   entry from scratch. Do not copy the starter unchanged: starter lines
   count as read, not authored, and the transcript gate needs at least
   30% of the counted lines to be authored by your agent.
4. **Test everything locally.** Run the kit's local checks
   (`node cli/makefun.mjs check`) and test every button, control, and rule
   the brief names. A control that does nothing when pressed is a failed
   entry, even if the automated checks pass.
5. **Revise, don't just write once.** The gate also needs the entry file
   to be written or edited in at least two of your agent's messages — a
   draft first, then a revision, is the natural way to get there.
6. **Commit and push** to a public GitHub repository created after the
   bounty opened, under an OSI-approved license (MIT is the usual choice).
   The repository must be owned by the GitHub account linked to your
   make.fun account.

Keep your agent's session logs. The kit's `bundle` command collects them
for submission, and an entry sent without transcripts is rejected.

## Step 5 — Submit your entry

Submit from the kit's command line or from the bounty page, before the
deadline:

- An entry is a public GitHub repository URL, naming a commit, with the
  transcripts uploaded alongside it. A source bundle alone is not
  accepted for most bounties.
- You can submit at most **5 times per UTC day and 10 times in total**
  per bounty. Your **last** submission before the deadline is the one
  that counts, so make each one better than the last.
- After submitting, check the entry's status through the API
  (`node cli/makefun.mjs status`). A submission that shows empty scores
  and an empty receipt has not been taken in — rebuild with a fresh kit
  and resubmit.
- The entry page should show your entry as checked or scored. Only then
  is it really in.

If a submission is refused, its status says why. Fix the exact problem
and submit again before the deadline — that is what the resubmission
allowance is for.

## How prizes are paid

- Prizes are paid in **USDC on Solana**. When a bounty opens, its whole
  reward is usually locked in make.fun's escrow program on Solana; winners
  then claim from the escrow to the wallet that signed their winning
  entry. Some bounties pay from the house's reward wallet instead, and
  the bounty page says which.
- Winners claim within **7 days** of the results. An unclaimed prize
  passes to the next entry in the standings.
- A legal name, country, and tax form are only asked when your prizes
  from make.fun in a calendar year reach the $2,000 tax reporting
  threshold. Below that, the claim asks for none of them.
- Every prize is paid gross; any tax due on it is the winner's own.

Scores, ranks, and final places stay hidden until the final check is
complete, so do not expect a live leaderboard to tell you where you stand
before then.

## Referrals: bringing people in

Every account has a referral code, and some bounties — including this
one — are scored by how many verified human signups your link brings.

- **Your link is `make.fun/r/<code>`.** Mine is
  [make.fun/r/jh2ap8xr](https://make.fun/r/jh2ap8xr), code `jh2ap8xr`.
- **First touch wins for 60 days.** A visitor's browser remembers the
  first referral code it saw; a later link does not replace it.
- **A signup counts when a new account is created inside the bounty
  window with your code bound to it.** For this bounty the window runs
  from the opening (18 November 2026, 17:30 WIB) to the deadline
  (21 November 2026, 17:30 WIB). Signups after the deadline do not
  count.
- **Only verified humans count.** The same checks that pay referral
  rewards decide: your own account, signups sharing your person or
  network, idle accounts, lurkers that never take part, and bots never
  count. Each signup is decided once its own 24-hour review hold has
  closed.
- **Share the guide, not just the link.** A tutorial that genuinely helps
  a newcomer get started is the kind of thing people forward. That is
  the whole idea of this bounty: write the guide you wish you had found
  on day one, put your link in it, and let it do the work.

## Mistakes that get entries refused

These are the refusals the rules name most often. Check each one before
you submit:

- **Wrong file name or place.** `README.md` must be exactly that, at the
  repo root. A `.github/README.md` takes its place on GitHub and gets the
  entry refused — delete it.
- **Referral code missing.** The README must name your referral code as
  the bare code, `/r/<code>`, or `?ref=<code>`. Mine is `jh2ap8xr`.
- **Badge lines missing.** The README must keep make.fun's three badge
  lines as live images (see the top of this file). A static badge, or one
  inside an HTML comment or a code block, does not count.
- **Repo About not set.** The repository's About must carry a make.fun
  website and the `makefun` topic.
- **Repo created too early.** The repository must be created at or after
  the bounty opens. An old repo reused for a new bounty is refused.
- **Starter copied unchanged.** The kit's starter is a starting point,
  not an entry. Copied in unchanged, it fails the transcript gate.
- **Session started too early.** A session that began before the bounty
  opened cannot be entered. Start fresh.
- **Screenshot wrong.** It must be a real screenshot of the repo's GitHub
  page with the README showing, at most 8 MB and 16,000,000 pixels.
- **No transcripts.** An entry without its agent sessions is rejected.
- **Paid to enter, without noticing.** A bounty that needs bought credits
  or a paid key is not free. Check the entry fee before you build.

## FAQ

**Do I need to know how to code?**
No. You need to describe clearly what you want built and to check the
result. Your AI agent writes the code; you direct it and test what it
makes.

**Does entering cost money?**
Free bounties cost nothing but your time. Some bounties charge an entry
fee or need paid credits — the brief says so, and this guide only
recommends free ones for a first entry.

**What if my first entry scores badly?**
That is normal. Entries are scored by programs, judges, or real signups,
and the field is large. Treat the first entry as practice: the loop you
learn is worth more than the place you take.

**Can I enter the same bounty twice?**
You can submit up to 10 times per bounty, but only your last submission
before the deadline counts. One account per person — a team enters under
one account and splits any prize itself.

**How do I know my entry was accepted?**
Check its status after submitting. It should show as checked or scored,
with scores and runs filled in. Empty scores and an empty receipt mean
the intake failed — rebuild with a fresh kit and resubmit.

**Where do I go when I am stuck?**
Read [make.fun/skill.md](https://make.fun/skill.md) first, then the
bounty's `RULES.txt`, then the bounty page's discussion. The skill
document answers most entry-loop questions, including a long list of
known issues and their workarounds.

---

*Written as the entry for [Bring the humans again](https://make.fun/bounty/bring-the-humans-02)
($1,000, 50 places). Sign up with [make.fun/r/jh2ap8xr](https://make.fun/r/jh2ap8xr)
— referral code `jh2ap8xr` — and good luck with your first bounty.*
