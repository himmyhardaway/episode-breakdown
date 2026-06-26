You are analyzing a podcast or show episode transcript to produce a professional episode breakdown.

**Input:** $ARGUMENTS

This skill works in two modes:

**Claude Code (CLI):** Pass a file path to a `.vtt` transcript file.
**Claude Chat:** Paste the transcript text directly into the conversation — no file path needed.

Optional extras (either mode):
- A YouTube channel URL — fetched to learn the show's identity before reading the transcript
- A path or contents of a `SHOW.md` file — read to establish show identity upfront

Examples:
- `/path/to/episode.vtt`
- `/path/to/episode.vtt https://youtube.com/@channelname`
- `/path/to/episode.vtt SHOW.md`
- *(paste transcript text directly — no arguments needed)*

---

## Principles

These rules apply to every output you produce. Hold yourself to them.

- **No AI slop.** Every output must sound like it was written by a human who actually listened. No hollow summaries, no generic chapter titles like "Introduction" or "Key Takeaways," no filler phrases. If it could have been written without reading the transcript, it's wrong.
- **Context first.** Learn the show before producing anything. Identity, tone, audience, and voice come from the source — the YouTube channel, the SHOW.md, or the transcript itself. Never assume.
- **No hallucination.** If an idea, theme, or claim is not in the transcript, it does not appear in the output. Do not invent insights or infer things that were never said. When something is unclear, flag it rather than fill it in.
- **Clarity over verbosity.** Say the thing. Don't dress it up. A sharp sentence beats a decorated one every time. If a word isn't pulling its weight, cut it.
- **Timestamps are exact.** Every chapter timestamp comes directly from a VTT cue in the source file. No estimating, no rounding.
- **Chapters reflect real shifts.** A chapter only starts when the conversation genuinely changes direction. Ten strong chapters beat twenty weak ones.
- **Themes must be earned.** A theme only qualifies if it surfaces at least twice in the episode, independently. One mention is a point. Two or more is a thread.
- **The summary is writing, not reporting.** It has a point of view and a voice. It does not list what was discussed.

---

## Step 1 — Learn the Show

Before reading the transcript, establish the show's identity using whichever source is available:

**If a YouTube URL was provided:**
Fetch the channel's About page. Extract the show's description, topic focus, audience, and any language that reveals its tone and voice. Also scan recent video titles and descriptions to understand what topics this show regularly covers.

**If a SHOW.md was provided:**
Read it. Use the information inside to establish the show's identity.

**If neither was provided:**
Proceed to Step 2 and infer the show's identity from the transcript itself:
- What this show is about
- Who it's for
- The tone (analytical, conversational, investigative, comedic, editorial, etc.)
- The hosts and guests — names, roles, and dynamic

---

## Step 2 — Get the Transcript

**If a file path was provided (Claude Code):**
Read the `.vtt` file at the provided path. Parse the cues to extract both the spoken content and exact timestamps.

**If no file path was provided (Claude Chat):**
If the user has already pasted transcript text into the conversation, use it directly. If no transcript is present, ask the user to paste it now before continuing.

---

## Step 3 — Chapters

Identify 10–20 natural topic shifts in the conversation. Use the timestamp from the nearest VTT cue for each. Do not invent chapters — only mark a new chapter when the conversation genuinely changes direction.

Output two formats:

**YouTube Format** (paste directly into video description — auto-links):
```
00:00 Chapter Title
03:41 Next Chapter Title
```

**Spotify / Podcast Format** (works on Spotify, Apple Podcasts, Buzzsprout, Transistor, etc.):
```
(0:00) Chapter Title
(3:41) Next Chapter Title
```

If the opening 2–3 minutes are pre-show setup or mic check, label it "Pre-show & Setup" and add a note at the bottom that editors may want to trim it before uploading.

---

## Step 4 — Key Themes

Identify 4–6 themes that run through the episode — ideas, tensions, or threads that surface at least twice, independently. Do not name a theme that only appears once.

For each theme:
- Write one punchy, specific sentence (not a generic label)
- Include 1–2 timestamps where it comes up most clearly

Example:
**Obsession as a filter** — Both guests return to founder obsession as the core signal, above pedigree or market size. (24:43, 32:25)

---

## Step 5 — Episode Summary

Write a 150–200 word summary of the episode. This is not a bullet list — it is a short piece of writing with a point of view.

Match the tone of the show:
- Analytical → sharp, precise, no fluff
- Conversational → warm, specific, let personality come through
- Investigative → lead with the tension or the stakes
- Comedic → keep the energy, don't over-explain

The summary should tell a new listener what this show is, why this episode matters, and what they'll leave with. It must be grounded entirely in what was actually said — no invented insights, no generic filler.

---

## Step 6 — Output

**If running in Claude Code (file path was provided):**
Save the full output (both chapter formats, themes, summary) to a `.txt` file in the same directory as the input transcript, named:
`[original-filename]-breakdown.txt`
Confirm the save path when done.

**If running in Claude Chat (pasted text):**
Display the full output in the conversation — both chapter formats, themes, and summary — formatted for easy copying. Do not attempt to save a file.
