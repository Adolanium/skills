---
name: the-row
description: Read the right row of a table, filing, or chart.
license: MIT
---

# The row

A number with no label is not a fact. Open the table, filing, chart, or PDF. Quote the row name, the column name, the unit, and the value from the file itself. If you cannot map those, you do not have the number.

## When to Use

- User asks what a table, chart, PDF, or filing says.
- A claim hangs on one cell ("90 cents", "revenue doubled", "p < 0.05", "program share").
- Extracted text flattened a table and the numbers might be in the wrong order.
- User says "read the row", "which line is that", "don't grab the wrong cell."

Don't use for:

- Deciding whether to buy, share, or sign. Use `hinge` after you have the cell.
- Checking your own marketing copy. Use `own-page`.
- A page with no table, chart, or filing.

## Need first

- The file, URL, or image. Open it. If you cannot, stop and say so.
- If it is an image of a chart, read the image. Do not guess axis text.

## Steps

### 1. Name the question

One sentence: which value, for whom, for which time. If the user asked two questions, split them. One cell per pass.

### 2. Find the right object

Pick the table, figure, or schedule that can answer that question. Say its title. If three tables could fit, do not pick the first one you see. Say why this one.

Open `references/kinds.md` for 990s, company filings, paper results, and charts.

### 3. Bind labels to the value

From the file, write:

- Table or figure title
- Row label (exact words)
- Column label (exact words)
- Unit and scale (dollars, percent, thousands, log)
- Time span
- The value
- Footnotes that change the value

**Hard rule.** Do not report a number unless you can quote the row label and column label from the file. Flattened text order is not a map. If the extract is messy, say Unknown and quote the nearby labels.

### 4. Check the usual traps

- Total vs a part (all funds vs program, year vs quarter)
- Percent of the wrong base
- A restated year sitting next to an old year
- Net vs gross
- Per-share vs whole company
- Axis that does not start at zero, or a broken scale
- Abstract or press line that does not match the table

If any of these would change the answer, say so. Do not "fix" the number.

### 5. Report

Use `templates/report.md`. Short.

If the cell cannot be bound, the finding is Unknown. Do not fill it from memory.

## Watch for

- Taking the first number that matches the claim.
- Using the abstract when a results table exists.
- Dropping the unit or the year.
- Adding two rows that are not meant to be added.

## You're done when

- The question is one sentence.
- The value has a quoted row label, column label, unit, and source.
- Or the finding is Unknown, with the labels you could not map.
