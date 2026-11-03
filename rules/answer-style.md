# Answer style

- **No LaTeX in chat answers.** The terminal doesn't render it. Derivations and equation-heavy explanations go into
  a Markdown note in the project (following `typora-markdown.md`); the reply says where in the note to look and
  summarizes in words or plain Unicode (λ, σ², ≈). Small inline quantities in chat: Unicode, not `$...$`. If the
  project has no note that fits, ask where the derivation should go.
- **Short status lines need the same technical care as full answers.** Brief progress lines and one-sentence
  summaries before a tool call must name the right tool or program and the right quantity (a value vs. its
  tendency, say), with no compressed paraphrase that changes the meaning. Check every technical noun and verb in
  them; if there is no room to say it precisely, say less ("checking the tutorial script") rather than compress a
  finding.

**Why:** in `bnf_wrf_da`, the user said a LaTeX-heavy answer about a likelihood derivation was unreadable in the
terminal and asked for it in the note instead (2026-10-27); and a one-line status attributed a DART program to
WRFDA and called a tendency a value. The user reads the short lines closely and relies on them (2026-10-02).
