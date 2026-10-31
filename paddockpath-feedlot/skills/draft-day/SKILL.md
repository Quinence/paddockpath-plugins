---
name: draft-day
description: "PaddockPath's draft-day report, from a feedlot's own records through the PaddockPath Feedlot connector: gates, weights and gain on feed for one draft through the crush. Use it when a draft has run, or someone asks how one went: each gate's rule and destination, how many head went through each, their weights and gain on feed, and by supplier."
---

# Draft-day report

Gates, weights and gain on feed for one draft through the crush. Make it when a draft has run, or someone asks how one went: each gate's rule and destination, how many head went through each, their weights and gain on feed, and by supplier.

The report comes from the PaddockPath Feedlot connector, which reads this feedlot's records and never changes them. The connector makes the report itself, on definitions it keeps in step with the PaddockPath app: follow what it returns, and send no SQL for this report.

## 1. Ask for what it needs

- Draft (`session`): The run, by its name in PaddockPath. Blank: the latest draft.

Nothing has to be asked: a blank has the meaning written beside it. Pass what the person gave.

## 2. Make it with the connector

Call the connector's `reports` tool with `id` set to `draft-day`, each detail the person gave in its own field under the name above, and `purpose`, one line in their words: it is how they find the report again. The connector runs the report's queries and hands back its definitions, its sections, every section's rows and what to check. When a name it needs is missing or isn't in the records, it lists the ones there are: choose from those or ask the person, rather than looking them up yourself, and call it again.

## 3. Check it

Before presenting anything, go through the connector's "Before you present it" list, and use its definitions, in its words. Where a section couldn't be read, or this feedlot doesn't have its records yet, say so rather than working it out another way.

## 4. Build it

Lay the report out in the connector's sections, in their order, and end it with the link into PaddockPath that the connector gives. Call `report_style` before you build it, for the PaddockPath look, unless the person asked for a different one. For a Word document or a PDF, also follow the paddockpath-documents skill.
