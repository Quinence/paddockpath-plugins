---
name: feed-team-scorecard
description: "PaddockPath's feed team scorecard, from a feedlot's own records through the PaddockPath Feedlot connector: delivered against called, mixing accuracy and short feeds, by staff code. Use it when the feed run is being reviewed: how closely feeds matched the call, which pens went short, how accurately rations were mixed, and who was on the crew. Staff are codes, never names."
---

# Feed team scorecard

Delivered against called, mixing accuracy and short feeds, by staff code. Make it when the feed run is being reviewed: how closely feeds matched the call, which pens went short, how accurately rations were mixed, and who was on the crew. Staff are codes, never names.

The report comes from the PaddockPath Feedlot connector, which reads this feedlot's records and never changes them. The connector makes the report itself, on definitions it keeps in step with the PaddockPath app: follow what it returns, and send no SQL for this report.

## 1. Ask for what it needs

- From (`from`): First day, YYYY-MM-DD. Blank: four weeks ago.
- To (`to`): Last day. Blank: today.

Nothing has to be asked: a blank has the meaning written beside it. Pass what the person gave.

## 2. Make it with the connector

Call the connector's `reports` tool with `id` set to `feed-team-scorecard`, each detail the person gave in its own field under the name above, and `purpose`, one line in their words: it is how they find the report again. The connector runs the report's queries and hands back its definitions, its sections, every section's rows and what to check.

## 3. Check it

Before presenting anything, go through the connector's "Before you present it" list, and use its definitions, in its words. Where a section couldn't be read, or this feedlot doesn't have its records yet, say so rather than working it out another way.

## 4. Build it

Lay the report out in the connector's sections, in their order, and end it with the link into PaddockPath that the connector gives. Call `report_style` before you build it, for the PaddockPath look, unless the person asked for a different one. For a Word document or a PDF, also follow the paddockpath-documents skill.
