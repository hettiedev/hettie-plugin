---
name: move-from-chatgpt-sites
description: Move a website made with ChatGPT Sites (or any plain HTML site) to Hettie, keeping every page, design, text and URL. Use when the person wants to move or migrate a ChatGPT site or another HTML site to Hettie. Works in any Claude chat with the Hettie connector.
---

# Move a ChatGPT site to Hettie

The ChatGPT site stays live until the domain is switched, so nothing breaks while you move. Hettie serves the files as they are, so the move is a copy, not a rebuild.

1. List the site's pages, by reading the home page's links (and the sitemap if it has one), and its forms. Show the list to the person before you start.
2. For each page, read its HTML from the live site. Keep it exactly as it is, apart from these changes:
   - Each form posts to `/forms/<name>`, like `<form method="post" action="/forms/contact">`, keeping its field names. Each reply becomes a lead in Hettie, emailed to the owner. If a form is sent by JavaScript, make it a plain form that posts there.
   - Remove ChatGPT Sites' own scripts and tracking, if any. Hettie adds its own analytics.
3. Publish with `publish_site`. Use `site` for the new site's name, give each page as `about/index.html` with its `content`, and give styles, scripts, fonts and images by their `url` on the live site. Hettie fetches them. Keep the same paths, so `/about` stays `/about`. For more than about 20 files, publish in several calls; only the files given change each time.
4. It goes live at `<name>.xtwelve.io` while the old site keeps running. Ask the person to open both side by side and check every page and form. To fix a page, read it with `get_site_files`, change it, and publish just that file. `undo` takes a publish back.
5. Blog posts become Hettie posts with `create_post` (see the write-post skill), and the person publishes each one.
6. To switch the domain, use `add_domain`. At their registrar the person adds the records Hettie shows. When `get_domains` says it's live, the site is on their domain with HTTPS. Hettie never changes their DNS.

Don't add features or change the text. If something can't move, such as a login or server code, stop and tell the person.
