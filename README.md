# Stateful for Claude

Stateful is property accounting for landlords who keep a separate set of books for each LLC. This plugin connects Claude to one Stateful workspace through the remote MCP server at https://withstateful.com/mcp.

Claude can read each LLC, profit and loss, the balance sheet, cash flow, the rent roll, items still waiting for review, capital accounts, and the K-1 worksheet. The K-1 figure is a worksheet, not a filed return.

A change to the books is a preview. Claude waits until you confirm before it saves a categorization, a journal entry, a posting, a rent payment, or a vendor. Posted history is not deleted. A correction is a new entry. The connector does not send a payment, pay a bill, or move money.

## Install

In Claude on the web, open the install button on https://withstateful.com/connectors/claude. It prefills the connector name Stateful and the server URL. You still review those values and sign in.

In Claude Code, add this marketplace and install the plugin:

```text
/plugin marketplace add sundeep868/stateful-claude-plugin
/plugin install stateful@stateful
```

Sign in with your Stateful account and choose one workspace. One connection is one workspace. Connect again to use another. There is no client secret to paste. Claude registers itself and sends you to Stateful.

## Skills

- `monthly-close` reads the month's profit and loss, balance sheet, cash flow, and items still in review.
- `rent-check` reads the rent roll and outstanding rent, and records a ledger payment only after you confirm.
- `k1-prep` reads capital accounts and the K-1 worksheet for one LLC and tax year.

## Privacy and support

Questions and confirmed writes go to the Stateful workspace you connect. The privacy policy is https://withstateful.com/privacy. The terms are https://withstateful.com/terms. Write support@withstateful.com or use https://withstateful.com/support. Do not send sign-in codes or bank login details.

The Investor plan is $15 a month or $144 a year, with a 30-day trial. Pricing is also on https://withstateful.com/pricing.

![Stateful](./icon.png)
