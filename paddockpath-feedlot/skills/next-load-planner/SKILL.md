---
name: next-load-planner
description: "PaddockPath's next load planner, from a feedlot's own records through the PaddockPath Feedlot connector: who's ready for the next load, from forecast weights and days on feed. Use it when a load is being planned: which head will be heavy enough and long enough on feed by the load day, out of withholding, and how recent loads to the same place compared."
---

# Next load planner

Who's ready for the next load, from forecast weights and days on feed. Make it when a load is being planned: which head will be heavy enough and long enough on feed by the load day, out of withholding, and how recent loads to the same place compared.

The report comes from the PaddockPath Feedlot connector, which reads this feedlot's records and never changes them. The connector makes the report itself, on definitions it keeps in step with the PaddockPath app: follow what it returns, and send no SQL for this report.

## 1. Ask for what it needs

- Load day (`load_date`): The day the load leaves, YYYY-MM-DD. Blank: a week from today.
- Lightest weight (`min_kg`): Forecast weight a head must reach by the load day, in kg. Blank: any weight.
- Fewest days on feed (`min_days`): Days on feed a head must have by the load day. Blank: any.
- Breed (`breed`): Only this breed, as PaddockPath names it. Blank: every breed.
- Sex (`sex`): M for steers and bulls, F for heifers and cows. Blank: both.
- Going to (`destination`): Part of the destination's name, to compare with the last loads there. Blank: every destination.

Nothing has to be asked: a blank has the meaning written beside it. Pass what the person gave.

## 2. Make it with the connector

Call the connector's `reports` tool with `id` set to `next-load-planner`, each detail the person gave in its own field under the name above, and `purpose`, one line in their words: it is how they find the report again. The connector runs the report's queries and hands back its definitions, its sections, every section's rows and what to check.

## 3. Check it

Before presenting anything, go through the connector's "Before you present it" list, and use its definitions, in its words. Where a section couldn't be read, or this feedlot doesn't have its records yet, say so rather than working it out another way.

## 4. Build it

Lay the report out in the connector's sections, in their order, and end it with the link into PaddockPath that the connector gives. Call `report_style` before you build it, for the PaddockPath look, unless the person asked for a different one. For a Word document or a PDF, also follow the paddockpath-documents skill.
