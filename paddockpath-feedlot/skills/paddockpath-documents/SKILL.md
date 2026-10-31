---
name: paddockpath-documents
description: "Word documents and PDFs in PaddockPath's look for anything made from a feedlot's PaddockPath records: A4 pages, type and colours, a letterhead, tables whose header row repeats on every page, and pages numbered Page X of Y. Use it when a report or table from the PaddockPath Feedlot connector is wanted as a .docx or .pdf file, or to print or send to a supplier, an owner or a buyer."
---

# PaddockPath documents

For a report or table made from a feedlot's PaddockPath records that is wanted as a Word document or a PDF. Call the PaddockPath Feedlot connector's `report_style` first: it names the feedlot and the day for the letterhead and footer, and gives the look in full. The settings below carry that look onto paper. When the person asks for a different look, their own branding or none, do that instead.

## Page

A4 portrait, 210 × 297 mm, with 15 mm margins on every side, which leaves 180 mm for the text.

## Type

Arial throughout, or Helvetica where a PDF tool has no Arial: Switzer, PaddockPath's face on screen, is seldom installed where a document is opened. Regular weight only, never bold.

- Document title and key figures: 22 pt, #0A0A0A.
- Section titles: 14 pt, #0A0A0A.
- Body text, table cells and figures: 11 pt, #0A0A0A; secondary text #3A3A3A.
- Notes, units and the footer: 9 pt, #5F5E5A.
- Labels and column heads: 8 pt capitals, letter-spaced 0.5 pt, #5F5E5A.

Nothing paler than #5F5E5A carries text. #0B5FFF is only for the stripe and the word Feedlot in the brand line: no other coloured text, and no fills, shading, boxes or shadows.

## The first page

1. The stripe: a 3 pt #0B5FFF rule across the text width at the top of the page.
2. The letterhead: "PaddockPath" in #0A0A0A and "Feedlot" in #0B5FFF, 14 pt, on the left; on the right, the feedlot's name in 11 pt over the day in 9 pt #5F5E5A.
3. The kind of report as a label, the title, and two to four label and value pairs: the period, the pens, the head, who it is for.

Later pages carry no letterhead: only the footer, and the header row of a table that runs on.

## The footer, on every page

9 pt #5F5E5A over a 1 pt #E5EAF0 rule: "Prepared with [Claude or ChatGPT, whichever you are] from [feedlot]'s PaddockPath records, [day]" on the left, and "paddockpath.com · Page 2 of 4" on the right. In Word, the numbers are PAGE and NUMPAGES fields (docx-js: PageNumber.CURRENT and PageNumber.TOTAL_PAGES). In a PDF, draw them once the total is known (reportlab: a canvas that holds each page until the document is laid out, then draws every footer with the total).

## Sections

24 pt before each section. Its title is 14 pt, with a 1 pt #E5EAF0 rule 12 pt below it.

## Tables

- Column heads are labels over a 1 pt #0A0A0A rule, and the header row repeats at the top of every page (Word: mark the first row as a header row; reportlab: repeatRows=1).
- Rows are 11 pt with a 0.5 pt #CBD3DC rule between them, none above the first; 7 pt above and below each cell's text and 8 pt either side.
- Text left, figures right. A total sits under a 1 pt #0A0A0A rule.
- No outer border, no vertical rules, no fills and no zebra rows. A row never breaks across a page (Word: turn off "allow row to break across pages").
- A table fits the 180 mm between the margins. When one doesn't, split its columns into two tables, each with its own label.

## Numbers

en-AU: $1,234.56, 5,182, 21 Oct 2026. A unit follows its figure in 9 pt #5F5E5A: 412 kg. Missing is an em dash in #5F5E5A, never 0 or a blank. Money is never shortened. A change carries its sign (+4.2%); a share does not (38.1%).

## Status

A word with its mark on a ground of its hue at 8%, never colour alone: ✓ Verified in #2E7D32 on #EEF5EF, ▲ Estimated in #B45309 on #F9F1EB, ✕ Disputed in #C0392F on #FAEFEE, and ● Draft in #5F5E5A on no ground.

## Charts

Placed as images at twice their printed size, or drawn as vectors in a PDF. Series in this order, at most four: #000000, #4D4D4D, #8C8C8C, #C2C2C2, with #0B5FFF for the one series the eye should go to. Horizontal gridlines only, 0.5 pt #E5EAF0, a #5F5E5A zero line and no frame; axis labels 9 pt #5F5E5A; bars start at zero. No pie, donut, area fill, gradient, shadow or 3D. Every figure a chart shows is also in a table or the text.

## In Word's own units

Word sets a page and its spacing in twentieths of a point (twips), type in half-points and borders in eighths of a point, and writes a colour without its #.

- Page 11906 × 16838; margins 850; text width 10206.
- Type: title 44, section titles 28, body 22, notes 18, labels 16, with label letter spacing 10.
- Borders: the stripe 24, heavy rules 8, hair rules 4.
- Cell margins 140 above and below and 160 either side; 480 before a section and 240 under its title.

## Making it

- Wanted as both Word and PDF: build the Word document, then convert it (LibreOffice: soffice --headless --convert-to pdf), so the two match and the page numbers fill in.
- Before handing it over, render the pages and look: the stripe and letterhead on the first page only, "Page X of Y" filled in on every page, the header row repeated where a table runs on, no row split across a page, nothing past the margins.
