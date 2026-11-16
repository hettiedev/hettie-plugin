---
name: run-an-experiment
description: Run an A/B experiment on a Hettie site - test a new version of a page against the current one and read the results. Use when the person wants to test a page, headline, offer or layout, or asks which version is winning.
---

# Run an A/B experiment on Hettie

Hettie splits a page's visitors between two published pages and counts visitors and leads for each.

1. Experiments are a Labs feature. Check `list_labs`, and turn it on with `set_lab` (`feature: "experiments"`, `on: true`) if the person agrees.
2. The B page must be live on the site first, at its own address such as `/pricing-b`. Read the A page with `get_site_files`, make the B version, and publish it with `publish_site` (for example `pricing-b/index.html`). Keep everything but the change being tested the same.
3. Start it with `start_experiment`: `page` (like `/pricing`), `b_page` (like `/pricing-b`) and an optional `split` such as `80/20`. Without one, the split is 50/50.
4. Read results with `list_experiments` or `get_experiment`. Give visitors and leads for each version and the lead rate. Don't call a winner until each version has at least a few hundred visitors and a clear difference. Say so when it is too early.
5. `stop_experiment` ends it, and everyone sees the original page again. If B won, replace the original page with B in the code and publish.
