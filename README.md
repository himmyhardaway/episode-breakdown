# episode-breakdown

A Claude Code skill for anyone making a show. Drop in a transcript, get back chapters for YouTube, key themes, and a summary written in the voice of your show — not a generic AI recap.

---

## Why This Exists

If you make a show — podcast, YouTube series, docuseries, interview program, whatever the format — you already know the tedious part: every episode needs chapters for YouTube, a summary for your feed, and themes for your team. It's the same work every time, and it's the last thing you want to be doing after a long recording session.

This skill handles that. It reads your transcript, learns what your show is actually about, and produces everything you need — shaped around your show's identity, not a template.

Built for producers, editors, and creators who are moving fast and can't afford to sound like a bot.

---

## Requirements

- [Claude Code](https://claude.ai/code) (desktop app or CLI)
- A `.vtt` transcript file from your episode (most recording tools export these)
- Optional: a YouTube channel URL or a filled-in `SHOW.md` to give the skill your show's identity upfront

---

## Install

**1. Copy the skill file into your Claude commands folder.**

Global install (available in every project):
```bash
cp SKILL.md ~/.claude/commands/episode-breakdown.md
```

Project install (available in one project only):
```bash
cp SKILL.md .claude/commands/episode-breakdown.md
```

**2. Optional: fill in `SHOW.md`** with your show's identity so the skill knows your voice before it reads a single word of the transcript. Or pass your YouTube channel URL and it will pull that automatically.

**3. Run it from Claude Code:**
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

---

## How It Works

The skill does four things in order:

**1. Learns the show**
If you pass a YouTube URL, it fetches your channel's about page and description to understand your show's identity, tone, and audience. If you pass a `SHOW.md`, it reads that. If you pass neither, it infers everything from the transcript itself.

**2. Chapters**
Identifies 10–20 natural topic shifts and outputs timestamps in two ready-to-paste formats:
- YouTube format: `00:00 Chapter Title`
- Spotify / Podcast format: `(0:00) Chapter Title`

**3. Key Themes**
4–6 ideas that run through the episode, each with a one-sentence description and timestamps for where they surface.

**4. Episode Summary**
150–200 words written in the actual tone of your show. Analytical shows get sharp copy. Conversational shows get warmth. Investigative shows get tension. It reads like a human wrote it because it's shaped around who you are.

Everything saves as a `.txt` file next to your original transcript.

---

## License

MIT — use it, modify it, share it.

---

## Contributors

- [@himmyhardaway](https://github.com/himmyhardaway)
- [Claude Code](https://claude.ai/code)
