---
name: kill-carcass-matching
description: "PaddockPath's kill and carcass matching, from a feedlot's own records through the PaddockPath Feedlot connector: a kill sheet matched to your cattle: weight and grading by supplier, lot and days on feed. Use it when a kill sheet or carcass feedback has come back and the person wants it against their cattle: who grew which carcasses, by supplier, lot or days on feed. These queries read a kill already imported into PaddockPath. For a file that isn't (a myMSA export, a kill sheet or genetics file), read its tags and call match_animals instead, 500 tags a call, and group what it returns."
---

# Kill and carcass matching

A kill sheet matched to your cattle: weight and grading by supplier, lot and days on feed. Make it when a kill sheet or carcass feedback has come back and the person wants it against their cattle: who grew which carcasses, by supplier, lot or days on feed. These queries read a kill already imported into PaddockPath. For a file that isn't (a myMSA export, a kill sheet or genetics file), read its tags and call match_animals instead, 500 tags a call, and group what it returns.

The report comes from the PaddockPath Feedlot connector, which reads this feedlot's records and never changes them. The connector makes the report itself, on definitions it keeps in step with the PaddockPath app: follow what it returns, and send no SQL for this report.

## 1. Ask for what it needs

- Kill sheet (`kill`): The kill sheet's code, its job name, or the kill day as YYYY-MM-DD. Blank: the latest kill.

Nothing has to be asked: a blank has the meaning written beside it. Pass what the person gave.

## 2. Make it with the connector

Call the connector's `reports` tool with `id` set to `kill-carcass-matching`, each detail the person gave in its own field under the name above, and `purpose`, one line in their words: it is how they find the report again. The connector runs the report's queries and hands back its definitions, its sections, every section's rows and what to check.

## 3. Check it

Before presenting anything, go through the connector's "Before you present it" list, and use its definitions, in its words. Where a section couldn't be read, or this feedlot doesn't have its records yet, say so rather than working it out another way.

## 4. Build it

Lay the report out in the connector's sections, in their order, and end it with the link into PaddockPath that the connector gives. Call `report_style` before you build it, for the PaddockPath look, unless the person asked for a different one. For a Word document or a PDF, also follow the paddockpath-documents skill.
