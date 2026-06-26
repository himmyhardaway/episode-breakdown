# episode-breakdown

A skill for anyone making a show. Drop in a transcript, get back chapters for YouTube, key themes, and a summary written in the voice of your show — not a generic AI recap.

Works in **Claude Chat** (claude.ai) and **Claude Code** (CLI/desktop app).

---

## Why This Exists

If you make a show — podcast, YouTube series, docuseries, interview program, whatever the format — you already know the tedious part: every episode needs chapters for YouTube, a summary for your feed, and themes for your team. It's the same work every time, and it's the last thing you want to be doing after a long recording session.

This skill handles that. It reads your transcript, learns what your show is actually about, and produces everything you need — shaped around your show's identity, not a template.

Built for producers, editors, and creators who are moving fast and can't afford to sound like a bot.

---

## How to Use It

### Option 1 — Claude Chat (no setup required)

1. Open [claude.ai](https://claude.ai)
2. Start a new conversation
3. Paste the contents of `SKILL.md` into the chat, followed by your transcript text
4. Claude will produce chapters, themes, and a summary directly in the conversation — formatted for easy copying

No install. No file paths. Just paste and go.

---

### Option 2 — Claude Code (CLI or desktop app)

Requires [Claude Code](https://claude.ai/code).

**Install the skill:**

Global install (available in every project):
```bash
cp SKILL.md ~/.claude/commands/episode-breakdown.md
```

Project install (available in one project only):
```bash
cp SKILL.md .claude/commands/episode-breakdown.md
```

**Run it:**
```
/episode-breakdown /path/to/transcript.vtt
```

With a YouTube channel URL:
```
/episode-breakdown /path/to/transcript.vtt https://youtube.com/@yourchannel
```

With a local show profile:
```
/episode-breakdown /path/to/transcript.vtt SHOW.md
```

Output saves automatically as a `.txt` file next to your original transcript.

---

## Optional: Give It Your Show's Identity Upfront

The skill will infer your show from the transcript — but you can give it a head start two ways:

- **YouTube URL** — pass your channel URL and it fetches your show description, tone, and recent topics automatically
- **SHOW.md** — fill in the included `SHOW.md` template with your show's identity and pass it as an argument (Claude Code) or paste it alongside your transcript (Claude Chat)

---

## What It Produces

**Chapters**
10–20 natural topic shifts with timestamps in two ready-to-paste formats:
- YouTube: `00:00 Chapter Title`
- Spotify / Podcast: `(0:00) Chapter Title`

**Key Themes**
4–6 ideas that run through the episode, each with a one-sentence description and timestamps for where they surface. Only themes that appear at least twice make the cut.

**Episode Summary**
150–200 words written in the actual tone of your show. Analytical shows get sharp copy. Conversational shows get warmth. Investigative shows get tension. It reads like a human wrote it because it's shaped around who you are.

---

## Requirements

- A transcript file — `.vtt` format works best (most recording tools export these). In Claude Chat, paste the text directly.
- Claude Chat (free or paid) or Claude Code (CLI/desktop)

---

## Contributors

- [@himmyhardaway](https://github.com/himmyhardaway)
- Built with [Claude Code](https://claude.ai/code)

---

## License

MIT — use it, modify it, share it.
