# Copilot instructions for this repo

This repository is a collection of pipe-delimited flashcard lists for Cantonese (Jyutping) ↔ English, intended for import into Anki or similar tools.

## What’s here
- Root-level CSVs; no code/build system. Each line is a card: front | back.
- No header rows. One card per line. Blank lines are rare and should be avoided.
- Files group content by course progression or topic: lesson1–lesson6, numbers, time, money, measure.

## File and field conventions
- Delimiter: a single space, pipe, space: " | ". Keep this exact spacing.
- Two fields only per line. Do not include additional pipes in content.
- Encoding: UTF-8. Preserve punctuation, accents, and numerals as written.
- Syllables in Jyutping are separated by spaces; tone numbers are appended (e.g., nei5 hou2, jat1 cin1).

## Column order by file type
- Lessons (lessonN.csv): Left = Jyutping, Right = English.
  - Example (lesson1.csv): "nei5 hou2 | Hello, Hi, Good day"
- Thematic lists (numbers.csv, time.csv, money.csv, measure.csv): Left = English/notation, Right = Jyutping.
  - Examples:
    - numbers.csv: "1,000 | jat1 cin1"; "What’s your phone number? | nei5 ge3 din6 waa2 hou6 maa5 hai6 mei1 je6?"
    - time.csv: "Wednesday, 20 October 2025 | jat1 gau2 ji6 ng5 nin4 sap6 jyut6 ji6 sap6 jat6 (sing1 kei4 saam1)"
    - money.csv: "3.75 | saam1 man1 sei3 sap6 ng5 hou4"
    - measure.csv: "a dog | jat1 zek3 gau2"
- numbers.csv can mix numerals and sentences; keep English on the left consistently.

## Formatting rules that matter
- Keep exactly one delimiter per line. If a literal "|" is needed, replace it with "/" or "or".
- Trim leading/trailing spaces in fields, but keep the single space around the pipe.
- Numerals: use commas for thousands (e.g., 1,000) and dot for decimals (e.g., 12.30) to match existing files.
- Parentheses and punctuation are allowed inside fields; do not quote fields.

## Organizing new content
- Add new cards to the end of the most relevant file. Maintain logical ordering:
  - numbers/time: generally ascending or grouped logically before example sentences.
  - lessons: progressive difficulty; mirror nearby patterns and vocabulary.
- New topic? Create a new lower-case CSV at the repo root (e.g., colors.csv) following the same delimiter and column rules.
- Avoid duplicates across files; prefer one canonical phrasing. If variants are needed, add them intentionally and group together.

## Importing into Anki (reference)
- Import as a text file with "Field separator: |" and two fields.
- Map Front = left column, Back = right column. Choose your deck/note type (Basic works).
- For lessons, prompts are Jyutping on the front; for thematic files, prompts are English on the front.

## Quick checklist before committing
- [ ] Two fields only, separated by " | "
- [ ] Column order matches file type (see above)
- [ ] No stray pipes, tabs, or trailing spaces
- [ ] Consistent Jyutping spacing and tone numbers
- [ ] Logical placement/order within the file

If anything above seems mismatched with your intent, leave a short comment in the commit message describing the exception.
