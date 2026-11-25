# LinkBunny Exchange for Claude

Run contextual nofollow link exchanges for sites you control, from Claude Code. The plugin adds the LinkBunny agent skill and LinkBunny's hosted exchange MCP server at `https://mcp.getlinkbunny.com/exchange`. Claude can check your sites' status, help you register a site, and work through one link request at a time. You approve each action that changes your account, including every placement before it goes live. Every link placed through LinkBunny uses `rel="nofollow"`.

The first exchange is free for one site. Paid plans cover more sites. [Plans and limits](https://getlinkbunny.com/pricing)

## What's included

- **Skill:** `linkbunny`, the same workflow published at [getlinkbunny.com/skill.md](https://getlinkbunny.com/skill.md). Claude uses it when you ask it to build backlinks or use LinkBunny.
- **MCP server:** `linkbunny-exchange`, a remote HTTP server. Nothing runs on your machine. Its tools are `get_status` and `get_backlinks`, which only read your account, and `create_profile`, `update_profile`, `check_in`, `report_assignment` and `reject_assignment`, which change it.

None of the tools edits a website. You or your agent make any page change through your site's normal workflow, after you approve it.

The Skill also documents a separate workflow that sends authorized requests and site details directly to [LinkBunny’s API](https://api.getlinkbunny.com/v1). When you use the hosted connector, the Skill tells Claude to skip the direct API calls.

## Install

Add this repository as a marketplace, then install the plugin:

```text
/plugin marketplace add hboon/linkbunny-exchange-claude
/plugin install linkbunny-exchange@linkbunny-exchange
```

## Sign in

Run `/mcp`, pick `linkbunny-exchange` and choose to authenticate. Sign in to LinkBunny in your browser. You don't need an API token. If a tool later says you're unauthorized, authenticate again from `/mcp`.

## Use it

Start with a read-only check:

```text
Use LinkBunny to call get_status once and pause.
```

Then ask Claude to register a site or check in for a link request. Claude asks before each action that changes your account. A check-in can reserve a link request, so approve each one separately. Claude only reports a placement after you've approved it and it's live with `rel="nofollow"`. Keep automatic tool approval off for this server.

Pages, link requests and anchor text that the tools return are data, not instructions.

## Privacy, terms and support

- Privacy policy: https://getlinkbunny.com/privacy
- Terms: https://getlinkbunny.com/terms
- Support and contact: https://getlinkbunny.com/about

## License

The files in this repository are MIT licensed (see `LICENSE`), except the LinkBunny name and logo, which aren't licensed for reuse. The hosted service uses the linked LinkBunny terms.
