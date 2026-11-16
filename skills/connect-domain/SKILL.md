---
name: connect-domain
description: Put a Hettie site on the person's own domain, like www.example.com or example.com, and check it's live. Use when the person wants their own domain, asks to switch a domain to Hettie, or a domain isn't working.
---

# Connect a domain on Hettie

Hettie never changes the person's DNS. They add the records at their registrar, and Hettie checks them.

1. Find the site with `list_sites` unless the person named it.
2. `add_domain` with the domain they own. Connecting `example.com` also sets up `www.example.com`, and one forwards to the other (`set_domain_www` picks which).
3. Show the DNS records exactly as returned, with the registrar's steps if Hettie gives them. Ask the person to add them, and to remove old records for the same name (from a previous host).
4. When they say they're done, check with `get_domains`. It shows each domain as Live, Setting up, Action needed or Not reachable, with what's missing. DNS can take a few minutes, sometimes up to an hour.
5. When it's Live, the site answers on the domain with HTTPS. If the domain came from another host, they can then turn the old site off there.
