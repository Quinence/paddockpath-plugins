# PaddockPath Feedlot

Your feedlot's PaddockPath records in your own Claude, read-only, with the reports feedlots make from
them again and again. Claude builds each report on the same definitions as the PaddockPath app, so its
figures match the ones you see there, and lays it out in PaddockPath's look, as a Word document or a
PDF if you ask for one.

## What it adds

- **The PaddockPath Feedlot connector**, at `https://feedlot-mcp.paddockpath.com/mcp`.
  It reads your feedlot's records and never changes them. Prices and costs reach only your
  feedlot's admins, and staff appear as codes. Claude and ChatGPT can both connect to it; this
  plugin brings it to Claude with the skills below.
- **A skill for each report:**
  - **Supplier feedback report.** Growth, health, losses and carcass results for one supplier's cattle, against others.
  - **Kill and carcass matching.** A kill sheet matched to your cattle: weight and grading by supplier, lot and days on feed.
  - **Next load planner.** Who's ready for the next load, from forecast weights and days on feed.
  - **Draft-day report.** Gates, weights and gain on feed for one draft through the crush.
  - **Lot performance.** One lot's weigh history, gain, intake, conversion and projected weights.
  - **Head on feed and exits.** Head on feed on any day by sex, class and days on feed, and the ins and outs over a period.
  - **Feed team scorecard.** Delivered against called, mixing accuracy and short feeds, by staff code.
  - **Intake against weather.** Each pen's intake against its own trend through rain, heat and cold.
  - **Mortality and health review.** Deaths and sick pulls over a period: rates, days on feed at death, causes, by supplier.
  - **Invoices for Xero.** One row per invoice, split into feed, health and fees, ready to enter in Xero.
- **PaddockPath documents**: Word and PDF settings for any of them, from the A4 page and its
  letterhead to tables whose header row repeats on every page.

A report's skill asks for what the report needs, has the connector make it, checks it and lays it
out. The skills hold no records and no SQL: the connector makes each report on PaddockPath's current
definitions, so an installed skill doesn't fall behind when PaddockPath improves one.

## Before you start

You need a PaddockPath Feedlot account at a feedlot that has asked PaddockPath to turn on AI access.
Your feedlot's admin can ask us. You sign in with your PaddockPath email and a code we send you, and
the connector then reads only your feedlot's records, as you.

## Add it

Find PaddockPath Feedlot in Claude's directory and add it. Then open the plugin's Connectors tab,
choose Connect, and sign in. On a Team or Enterprise plan, an owner can add the plugin once for
everyone in the organization.

To add it by hand, go to Customize › Plugins › Add › Upload plugin in claude.ai or the Claude desktop
app, and choose a zip:

- `paddockpath-feedlot-0.1.0.zip` adds the connector and the skills.
- `paddockpath-feedlot-skills-0.1.0.zip` adds the skills only, for when you have already added
  PaddockPath Feedlot under Connectors yourself.

In Claude Code, run `/plugin install paddockpath-feedlot --marketplace Quinence/paddockpath-plugins` and sign in from
`/mcp`.

## Connect without the plugin

The connector works on its own, without the skills: in Claude, go to Customize › Connectors › Add ›
Add custom connector; in ChatGPT, go to Plugins › Add › Add custom MCP server. Give either one
`https://feedlot-mcp.paddockpath.com/mcp` and sign in the same way. Ask "What reports can you make from our records?" to
see the reports it offers.

## Use it

Ask in any chat, in your own words. For example:

- What reports can you make from our records?
- Make this year's supplier feedback report for Ridgeway Pastoral, as a Word document.
- Match this kill sheet to our cattle.
- What needs a look today?

## What it sends

The plugin holds no records and sends none itself. When Claude uses the connector, PaddockPath's
server reads your feedlot's records as the person who signed in and answers what Claude asked for.
What Claude reads goes to Anthropic, under your Claude account and its settings. PaddockPath keeps a
log of each request, the query and the reason Claude gave for it, to run the service and improve the
reports. Nothing is ever written to your records. Privacy policy: https://www.paddockpath.com/privacy

## Help

Write to hello@paddockpath.com with a question or a problem, or about turning on AI access.

## Licence

© 2026 Quinence Australia Pty Ltd. PaddockPath customers may use this plugin under the terms in
LICENSE.
