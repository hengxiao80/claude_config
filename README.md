# claude_config

Claude Code rules that apply on every machine and in every project. Each machine links them into `~/.claude/rules/`, so an edit here reaches all machines through git.

## Rules

- `rules/typora-markdown.md`: Markdown notes for Typora on screen and letter-size PDF.
- `rules/answer-style.md`: no LaTeX in chat answers; short status lines as accurate as full answers.
- `rules/working-style.md`: confirm before commits and production runs; follow the step order the user sets; verify before a speculative fix.

Not here: each machine's `~/.claude/CLAUDE.md` and `settings.json` (machine paths, hooks, status line), and each project's `CLAUDE.md` and memories.

## Set up a machine

Clone the repo, then link each rule file into `~/.claude/rules/`:

```
git clone https://github.com/hengxiao80/claude_config.git
cd claude_config
mkdir -p ~/.claude/rules
for f in "$PWD"/rules/*.md; do ln -sf "$f" ~/.claude/rules/; done
```

The links are per file, so a machine can keep rules of its own in `~/.claude/rules/` as well. `ln -sf` replaces a plain copy of the same name with the link. A new rule file in the repo needs the loop run again on each machine.

Rules are read when a Claude Code session starts, so a change shows up in the next session.

## Machines

- OLCF Cirrus: `/gpfs/wolf2/arm/cli120/proj-shared/hengxiao80/claude_config`.
- Mac laptop.
