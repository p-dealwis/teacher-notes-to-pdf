# teacher-notes-to-pdf

A Claude plugin that turns photos of handwritten notes into a neat typed PDF, and can also make randomised practice questions from them.

## What it does

1. **Types up handwriting.** Upload photos or scans of handwritten pages and get back a clean, A4 PDF that keeps the original wording, headings, tables, maths and diagrams.
2. **Makes new versions of question papers.** If the notes are question papers (several numbered lists on a page), it makes a new version of every paper: the same questions in the same order, with different numbers so the answers change.
3. **Makes questions (optional).** A fresh, shuffled set of questions from the notes: short answer, fill-in-the-blank, multiple choice and true/false, with new numbers for maths. Choose how many, how much working space, whether to include answers (on the last page or in a separate PDF), and how many different versions.
4. **Checks unclear words.** Before building the PDF, it asks about any words it couldn't read, offering its best guesses to pick from.

## No typing needed

After uploading, everything is guided with tap-to-choose questions:

- What to make (typed notes, notes + questions, or just questions) and how to lay out the pages
- Question options (count, working space, answers on the last page or in a separate PDF, versions)
- Any hard-to-read words
- An "Anything else?" menu after each PDF: make questions, a new set, bigger writing, or fix something

## Install

In Claude Code:

```
/plugin install teacher-notes-to-pdf --marketplace p-dealwis/teacher-notes-to-pdf
```

In the Claude app, download this repo as a zip and add it as a plugin, or copy `skills/teacher-notes-to-pdf/` into your own skills.

## Structure

```
.claude-plugin/plugin.json
.claude-plugin/marketplace.json
.claude-plugin/icon.png
skills/teacher-notes-to-pdf/SKILL.md
```

## License

MIT
