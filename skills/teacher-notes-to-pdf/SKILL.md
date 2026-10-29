---
name: teacher-notes-to-pdf
description: Turn photos or scans of handwritten notes into a neat typed PDF, and optionally a sheet of randomised questions with working space and an answer key.
---

# Handwritten notes → typed PDF (and optional question sheet)

This skill is for teachers, parents and tutors who may not be technical. Keep every message **short, warm and in plain words**. Don't mention code, Python, libraries, file paths or "skills".

**The user shouldn't have to type.** As soon as they upload, guide them through the job with tap-to-choose questions (AskUserQuestion). Every choice is a button. Typing is only for the rare case where none of the buttons fit, and the automatic "Other" option covers that.

Use this skill even if the user uploads photos with no message, or with only "hi" or "can you do this".

## What users usually want

1. **Typed notes (almost always):** read the handwritten page(s) and type them up into a neat PDF.
2. **Questions (sometimes):** make randomised practice questions from those notes.
   - **If the notes are themselves question papers** (numbered lists of questions, often several papers on one page, with numbering restarting at 1 for each), the questions are a new version of **every** paper: the same questions in the same order, with different numbers so the answers change. See "Question papers" in section 2.
3. **Layout:** split onto several pages, and leave working space.

## The guided flow

If the user's message already makes something clear (e.g. "make 10 questions"), skip that question. Never ask about something they have already said.

### Tap 1: right after the upload

Open with one friendly line, e.g. "Got your 2 pages! A few quick taps and I'll make your PDF." Then call AskUserQuestion with:

- **"What would you like me to make?"** with options: "Typed-up notes" / "Typed-up notes + questions" / "Just questions"
- **"How should the pages be laid out?"** with options: "Keep it all together" / "New page for each topic"

Start reading the handwriting (section 1) while they decide. If the page holds question papers, say so in the opening line, e.g. "Got your page! I can see 4 question papers on it."

For question papers, word the options as "Typed-up papers" / "Typed-up papers + new versions" / "Just new versions".

### Tap 2: only if they chose questions

One AskUserQuestion call with up to four questions:

- **"How many questions?"**: "5" / "10 (Recommended)" / "20". **Skip this for question papers:** each new version has exactly as many questions as its original paper.
- **"Space for writing answers?"**: "A few lines under each" / "Big space under each" / "One question per page" / "No space needed"
- **"Include the answers?"**: "Yes, on the last page" / "Yes, in a separate PDF" / "No answers"
- **"How many different versions?"**: "Just one" / "2 versions (different questions)" / "3 versions". For question papers, word it as "How many new versions of each paper?"

### Tap 3: only if some words were hard to read

Ask before building the PDF, so the first PDF comes out right. Use one AskUserQuestion call per batch of up to four words. Each question shows the surrounding words, with the unclear word in capitals, e.g. **"Line 4: 'the cell takes in water by OSMOSIS'. Is that the right word?"** Offer your 2–3 best guesses as options, plus "Leave it as it is". The user can type the right word under "Other".

If there are more than eight unclear words, ask about the eight most important ones. Mark the rest with "(?)" in the PDF.

### Then make and send the PDF

Follow sections 1–5 below, then send it (section 6).

### Tap 4: what next (always, after sending)

Call AskUserQuestion with **"Anything else?"** and these options:

- "All done, thank you"
- "Make questions from this" (only if they didn't get questions), or "Make a new set of questions" (if they did)
- "Make the writing bigger"
- "Something's wrong"

If they pick **"Something's wrong"**, follow up with buttons: "A word is wrong" / "Something's missing" / "Pages look messy" / "Too much or too little space". Then ask one more button question to pin it down (e.g. list the sections, and they tap the one with the problem). Fix only that, resend the whole PDF, and show the "Anything else?" menu again. Keep looping until they tap "All done".

### If buttons aren't available

If AskUserQuestion isn't available, ask the same questions in plain text as a short numbered list, so the user only has to reply with a number ("Reply 1, 2 or 3").

### If there's no answer

If the user goes quiet, or says "you decide" under Other, use these defaults: typed notes only, kept together. If they asked for questions: 10 questions (or, for question papers, a new version of every paper), a few lines of space under each, answers on the last page, one version.

## 1. Read the handwriting

- Open every image or PDF attached. With several pages, follow the order given, or the page numbers written on the paper.
- **Transcribe faithfully:** keep the writer's words, order, headings, numbering and bullets. Underlined words become **bold**. Tables stay tables. Write maths exactly, with proper symbols (×, ÷, ², √, fractions).
- Fix obvious spelling slips. Never change facts, numbers or meaning, and don't summarise or rewrite.
- **Words you can't read:** note your best guesses for Tap 3. Anything still uncertain gets a small grey "(?)" in the PDF.
- **Diagrams or drawings:** crop that part of the original photo (straightened and tidied) and place it in the PDF at the right spot. Don't try to redraw anything complicated.
- **Language:** type it in the language it was written in.

## 2. Questions (only if wanted)

### Question papers

When the notes are question papers, don't invent new questions. For **every** paper on the page:

- Keep **the same questions in the same order**, with the same wording and the same kind of task. Question 1 stays a place-value question, question 4 stays a subtraction, the eggs word problem stays a sold-and-left word problem, and so on.
- **Change only the numbers** (and small details such as the item or a person's name in word problems), so every answer is different from the original.
- Keep each question the same difficulty and shape: the same number of digits, the same operations in the same order, whether there's a remainder, whether rounding is to tens or hundreds, a Roman numeral of similar length. If a "missing digit" or "find the base" question has a neat answer in the original, make sure the new one does too.
- Number the new papers "Paper 1", "Paper 2" and so on in the order they appear on the page (top to bottom, then left column before right column), and start each paper on a new page so it can be printed on its own.
- If they chose several versions, make that many new versions of each paper (e.g. "Paper 1, Version A" and "Paper 1, Version B"), each with different numbers.

### Other notes

- Base them **only on the notes**. Don't add material from outside.
- **Mix the types:** short answer, fill-in-the-blank, multiple choice, true/false. For maths or number content, add worked problems that use the same method with **new numbers**.
- **Randomise:** shuffle the order, vary which facts get tested, and change the numbers in calculation questions. Whenever the user asks for a new set, make a fresh one instead of repeating the last. If they chose several versions, make Version A, Version B and so on, each different and each with its own answers.
- Match the level of difficulty to the notes.
- **Check every answer.** For calculations, actually work them out with code, not in your head.
- **Answers on the last page:** put them on their own page(s) at the end, titled "Answers", so the questions can be printed without them.
- **Answers in a separate PDF:** leave them out of the main PDF entirely and make a second PDF with the same title plus "Answers", in the same layout and numbering. With several versions, label each version's answers clearly (e.g. "Version A answers") in that one answers PDF.

## 3. Layout

- A4 paper (or US Letter if the user is in the US), about 2 cm margins, a clear font at roughly 12–13 pt, larger headings. If they tap "Make the writing bigger", go up to about 15–16 pt. Page numbers go in the footer.
- **Typed-up copy mirrors the original page.** Keep the same layout: if the handwriting is in two columns, type it in two columns with a thin line between; keep papers or sections in the same places, separated by a small gap where the numbering restarts. Fit it on the same number of pages as the original (one handwritten page → one typed page), adjusting font size and spacing to fill the page neatly without going below about 10 pt.
- **No added title or subtitle.** Only include a heading if one is written on the page. For new versions or question sheets, a plain label such as "Paper 1" is fine.
- **Splitting into pages:** if they chose "New page for each topic", start each topic or section on a new page. Never split a question from its working space across two pages. Keep tables and diagrams whole.
- **Working space:** "A few lines" means about 3 faint ruled lines (about a third of a page, or a light grid, for calculations). "Big space" means about a third of a page for every question. "One question per page" means exactly that.
- **Notes and questions together:** put the notes first, start the questions on a new page, then put the answers at the end (unless they chose a separate answers PDF).

## 4. Make the PDF

- Load the `pdf` skill first if one is available, and follow it.
- Reliable route: write HTML and CSS, then convert with WeasyPrint. Use `break-before: page` for new pages and `break-inside: avoid` on each question block.
- For non-Latin scripts, use a matching Noto font so letters join and display correctly.
- If the user specifically asks for a Word document, make a .docx instead (with the `docx` skill if available).

## 5. Check it

Render each page to an image and look at it before sending. Check that nothing is cut off, page breaks fall in sensible places, and the working space is there. Fix any problem before the user sees it.

## 6. Hand it over

- Give the file a meaningful name, e.g. `Photosynthesis notes.pdf` or `Photosynthesis questions.pdf`, and send it with SendUserFile. If the answers are separate, send both files together, e.g. `Photosynthesis questions.pdf` and `Photosynthesis answers.pdf`.
- Keep the message to one line, e.g. "Here's your page typed up!" If any "(?)" marks are left, add: "I've marked a couple of words I wasn't sure of with (?)."
- Then go straight to Tap 4.
