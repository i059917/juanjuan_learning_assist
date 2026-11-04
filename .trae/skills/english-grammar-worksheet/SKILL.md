---
name: english-grammar-worksheet
description: Generate printable English grammar fill-in-the-blank worksheets in Markdown for primary school students. Use when the user asks for an English worksheet, exercise sheet, practice sheet, or grammar drill on any tense or grammar topic. Do not use for answering standalone grammar questions or writing essays.
---

# English Grammar Worksheet Generator

Generate a Markdown worksheet where each item has exactly one blank and the target verb's base form is given in brackets. Output is optimized for printing page by page.

## Workflow

1. Confirm the target directory. Default to the grade/subject folder matching the request (for example `小学英语三年级/`). If no folder matches, ask once, otherwise use the workspace root.
2. Decide the grammar scope from the request. Default when unspecified: simple present tense.
3. Draft the items, keeping the constraint checklist below satisfied.
4. Write the file as `英语<语法点>练习题单.md` inside the target directory.
5. Report the path with a `computer://` link.

## Required Structure

- Each page starts with a level-2 heading: `## 第 N 页 · <主题描述>`
- One instruction line under each heading: `每题只有一个空格，请在横线上填入括号中动词的正确形式。`
- 16 items per page, numbered 1-16 restarting per page
- Blank written as `______` and the base form in brackets: `______ (play)`
- Separate pages with `<!-- pagebreak -->`
- Filename and headings in Chinese

## Hard Constraints

- Every page is a **mixed** page: blend affirmative, negative, interrogative, and modal items on every page. Never dedicate a whole page to a single sentence type.
- **Do not include a reference answer section.** The user asked for a blank worksheet only. Never add 参考答案, 答案, a key, an error-tracking table, or a 错题整理 table.
- **Do not include knowledge tables or rules sections.** No 速查表, no grammar explanation, no reference lists, no checklist of common mistakes.
- **Do not include a header block** with 姓名 / 日期 / 得分 / 班级 fields.
- Keep the file to questions only, so each page can be printed and handed out standalone.

## Content Coverage Rules

Balance the mix across the whole sheet:

- Be verbs are supporting items only — roughly 3-4 per page, never the focus.
- The main mass is ordinary verbs: third-person singular `-s` / `-es` changes, `has` / `does` as lexical verbs, and modal verbs `can` / `must`.
- Cover all three persons in both singular and plural, and cross them: `he/she/it`, `I`, `you/we/they`, singular nouns, plural nouns. Within a single item, contrast a singular subject with a plural one to force the form choice.
- Negative sentences: give both forms of the hint across items — `(not like)` and `(do not like)` — so students practise `doesn't like` and `does not like`.
- Interrogatives: mix `Do` / `Does` / `Have` / `Has` questions with special questions (`How often`, `What time`, `Where`).
- `does` and `has` are followed by the base verb form; the base form must not be marked with `-s`.
- Use `have` / `has` only as **ordinary verbs** (`have a fever`, `have a meeting`, `have a dictionary`, `have a bike`). Do **not** use perfect/perfect-continuous structures such as `have been to`, `have finished`, `have you finished`.
- Include one or two items per page with two blanks contrasting a singular and a plural subject.
- Keep sentences at primary-school vocabulary level, short and natural.

## Verification Before Finishing

Check the generated file:

- No 参考答案 / no 错题整理 / no 速查表 / no 姓名日期得分
- Every page has 16 items and its own `##` heading
- Every page contains affirmative, negative, interrogative and modal items
- No `has been` / `have been` / `have finished` anywhere
- Base form in brackets is the bare verb, never an inflected form
