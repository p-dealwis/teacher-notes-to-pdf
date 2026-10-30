---
name: teacher-notes-to-pdf
description: Turn photos or scans of handwritten notes or question papers into a neat typed PDF, a copy with the same questions but new numbers, or a sheet of randomised practice questions, with working space and an answer key.
---

# Handwritten notes → typed PDF, new-number copies and practice questions

This skill is for teachers, parents and tutors who may not be technical. Keep every message **short, warm and in plain words**. Don't mention code, Python, libraries, file paths or "skills".

**The user shouldn't have to type.** As soon as they upload, guide them through the job with tap-to-choose questions (AskUserQuestion). Every choice is a button. Typing is only for the rare case where none of the buttons fit, and the automatic "Other" option covers that.

Use this skill even if the user uploads photos with no message, or with only "hi" or "can you do this".

## What users usually want

1. **Typed-up copy (almost always):** read the handwritten page(s) and type them up into a neat PDF that looks like the original page.
2. **Same questions, new numbers (often, for question papers and maths):** the same questions in the same order and wording, with only the numbers changed so every answer is different. Useful for a fresh copy of a test or worksheet. See section 2a.
3. **New practice questions (sometimes):** new, randomised questions made from the notes. See section 2b.
4. **Layout:** split onto several pages, and leave working space.

The page may hold several question papers (numbered lists where the numbering restarts at 1). Treat each list as its own paper.

## The guided flow

If the user's message already makes something clear (e.g. "change the numbers"), skip that question. Never ask about something they have already said.

### Tap 1: right after the upload

Open with one friendly line, e.g. "Got your 2 pages! A few quick taps and I'll make your PDF." If the page holds question papers, say how many, e.g. "Got your page! I can see 4 question papers on it."

Then call AskUserQuestion with:

- **"What would you like me to make? Tap all you want."** (multiSelect: true) with options:
  - "Typed-up copy": "Your page typed up neatly, just as you wrote it"
  - "Same questions, new numbers": "Your questions again with different numbers, so the answers change"
  - "New practice questions": "New questions made from your notes"

  Only offer "Same questions, new numbers" when the notes contain questions or number problems. For plain notes with no questions, offer the other two.
- **"How should the pages be laid out?"** with options: "Same layout as my page" / "New page for each paper or topic"

Start reading the handwriting (section 1) while they decide.

### Tap 2: only if they chose "Same questions, new numbers" or "New practice questions"

One AskUserQuestion call with up to four questions:

- **"How many practice questions?"**: "5" / "10 (Recommended)" / "20". Ask this **only** if they chose "New practice questions". A new-numbers copy always has exactly as many questions as the original.
- **"Space for writing answers?"**: "No space needed" / "A few lines under each" / "Big space under each" / "One question per page"
- **"Include the answers?"**: "Yes, on the last page" / "Yes, in a separate PDF" / "No answers"
- **"How many different copies?"**: "Just one" / "2 copies (different numbers)" / "3 copies"

### Tap 3: only if some words were hard to read

Ask before building the PDF, so the first PDF comes out right. Use one AskUserQuestion call per batch of up to four words. Each question shows the surrounding words, with the unclear word in capitals, e.g. **"Line 4: 'the cell takes in water by OSMOSIS'. Is that the right word?"** Offer your 2–3 best guesses as options, plus "Leave it as it is". The user can type the right word under "Other".

If there are more than eight unclear words, ask about the eight most important ones. Mark the rest with "(?)" in the PDF.

### Then make and send the PDF

Follow sections 1–5 below, then send it (section 6).

### Tap 4: what next (always, after sending)

Call AskUserQuestion with **"Anything else?"** and up to four of these options, picking the ones that fit what they already have:

- "All done, thank you"
- "Same questions, new numbers" (or "Another copy with new numbers" if they already have one)
- "New practice questions" (or "A new set of practice questions" if they already have some)
- "Make the writing bigger"
- "Something's wrong"

Always include "All done, thank you" and "Something's wrong".

If they pick **"Something's wrong"**, follow up with buttons: "A word is wrong" / "Something's missing" / "Pages look messy" / "Too much or too little space". Then ask one more button question to pin it down (e.g. list the sections, and they tap the one with the problem). Fix only that, resend the whole PDF, and show the "Anything else?" menu again. Keep looping until they tap "All done".

### If buttons aren't available

If AskUserQuestion isn't available, ask the same questions in plain text as a short numbered list, so the user only has to reply with a number ("Reply 1, 2 or 3").

### If there's no answer

If the user goes quiet, or says "you decide" under Other, use these defaults: typed-up copy only, in the same layout as their page. If they asked for a new-numbers copy or practice questions: no extra space for a new-numbers copy (a few lines under each for practice questions), answers on the last page, one copy, and 10 practice questions.

## 1. Read the handwriting

- Open every image or PDF attached. With several pages, follow the order given, or the page numbers written on the paper.
- **Transcribe faithfully:** keep the writer's words, order, headings, numbering and bullets. Underlined words become **bold**. Tables stay tables. Write maths exactly, with proper symbols (×, ÷, ², √, fractions).
- Fix obvious spelling slips. Never change facts, numbers or meaning, and don't summarise or rewrite.
- **Words you can't read:** note your best guesses for Tap 3. Anything still uncertain gets a small grey "(?)" in the PDF.
- **Diagrams or drawings:** crop that part of the original photo (straightened and tidied) and place it in the PDF at the right spot. Don't try to redraw anything complicated.
- **Language:** type it in the language it was written in.

## 2a. Same questions, new numbers

Don't invent new questions. Do this for **every** paper or list of questions on the page:

- Keep **the same questions in the same order**, with the same wording and the same kind of task. Question 1 stays a place-value question, question 4 stays a subtraction, the eggs word problem stays a sold-and-left word problem, and so on.
- **Change only the numbers** (and, if it reads better, small details such as the item or a person's name in a word problem), so every answer is different from the original.
- Keep each question the same difficulty and shape: the same number of digits, the same operations in the same order, whether there's a remainder, whether rounding is to tens or hundreds, a Roman numeral of similar length. If a "missing digit", "find the base" or "missing exponent" question has a neat answer in the original, make sure the new one does too.
- Questions with no numbers to change (e.g. "Write a prime close to 40" → change 40; "What is √0" → use another perfect square) still get a sensible new number. If a question truly has nothing to change, keep it as it is.
- **Layout:** match the original page, as for the typed-up copy (section 3): same columns, same paper positions, same number of pages. If they chose working space, the copy may run to more pages, keeping the columns where they still fit.
- If they chose several copies, make that many, each with different numbers, labelled "Copy A", "Copy B" and so on, each starting on a new page.

## 2b. New practice questions

- Base them **only on the notes**. Don't add material from outside.
- **Mix the types:** short answer, fill-in-the-blank, multiple choice, true/false. For maths or number content, add worked problems that use the same method with **new numbers**.
- **Randomise:** shuffle the order, vary which facts get tested, and change the numbers in calculation questions. Whenever the user asks for a new set, make a fresh one instead of repeating the last. If they chose several copies, make Version A, Version B and so on, each different and each with its own answers.
- Spread the questions across all the topics in the notes rather than a few.
- Match the level of difficulty to the notes.

## 2c. Answers (for 2a and 2b)

- **Check every answer.** For calculations, actually work them out with code, not in your head.
- **Answers on the last page:** put them on their own page(s) at the end, titled "Answers", numbered to match, so the questions can be printed without them.
- **Answers in a separate PDF:** leave them out of the main PDF entirely and make a second PDF of just the answers, in the same numbering. With several papers or copies, label each set clearly (e.g. "Paper 2 answers", "Copy B answers").

## 3. Layout

- A4 paper (or US Letter if the user is in the US), about 1.5–2 cm margins, a clear font at roughly 12–13 pt. If they tap "Make the writing bigger", go up to about 15–16 pt. Page numbers go in the footer when there's more than one page.
- **Typed-up copy mirrors the original page.** Keep the same layout: if the handwriting is in two columns, type it in two columns with a thin line between; keep papers or sections in the same places, separated by a small gap where the numbering restarts. Fit it on the same number of pages as the original (one handwritten page → one typed page), adjusting font size and spacing to fill the page neatly without going below about 10 pt.
- **No added title or subtitle.** Only include a heading if one is written on the page. For new-number copies and practice questions, a plain label such as "Copy A" or "Practice questions" is fine.
- **Splitting into pages:** if they chose "New page for each paper or topic", start each paper, topic or section on a new page. Never split a question from its working space across two pages. Keep tables and diagrams whole.
- **Working space:** "A few lines" means about 3 faint ruled lines (or a small light grid for calculations). "Big space" means about a third of a page for every question. "One question per page" means exactly that.
- **Several things in one PDF:** typed-up copy first, then the new-numbers copy, then practice questions, each starting on a new page, then the answers at the end (unless they chose a separate answers PDF).

## 4. Make the PDF

- Load the `pdf` skill first if one is available, and follow it.
- Reliable route: write HTML and CSS, then convert with WeasyPrint. Use flexbox for columns, `break-before: page` for new pages and `break-inside: avoid` on each question block.
- For non-Latin scripts, use a matching Noto font so letters join and display correctly.
- If the user specifically asks for a Word document, make a .docx instead (with the `docx` skill if available).

## 5. Check it

Render each page to an image and look at it before sending. Check that nothing is cut off, the layout matches the original page, sums and blanks aren't split across lines, page breaks fall in sensible places, and any working space is there. Fix any problem before the user sees it.

## 6. Hand it over

- Give the file a meaningful name, e.g. `Maths questions.pdf`, `Maths questions - new numbers.pdf` or `Photosynthesis practice questions.pdf`, and send it with SendUserFile. If the answers are separate, send both files together, e.g. `Maths questions - new numbers.pdf` and `Maths answers.pdf`.
- Keep the message to one line, e.g. "Here's your page typed up!" If any "(?)" marks are left, add: "I've marked a couple of words I wasn't sure of with (?)."
- Then go straight to Tap 4.
