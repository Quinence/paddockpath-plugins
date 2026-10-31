---
name: supplier-feedback
description: "PaddockPath's supplier feedback report, from a feedlot's own records through the PaddockPath Feedlot connector: growth, health, losses and carcass results for one supplier's cattle, against others. Use it when a supplier's cattle are being reviewed, or a report is going back to the supplier: how their cattle grew, got sick, died and graded against similar cattle from other suppliers."
---

# Supplier feedback report

Growth, health, losses and carcass results for one supplier's cattle, against others. Make it when a supplier's cattle are being reviewed, or a report is going back to the supplier: how their cattle grew, got sick, died and graded against similar cattle from other suppliers.

The report comes from the PaddockPath Feedlot connector, which reads this feedlot's records and never changes them. The connector makes the report itself, on definitions it keeps in step with the PaddockPath app: follow what it returns, and send no SQL for this report.

## 1. Ask for what it needs

- Supplier (`supplier`, needed): The supplier (source partner) as PaddockPath names them.
- Arrived from (`from`): First arrival day counted, YYYY-MM-DD. Blank: 1 January this year.
- Arrived to (`to`): Last arrival day counted. Blank: today.
- Compare with breeds (`breeds`): Breeds the other suppliers' cattle must be, separated by commas. Blank: the breeds this supplier sent.

Ask only for what is needed and not yet said. Pass anything else the person gave; a blank has the meaning written beside it.

## 2. Make it with the connector

Call the connector's `reports` tool with `id` set to `supplier-feedback`, each detail the person gave in its own field under the name above, and `purpose`, one line in their words: it is how they find the report again. The connector runs the report's queries and hands back its definitions, its sections, every section's rows and what to check. When a name it needs is missing or isn't in the records, it lists the ones there are: choose from those or ask the person, rather than looking them up yourself, and call it again.

## 3. Check it

Before presenting anything, go through the connector's "Before you present it" list, and use its definitions, in its words. Where a section couldn't be read, or this feedlot doesn't have its records yet, say so rather than working it out another way.

## 4. Build it

Lay the report out in the connector's sections, in their order, and end it with the link into PaddockPath that the connector gives. Call `report_style` before you build it, for the PaddockPath look, unless the person asked for a different one. For a Word document or a PDF, also follow the paddockpath-documents skill.
