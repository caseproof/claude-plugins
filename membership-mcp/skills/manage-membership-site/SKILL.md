---
name: manage-membership-site
description: Use when someone asks about their MemberPress membership site (members, memberships, subscriptions, transactions, coupons, access rules, courses, reports, posts and pages, reminders, gateways) or asks Claude to change one of them, or to move members from MemberMouse. Works through the Membership MCP connector.
---

# Manage a membership site

## One connection, one site

Each Membership MCP connection is bound to the one site the person picked when they signed in on membershipmcp.ai. Everything you do happens on that site. To work on another site, they add the connector again and pick that site. If they ask about a site and you can't tell which one this connection is, ask them.

Someone who isn't the site's owner may connect as a team member. They sign in as themselves, and they can only do what their own WordPress account is allowed to do. The owner can revoke that access.

## What you can see depends on the site's access level

The site owner sets **Maximum access** in WordPress (MemberPress > MCP):

- **Read** (the default): you can look things up but not change anything, and no tools that make changes are offered.
- **Content**: reads, plus drafting and editing posts and pages.
- **Full**: every change the tools support.

Some tools also need an Administrator's WordPress account, and some only appear when an add-on is active (Courses, Corporate Accounts, Downloads, Gifting, MemberMouse, WishList Member, BuddyBoss). If what they ask for has no tool, say which access level or add-on it needs instead of trying a workaround.

## Working on their site

1. Read before you write. Look up the member, membership, rule or subscription they mean, and show what you found.
2. A question is not a request. "Why did this member churn?" is a question; don't cancel, refund, delete or email anyone unless they ask for that change.
3. Before any change, say exactly what will change and ask them to confirm.
4. Many changes take two steps on their own: the first call returns a preview and a `confirmation_token`, and only the second call makes the change. Send the same arguments again, plus the token and any field the preview tells you to send back (an update's last-modified time, or a pricing page's memberships fingerprint). Show the preview, get their yes, then send the second call. Never invent or reuse a token.
5. Some tools preview unless `execute` is true. Run the preview first, and set `execute: true` only after they confirm.
6. Some changes wait for the owner. Refunds, cancellations, deletions, imports, coupon, gateway and settings changes, publishing a membership and the MemberMouse move go to **MemberPress > MCP > Waiting for you** in WordPress, and nothing happens until the owner confirms there. Unconfirmed requests expire after 7 days. The owner can let refunds, cancellations and imports skip that wait. When a change is waiting, say so in one sentence, don't claim it's done, and don't ask them to confirm again.
7. New memberships, rules, pricing pages, posts, pages and menus are saved as drafts. Publishing is a separate step they choose.
8. Watch for anything that emails members: changing a member's email (WordPress emails the old address), the `send_welcome_email` option on new members, subscriptions and imports, and reminders, which start sending as soon as they're created. Say so before you do it.
9. If a tool says the outcome is unknown or a write is in progress, don't retry. Tell them, and check the result with a read first.
10. After a change, read it back and tell them it's done, or waiting for the owner, in one sentence.

## Moving from MemberMouse or WishList Member

Run the dry run first: it changes nothing and shows what would move. The MemberMouse move then goes to Waiting for you. It charges no one, calls no gateway and sends no email. Memberships and rules arrive as drafts, and MemberMouse keeps billing until the owner switches over. For WishList Member, only the dry run is offered.

## Membership MCP's own tools

Depending on the account, the connector adds a few tools of its own beside the site's: saved skills the owner can run, the site's history and the owner's notes, a way to send feedback when no tool fits, and a reset for the day's tool-call allowance. Use them the same way, and only when they're offered.

## Sign-in

If the connector asks them to sign in, they sign in on membershipmcp.ai. Never ask for a password, an API key or a token in chat.
