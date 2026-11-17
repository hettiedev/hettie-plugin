---
name: write-post
description: Write, edit, schedule or publish a blog post on a Hettie site. Use when the person asks for a blog post, article or news item on their Hettie site, or to change, schedule or take down one.
---

# Write a post on Hettie

> **Not connected yet?** If Hettie's tools (like `list_sites`) aren't available, the Hettie connector isn't signed in. Don't work around it. Tell the person how to connect, then stop: in Claude Code, type `/mcp`, pick `plugin:hettie:hettie` and choose Authenticate; in Codex, run `codex mcp login hettie`; in Claude or ChatGPT on the web, connect Hettie under Connectors or Plugins. They sign in to Hettie and press Allow once.

Posts live in Hettie, not in the site's files, so they go live without publishing the site again. Use the Hettie connector's tools.

1. Find the site with `list_sites` unless the person named it. Read `list_posts` to match the tone and avoid repeating a topic.
2. Draft the post and show it to the person before saving, unless they asked you to go ahead.
3. Save it as a draft with `create_post`: `title`, `body`, and a `description` of at most 160 characters for search and link previews. Add `tags` when the site uses them. Leave `slug` out to have it made from the title.
4. Publish only when the person says so: `publish_post`, with `date` (ISO, like `2026-12-01T09:00:00Z`) to schedule it. Otherwise tell them it is a draft they can read in Hettie under Posts.
5. To change a post, use `get_post`, then `update_post` with only the fields that change. A published post changes on the site at once. `post_history` and `restore_post` go back to an earlier save.

## The body

Markdown, plus these Markdoc tags:

```
{% button href="/contact/" %}Book a tasting{% /button %}
{% image src="/_hettie/media/oven.jpg" alt="The oven" caption="Fresh at six" width="wide" /%}   (width: normal, wide or full)
{% embed url="https://www.youtube.com/watch?v=…" /%}                                            (YouTube or Vimeo)
{% callout %}Closed on Mondays.{% /callout %}
```

HTML in a post is shown as text, not run.

## Images

- **Unsplash**: `search_unsplash`, then `feature_image: "unsplash:<id>"` or `{% image src="unsplash:<id>" alt="…" /%}` in the body. Hettie picks the photo, keeps it on Unsplash and credits the photographer. Keep that credit.
- **The person's own image at a public URL**: `upload_media_from_url`, then use the URL it returns.
- **Already uploaded**: `list_media` shows the site's files and their URLs.

Every image needs alt text that says what it shows.
