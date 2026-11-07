# Answer style

- **No LaTeX in chat answers.** The terminal doesn't render it. Derivations and equation-heavy explanations go into
  a Markdown note in the project (following `typora-markdown.md`); the reply says where in the note to look and
  summarizes in words or plain Unicode (λ, σ², ≈). Small inline quantities in chat: Unicode, not `$...$`. If the
  project has no note that fits, ask where the derivation should go.
- **Short status lines need the same technical care as full answers, and must be understandable on their own.**
  Brief progress lines and one-sentence summaries before a tool call are written as complete sentences that say
  what is being done, on what, and why, so the reader can follow without seeing the command. They must name the
  right tool or program and the right quantity (a value vs. its tendency, say), with no compressed paraphrase
  that changes the meaning. Check every technical noun and verb in them. If a line can't be both short and
  precise, make it longer rather than vaguer.

**Why:** in `bnf_wrf_da`, the user said a LaTeX-heavy answer about a likelihood derivation was unreadable in the
terminal and asked for it in the note instead (2026-10-27); and a one-line status attributed a DART program to
WRFDA and called a tendency a value. The user reads the short lines closely and relies on them (2026-10-02).
Later the user found the status lines "all too short to understand" (2026-11-07): the earlier advice to "say
less" had produced terse fragments.
