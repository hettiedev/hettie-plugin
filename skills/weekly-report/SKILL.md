---
name: weekly-report
description: Report how the person's Hettie sites are doing - visits, leads, lead rate, top sources and what changed. Use when they ask how their sites or marketing are doing, for a weekly or monthly report, or where their leads come from.
---

# Weekly report for Hettie sites

Use the Hettie connector's tools. Numbers come from the tools, never from memory or an earlier answer.

1. `list_sites` with `days: 7` (or the period the person asked for) gives every site's engaged visitors, leads, lead rate, top source and, with Google Ads connected, cost per lead. Call it again with `days: 14` to compare with the week before.
2. For each site with visits, call `get_analytics` for the top pages, sources, countries and devices.
3. For sites with new leads, call `list_leads` and summarise who got in touch and what they asked about. Don't repeat email addresses or phone numbers unless the person asks.

Write it short:

- One line per site: visitors, leads and lead rate, and the change from the week before.
- The source that brought the most leads, and any page that got many visits but no leads.
- One or two things worth doing next, such as writing a post on a topic people search for (see the write-post skill), or testing a new version of a page that gets visits but no leads (see the run-an-experiment skill).

Say plainly when a site has too few visits to draw a conclusion.
