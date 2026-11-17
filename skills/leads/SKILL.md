---
name: leads
description: Show and follow up on the leads from a Hettie site's forms - who got in touch, what they asked, and where they came from. Use when the person asks about leads, form replies, enquiries, contact messages or sign-ups on their Hettie site.
---

# Leads on Hettie

> **Not connected yet?** If Hettie's tools (like `list_sites`) aren't available, the Hettie connector isn't signed in. Don't work around it. Tell the person how to connect, then stop: in Claude Code, type `/mcp`, pick `plugin:hettie:hettie` and choose Authenticate; in Codex, run `codex mcp login hettie`; in Claude chat or Cowork, go to Customize > Plugins > Hettie > Connectors and press Connect (claude.ai/customize/plugins); in ChatGPT, add Hettie on chatgpt.com/plugins. They sign in to Hettie and press Allow once.

Every form on a Hettie site posts to `/forms/<name>`. Hettie saves each reply as a lead, emails it to the owner, and records where the visitor came from.

1. Find the site with `list_sites` unless the person named it.
2. `list_leads` gives the site's forms and their leads, newest first. Pass `form` for one form.
3. Summarise: how many leads and from which forms, what people asked for, and the source of each (from `get_analytics` or `list_sites`, which give leads by source and the lead rate).
4. Show names and messages, but don't repeat email addresses or phone numbers unless the person asks.
5. If they want to reply, draft the replies for them to send. Hettie doesn't send them.

To add a form to a page, see the start-a-site skill: a plain HTML form with `action="/forms/<name>"`, published with `publish_site`. Lead emails go to the address in the site's settings (`update_site_settings` with `notify_email`).
