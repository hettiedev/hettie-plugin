---
name: move-from-lovable
description: Move a website made in Lovable to Hettie, keeping its design, text and URLs. Use when the person wants to move, migrate or copy a Lovable site to Hettie. Needs the Lovable project's code (GitHub) and the Hettie connector.
---

# Move a Lovable site to Hettie

This is for Lovable projects that are websites: a few pages and forms. Sites where people log in, have accounts or pay inside the app should stay on Lovable. If you find a login or live data, stop and tell the person before going further.

You need the code: in Lovable the person connects GitHub, and you read that repository (with the GitHub connector, or a clone in Claude Code). Nothing changes on Lovable while you move.

Lovable sites are React, Vite, Tailwind and shadcn, often with Supabase. Hettie serves plain files, so turn each page into HTML:

- Each route in `src/App.tsx` becomes an HTML page at the same address (`/about` is `about/index.html`).
- Copy the colors and fonts from `src/index.css`, and keep the same Tailwind classes (Tailwind from a CDN, or the built CSS).
- Replace shadcn components with plain HTML that looks the same. Keep JavaScript only where the page needs it.
- Point every form at `/forms/<name>`, keeping the field names. Replies that went to Supabase now become Hettie leads, emailed to the owner. Old replies stay in Supabase; the person can export that table as CSV.
- Give images by their `url` on the live site, or `base64`.
- Never copy Supabase keys or other secrets.

Keep the design, text and URLs exactly the same, and don't add features.

Publish a test version with `publish_site` and ask the person to open it beside the Lovable site, on a laptop and a phone, and check every page.

To switch the domain, use `add_domain`. At their registrar they replace Lovable's records with the ones Hettie shows. When `get_domains` says the domain is live, they remove it in Lovable's settings. The Lovable project stays, so they can switch back.
