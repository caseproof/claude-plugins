# Membership MCP for Claude

Run your MemberPress membership site from Claude. Ask about members, memberships, subscriptions, transactions, coupons and access rules, or ask Claude to make a change, and it works on your site through Membership MCP.

## Before you start

- Your WordPress site runs MemberPress and the Membership MCP plugin, connected to your membershipmcp.ai account (see https://membershipmcp.ai/docs/connect-your-site/).
- On a Claude Team or Enterprise plan, an Owner adds the Membership MCP connector for your organization first. Members then connect with their own membershipmcp.ai sign-in. If "Add custom connector" is greyed out with "Ask an organization owner", that is this step.

## Install in claude.ai or the Claude desktop app

1. Download `membership-mcp.zip`. Don't unzip it.
2. Open **Customize > Plugins > Add > Upload plugin** (https://claude.ai/customize/plugins) and choose the zip.
3. Open the plugin's **Connectors** tab and connect **membership-mcp**.
4. Sign in on membershipmcp.ai when it asks, and choose the site Claude may use.

Then ask, for example: "List my sites" or "How many active members do I have?"

## Install in Claude Code

From the Caseproof marketplace, add it, then install the plugin:

```
/plugin marketplace add caseproof/claude-plugins
/plugin install membership-mcp@caseproof
```

On Claude Code 2.1.275 or later, one line does both: `claude plugin install membership-mcp --marketplace caseproof/claude-plugins`. Or run `claude --plugin-dir ./membership-mcp.zip`. Then run `/mcp` to sign in.

## ChatGPT

ChatGPT doesn't take this zip. Add Membership MCP as a custom MCP server instead: open **Plugins**, choose **+**, then **Add custom MCP server**. Paste `https://mcp.membershipmcp.ai/`, tick the risk notice, and sign in on membershipmcp.ai. Works with ChatGPT Plus, Pro, Business and Enterprise; on a Business workspace, only admins and owners can add one.

## Data

The plugin itself stores nothing and holds no keys. Claude sends your requests, and the site details they need, to https://mcp.membershipmcp.ai/, which reads from and writes to the sites you connected, under your membershipmcp.ai sign-in. See https://membershipmcp.ai/privacy/.
