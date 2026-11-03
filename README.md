# Caseproof Claude plugins

Claude plugins from Caseproof, the maker of MemberPress. Each plugin is a folder in this repository, and the repository is also a Claude Code plugin marketplace.

| plugin | what it does |
|---|---|
| [`membership-mcp`](membership-mcp/) | Runs your MemberPress membership site from Claude through [membershipmcp.ai](https://membershipmcp.ai). |

## Install in Claude Code

Inside Claude Code, add the marketplace, then install the plugin:

```
/plugin marketplace add caseproof/claude-plugins
/plugin install membership-mcp@caseproof
```

From a terminal, one command does both:

```
claude plugin install membership-mcp --marketplace caseproof/claude-plugins
```

Each plugin's folder has its own README and LICENSE.
