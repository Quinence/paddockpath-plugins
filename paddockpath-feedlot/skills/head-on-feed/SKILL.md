---
name: head-on-feed
description: "PaddockPath's head on feed and exits, from a feedlot's own records through the PaddockPath Feedlot connector: head on feed on any day by sex, class and days on feed, and the ins and outs over a period. Use it when someone needs the head count on a day (month end, an audit, a bank or an owner), how long the cattle have been on feed, or what came in and left over a period, and how."
---

# Head on feed and exits

Head on feed on any day by sex, class and days on feed, and the ins and outs over a period. Make it when someone needs the head count on a day (month end, an audit, a bank or an owner), how long the cattle have been on feed, or what came in and left over a period, and how.

The report comes from the PaddockPath Feedlot connector, which reads this feedlot's records and never changes them. The connector makes the report itself, on definitions it keeps in step with the PaddockPath app: follow what it returns, and send no SQL for this report.

## 1. Ask for what it needs

- On the day (`on`): The day to count head on feed, YYYY-MM-DD, within the last 24 months. Blank: today.
- Period from (`from`): First day of the period for arrivals and exits. Blank: the 1st of this month.
- Period to (`to`): Last day of the period. Blank: today.

Nothing has to be asked: a blank has the meaning written beside it. Pass what the person gave.

## 2. Make it with the connector

Call the connector's `reports` tool with `id` set to `head-on-feed`, each detail the person gave in its own field under the name above, and `purpose`, one line in their words: it is how they find the report again. The connector runs the report's queries and hands back its definitions, its sections, every section's rows and what to check.

## 3. Check it

Before presenting anything, go through the connector's "Before you present it" list, and use its definitions, in its words. Where a section couldn't be read, or this feedlot doesn't have its records yet, say so rather than working it out another way.

## 4. Build it

Lay the report out in the connector's sections, in their order, and end it with the link into PaddockPath that the connector gives. Call `report_style` before you build it, for the PaddockPath look, unless the person asked for a different one. For a Word document or a PDF, also follow the paddockpath-documents skill.
