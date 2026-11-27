# Membership MCP for Claude

Run your MemberPress membership site from Claude. Ask about members, memberships, subscriptions, transactions, coupons and access rules, or ask Claude to make a change, and it works on your site through Membership MCP.

## Before you start

- Your WordPress site runs MemberPress and the Membership MCP plugin, connected to your membershipmcp.ai account (see https://membershipmcp.ai/docs/connect-your-site/).
- On a Claude Team or Enterprise plan, an Owner adds the Membership MCP connector for your organization first. Members then connect with their own membershipmcp.ai sign-in. If "Add custom connector" is greyed out with "Ask an organization owner", that is this step.
- Claude can change things on your site only as far as the site allows. In WordPress, **MemberPress > MCP > Maximum access** starts at **Read** (look things up only). Choose **Content** to let it draft posts and pages, or **Full** for every change. Changes that matter, like refunds and cancellations, still wait for you under **Waiting for you** before anything happens.

## Install in claude.ai or the Claude desktop app

1. Open **Customize > Plugins** (https://claude.ai/customize/plugins), choose **Add**, then add from GitHub: `caseproof/claude-plugins`. Install **Membership MCP**.
2. Open the plugin's **Connectors** tab and connect **membership-mcp**.
3. Sign in on membershipmcp.ai when it asks, and choose the site Claude may use. Each connection works on one site; to add another site, connect again and pick it.

The plugin brings the connector and a skill that teaches Claude how to work on a membership site safely. To add just the connector instead: **Customize > Connectors > Add custom connector**, with the URL `https://mcp.membershipmcp.ai/`.

Then ask, for example: "How many active members do I have?" or "Which members' payments failed this week?"

## Install in Claude Code

From the Caseproof marketplace, add it, then install the plugin:

```
/plugin marketplace add caseproof/claude-plugins
/plugin install membership-mcp@caseproof
```

On Claude Code 2.1.275 or later, one line does both: `claude plugin install membership-mcp --marketplace caseproof/claude-plugins`. To try it from a checkout instead, run `git clone https://github.com/caseproof/claude-plugins` and then `claude --plugin-dir claude-plugins/membership-mcp`. Then run `/mcp` to sign in.

## ChatGPT

ChatGPT doesn't use this plugin. Add Membership MCP as a custom MCP server instead: open **Plugins**, choose **+**, then **Add custom MCP server**. Paste `https://mcp.membershipmcp.ai/`, tick the risk notice, and sign in on membershipmcp.ai. OpenAI says full MCP support is only on ChatGPT Business and Enterprise/Edu. Pro gets read access only: it can look things up but not make changes. Free and Plus aren’t listed. On a Business workspace, an admin or owner adds it for everyone.

## Data

The plugin itself stores nothing and holds no keys. Claude sends your requests, and the site details they need, to https://mcp.membershipmcp.ai/, which reads from and writes to the site you connected, under your membershipmcp.ai sign-in. See https://membershipmcp.ai/privacy/.
