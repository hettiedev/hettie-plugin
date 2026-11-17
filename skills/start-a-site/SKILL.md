---
name: start-a-site
description: Make a new website and publish it on Hettie, or publish changes to a Hettie site. Use when the person wants a new website or landing page, or says "publish this with Hettie". Works in any chat with the Hettie connector.
---

# Start a site on Hettie

> **Not connected yet?** If Hettie's tools (like `list_sites`) aren't available, the Hettie connector isn't signed in. Don't work around it. Tell the person how to connect, then stop: in Claude Code, type `/mcp`, pick `plugin:hettie:hettie` and choose Authenticate; in Codex, run `codex mcp login hettie`; in Claude chat or Cowork, go to Customize > Plugins > Hettie > Connectors and press Connect (claude.ai/customize/plugins); in ChatGPT, add Hettie on chatgpt.com/plugins. They sign in to Hettie and press Allow once.

Hettie hosts the site's files as they are: HTML, CSS, JavaScript, images and fonts. No build step is needed.

1. Ask for what you don't know: the business, who the site is for, the one thing visitors should do, and the pages.
2. Write each page as plain HTML with its CSS (Tailwind from a CDN is fine). Give every page a title and description, every image alt text, and a layout that works on a phone.
3. Forms post to `/forms/<name>`, like `<form method="post" action="/forms/contact">`. Hettie saves each reply as a lead, emails the owner, and sends the visitor back with `?sent=1`. Don't use `/forms/` or `/_hettie/` for anything else.
4. Show the person the pages, then publish when they say so: `publish_site` with a new `site` name, each page as `index.html`, `about/index.html` and so on with its `content`, and images by `url` or `base64`. It goes live at `<name>.xtwelve.io`. Every publish is a version, and `undo` puts the previous one back.
5. To change a page later, read it with `get_site_files`, edit it, and publish just that file.
6. For their own domain, use `add_domain`. Show the DNS records exactly as returned, and check with `get_domains` after they add them. Hettie never changes their DNS.

Blog posts are written with the write-post skill. They show at `/blog` in the site's own header and footer, unless the site has its own blog pages.
