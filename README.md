# Hettie plugin for Claude, ChatGPT and Codex

Publish and run websites made with Claude on [Hettie](https://hettie.dev): posts, leads, analytics, media, domains and A/B experiments.

The plugin is the Hettie connector (a remote MCP at `https://app.hettie.dev/mcp`, signed in with your Hettie account) plus skills:

| Skill | What it does | Works in |
| --- | --- | --- |
| `write-post` | Draft, edit, schedule and publish blog posts | Everywhere |
| `weekly-report` | Visits, leads and top sources across your sites | Everywhere |
| `run-an-experiment` | A/B test a page and read the results | Everywhere |
| `start-a-site` | Make a site and publish it | Everywhere |
| `move-from-lovable` | Move a Lovable site to Hettie | Everywhere (needs the code on GitHub) |
| `move-from-chatgpt-sites` | Move a ChatGPT or HTML site to Hettie | Everywhere |
| `leads` | Who got in touch through the site's forms, and from where | Everywhere |
| `connect-domain` | Put a site on your own domain and check it's live | Everywhere |

## Install

**Claude Code**

```
claude plugin marketplace add hettiedev/hettie-plugin
claude plugin install hettie@hettie
```

Then connect it once: type `/mcp`, pick `plugin:hettie:hettie`, choose **Authenticate**, sign in to Hettie and press Allow. Claude Code doesn't prompt for this on its own.

**Claude chat and Cowork**: add the marketplace `hettiedev/hettie-plugin` under Customize > Plugins, install Hettie, then open its **Connectors** tab and press **Connect** (sign in to Hettie, press Allow).

**Codex**

```
codex plugin marketplace add hettiedev/hettie-plugin
codex plugin add hettie@hettie
```

Then sign in to Hettie when Codex asks (or run `codex mcp login hettie`).

**ChatGPT desktop app**: add the same marketplace (`hettiedev/hettie-plugin`) in Codex as above, restart the app, and install Hettie from the Plugins directory under the Hettie marketplace.

**Without the plugin**: add the connector `https://app.hettie.dev/mcp` in Claude (Settings > Connectors > Add custom connector) or ChatGPT (developer mode, Settings > Apps & Connectors).

One folder serves every host: `.claude-plugin/` and `.mcp.json` for Claude, `plugin.json` (Agent Plugins 1.0.0, with `extensions.com.openai`), `mcp.json` and `.agents/plugins/marketplace.json` for ChatGPT and Codex, and the same `skills/`.

Sites are published as their files (HTML, CSS, JavaScript, images) straight from the chat, with no build step.
