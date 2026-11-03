# Markdown notes for Typora (screen and letter-size PDF)

The user reads Markdown notes in Typora and often prints them with its *Export to PDF* on letter-size paper. Write
every Markdown document meant for the user to read (notes, write-ups, plans, logs, reports) so that it renders
correctly there and fits the printed page. This does not cover `CLAUDE.md`, Claude's memory files, or Markdown whose
format another tool dictates.

## Math

- **Every `$$` display block needs `\tag{n}` or `\notag`.** Typora has numbered untagged blocks, throwing off the
  manual numbering, even with "No Automatic Equation Number" selected. One `\tag`/`\notag` per block; in a
  multi-line block it goes after `\end{aligned}` / `\end{gathered}`.
- **Keep display equations narrow.** Split chains of several `\qquad`-joined parts or `\Longrightarrow` steps into
  `aligned`/`gathered` lines. Put remarks in the prose, not in `\text{...}` inside the equation. Avoid label columns
  (`&&\text{...}`) in `aligned`.
- Inline `$...$` math needs Typora's *Preferences → Markdown → Inline Math*; display math works by default.

## Tables

- **Keep tables narrow:** few columns, short cells, no long unbreakable cells (code-span lists, long inline math,
  "a/b" number pairs).
- Split a wide table (one per file, one per quantity), move definitions to a lead-in sentence, and use footnote
  marks (¹ ²) for long cell remarks.

## Prose

- **Don't hard-wrap prose:** one line per paragraph or list item; Typora wraps it to the page. Existing hard-wrapped
  files should be unwrapped too, but only when they are edited or saved anyway: then unwrap all of the file's prose,
  not only the new text. Don't unwrap files in bulk or on their own. This applies only to Markdown files created for
  the current project (by the user, by Claude, or by anyone else working on it). It does not apply to files of
  another project, loose files outside a project, or Markdown that came from elsewhere (upstream, vendored or
  cloned code, or documents copied in for reference).

## Diagrams in code blocks

- **At most ~72 characters per line, plain ASCII** (`|`, `v`, `->`), so they fit the page and can't lose their
  alignment to a font fallback.
- Don't split a text line that already fits, and use one `v` line per arrow; extra breaks there are unnecessary.

**Why:** wide equations and table rows ran off the printed page, untagged equations got stray numbers, and
hard-wrapped prose and over-broken diagrams were unwanted.
