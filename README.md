# teacher-notes-to-pdf

A Claude plugin that turns photos of handwritten notes or question papers into a neat typed PDF. It can also make a copy with the same questions but new numbers, or a set of new practice questions.

## What it does

1. **Types up handwriting.** Upload photos or scans of handwritten pages and get back a clean PDF laid out like the original page (same columns, same number of pages), keeping the wording, tables, maths and diagrams.
2. **Same questions, new numbers.** Makes a fresh copy of a test or worksheet: every question stays the same, in the same order, but the numbers change so the answers are different. Works across several question papers on one page.
3. **New practice questions.** A shuffled set of new questions from the notes: short answer, fill-in-the-blank, multiple choice and true/false.
4. **Answers and working space.** Optional working space under each question, answers on the last page or in a separate PDF, and several different copies.
5. **Checks unclear words.** Before building the PDF, it asks about any words it couldn't read, offering its best guesses to pick from.

## No typing needed

After uploading, everything is guided with tap-to-choose questions:

- What to make: typed-up copy, same questions with new numbers, new practice questions (tap any combination), and the page layout
- Options: how many practice questions, working space, where the answers go, how many copies
- Any hard-to-read words
- An "Anything else?" menu after each PDF: another copy with new numbers, practice questions, bigger writing, or fix something

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
