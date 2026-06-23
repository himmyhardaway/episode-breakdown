You are analyzing a podcast or show episode transcript to produce a professional episode breakdown.

**Input:** $ARGUMENTS

Arguments can be:
- A path to a `.vtt` transcript file (required)
- A YouTube channel URL (optional) — if provided, fetch the channel's About page to learn the show's identity, tone, and audience before reading the transcript
- A path to a `SHOW.md` file (optional) — if provided, read it to understand the show's identity before reading the transcript

Examples:
- `/path/to/episode.vtt`
- `/path/to/episode.vtt https://youtube.com/@channelname`
- `/path/to/episode.vtt SHOW.md`

---

## Step 1 — Learn the Show

Before reading the transcript, establish the show's identity using whichever source is available:

**If a YouTube URL was provided:**
Fetch the channel's About page. Extract: the show's description, topic focus, audience, and any language that reveals the show's tone and voice.

**If a SHOW.md was provided:**
Read it. Use the information inside to establish the show's identity.

**If neither was provided:**
Read the transcript first (Step 2), then infer:
- What this show is about
- Who it's for
- The tone (analytical, conversational, investigative, comedic, editorial, etc.)
- The hosts and guests — names, roles, and dynamic

Use this understanding to inform every output that follows. Chapters, themes, and summaries should all reflect the actual identity of this show.

---

## Step 2 — Read the Transcript

Read the `.vtt` file at the provided path. Parse the cues to get both the spoken content and the exact timestamps.

---

## Step 3 — Chapters

Identify 10–20 natural topic shifts in the conversation. Use the timestamp from the nearest VTT cue for each.

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

Identify 4–6 themes that run through the episode — ideas, tensions, or threads that keep resurfacing. For each:
- Write one punchy, specific sentence (not a generic label)
- Include 1–2 timestamps where the theme comes up most clearly

Example:
**Obsession as a filter** — Both guests return to founder obsession as the core signal, above pedigree or market size. (24:43, 32:25)

---

## Step 5 — Episode Summary

Write a 150–200 word summary of the episode. This is not a bullet list — it is a short piece of writing.

Match the tone of the show:
- Analytical → sharp, precise, no fluff
- Conversational → warm, specific, let personality come through
- Investigative → lead with the tension or the stakes
- Comedic → keep the energy, don't over-explain the jokes

The summary should tell a new listener what this show is, why this episode matters, and what they'll leave with. It should feel like it was written by someone who actually listened — not auto-generated.

---

## Step 6 — Save Output

Save the full output (chapters both formats, themes, summary) to a `.txt` file in the same directory as the input transcript, named:
`[original-filename]-breakdown.txt`

Confirm the save path when done.
