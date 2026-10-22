---
name: monthly-close
description: Close one month of Stateful books for an LLC. Use when the user asks for a monthly close, month-end profit and loss, a balance sheet as of month end, cash flow, or uncoded transactions still in review.
---

# Monthly close

Use the connected Stateful workspace only. One connection is one workspace. Call the Stateful MCP tools. Do not invent balances.

## Read the month

1. Call `list_entities` and use an LLC the tool returns. If the user names an LLC that is not in the list, say it is not in this workspace.
2. Call `get_profit_and_loss` for that LLC and the month they named. Name the legal owner when they want one set of books.
3. Call `get_balance_sheet` as of the last day of that month. A balance sheet is cumulative through that date. Do not treat a start date as the beginning of the balance sheet.
4. Call `get_cash_flow` for that LLC and the same month. A property filter does not allocate entity cash.
5. Call `list_review_items` and `search_transactions` for rows that still need coding. Posted and ignored rows are not a close exception.

## Report

Lead with the LLC name, the month, profit and loss, the balance sheet date, and how many items still need review. Say which figures came from which tool.

## If they want a coding saved

Call `preview_categorize_transaction` and show the proposed coding. Wait for an explicit yes. Then call `commit_categorize_transaction` with the `confirmationToken` from that preview. Saving a category does not post it.

A journal, a posting approval, or a vendor follows the same rule: `preview_journal_entry`, `preview_approve_posting`, or `preview_add_vendor`, then the matching commit tool only after the user confirms, using that preview's `confirmationToken`. If the preview returns no token, stop and explain why. Do not invent a token.

Posted history is not deleted. A correction is a new entry. This connector does not send a payment, pay a bill, or move money.
