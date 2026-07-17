# Clear English

**Make your AI coding assistant reply in clear, simple English — without losing any meaning.**

If English is not your first language, AI replies can be hard to read: long
sentences, jargon dropped with no explanation, idioms, and hype words like
"robust" or "seamless" that carry no real information. This is a small set of
rules that fixes that. It keeps every fact exact — only the wording gets simpler.

It works in **Claude Code, Codex CLI, Cursor, and Gemini CLI**.

## Before → after

> "Utilize the aforementioned endpoint to instantiate a session."
> → **"Use that endpoint to start a session."**

> "The build is failing due to a type error in the routing layer."
> → **"The build stops because one value has the wrong type — the code expects
> text but gets a number. It happens in the file that handles page routes."**

## What it does

- **Common word first** — "use" not "utilize", "start" not "initiate".
- **One idea per sentence** — splits long, stacked sentences.
- **Defines a term once**, then uses it — "a hook (a small script the tool runs
  at a set moment)".
- **Real examples, not categories** — "an empty list, or a name with an
  apostrophe", not "edge cases".
- **No idioms, no hype.**
- **Keeps code, commands, and error text exact** — those are never reworded.

## Install

Pick your tool. Each is copy-paste.

### Claude Code

```bash
mkdir -p ~/.claude/skills/clear-english
# then copy SKILL.md from this repo into that folder:
#   ~/.claude/skills/clear-english/SKILL.md
```

Start a new Claude Code session. Type `/clear-english`, or let it turn on by
itself when Claude explains something.

**Always on (optional):** add one line to `~/.claude/CLAUDE.md`:
`For all prose explanations, follow the clear-english skill's voice rules.`

### Codex CLI

Copy [`codex/AGENTS.md`](codex/AGENTS.md) into `~/.codex/AGENTS.md` (global), or
paste its rules into your project's own `AGENTS.md`. Codex reads this on every
run.

### Cursor

Copy [`cursor/clear-english.mdc`](cursor/clear-english.mdc) into your project's
`.cursor/rules/` folder. It is set to always apply.

### Gemini CLI

Copy [`gemini/GEMINI.md`](gemini/GEMINI.md) into your project (or your global
Gemini config). Gemini reads this on every run.

## Why this format works everywhere

The rules are the same in every file — only the file's **name and location**
change per tool. `SKILL.md` is a shared format that Claude Code, Codex, Cursor,
and others can read. The other files are the same rules in each tool's own
"always-on instructions" file.

## Author

Made by **Soumya**.
<!-- Fill these in before you push: -->
- GitHub: `https://github.com/sho-das`
- LinkedIn: `https://www.linkedin.com/in/soumya-das-/`

If it helps you, a ⭐ on the repo is welcome.

## License

MIT — see [LICENSE](LICENSE). Use it, change it, share it.
