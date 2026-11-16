# Hettie plugin for Claude

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

## Install

Claude Code:

```
claude plugin marketplace add hettiedev/hettie-plugin
claude plugin install hettie@hettie
```

Claude on the web, desktop and mobile without the plugin: Settings > Connectors > Add custom connector, with the URL `https://app.hettie.dev/mcp`.

Sites are published as their files (HTML, CSS, JavaScript, images) straight from the chat, with no build step.
