---
name: k1-prep
description: Prepare partner capital and the K-1 worksheet for one Stateful LLC. Use when the user asks for capital accounts, partner allocations, or a K-1 worksheet for a tax year.
---

# K-1 prep

Use the connected Stateful workspace only. Call the Stateful MCP tools. The K-1 figure is a worksheet. It is not a filed return. Do not file a tax return and do not tell the user the worksheet was filed.

## Read the LLC

1. Call `list_entities` and use an LLC the tool returns. If the user names an LLC that is not in the list, say it is not in this workspace.
2. Call `get_capital_accounts` for that LLC.
3. Call `get_k1_summary` for that LLC and the tax year they named.

## Report

Lead with the LLC, the tax year, each partner's capital, and the worksheet lines `get_k1_summary` returned. Say this is a worksheet for the books in Stateful, not a return filed with a tax authority.

Do not distribute cash, delete a partner, or change capital from this skill. No tool here moves money. If a figure is missing, say the tool did not return it.
