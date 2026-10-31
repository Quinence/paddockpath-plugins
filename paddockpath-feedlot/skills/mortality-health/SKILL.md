---
name: mortality-health
description: "PaddockPath's mortality and health review, from a feedlot's own records through the PaddockPath Feedlot connector: deaths and sick pulls over a period: rates, days on feed at death, causes, by supplier. Use it when losses or sickness are being reviewed for the feedlot as a whole: how the death rate moved month to month, when on feed cattle died, of what, how many were pulled sick, and which suppliers' cattle fared worst."
---

# Mortality and health review

Deaths and sick pulls over a period: rates, days on feed at death, causes, by supplier. Make it when losses or sickness are being reviewed for the feedlot as a whole: how the death rate moved month to month, when on feed cattle died, of what, how many were pulled sick, and which suppliers' cattle fared worst.

The report comes from the PaddockPath Feedlot connector, which reads this feedlot's records and never changes them. The connector makes the report itself, on definitions it keeps in step with the PaddockPath app: follow what it returns, and send no SQL for this report.

## 1. Ask for what it needs

- From (`from`): First day, YYYY-MM-DD. Blank: a year ago.
- To (`to`): Last day. Blank: today.

Nothing has to be asked: a blank has the meaning written beside it. Pass what the person gave.

## 2. Make it with the connector

Call the connector's `reports` tool with `id` set to `mortality-health`, each detail the person gave in its own field under the name above, and `purpose`, one line in their words: it is how they find the report again. The connector runs the report's queries and hands back its definitions, its sections, every section's rows and what to check.

## 3. Check it

Before presenting anything, go through the connector's "Before you present it" list, and use its definitions, in its words. Where a section couldn't be read, or this feedlot doesn't have its records yet, say so rather than working it out another way.

## 4. Build it

Lay the report out in the connector's sections, in their order, and end it with the link into PaddockPath that the connector gives. Call `report_style` before you build it, for the PaddockPath look, unless the person asked for a different one. For a Word document or a PDF, also follow the paddockpath-documents skill.
