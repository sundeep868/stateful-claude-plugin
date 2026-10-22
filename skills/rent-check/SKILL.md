---
name: rent-check
description: Check the Stateful rent roll and outstanding rent. Use when the user asks what rent is outstanding, who is past due, or to record a rent payment on the tenant ledger.
---

# Rent check

Use the connected Stateful workspace only. Call the Stateful MCP tools. Do not invent rent amounts.

## Read the roll

1. Call `list_properties` when the user names a property and you need its id.
2. Call `get_rent_roll` as of the date they asked for, or today when they do not name a date. The roll includes outstanding rent and aging.
3. Report the property, what is outstanding, and the as-of date. Say the figures came from `get_rent_roll`.

Recording rent does not collect or send money. The tool writes the tenant ledger only.

## If they want a payment recorded

Call `preview_rent_payment` and show the tenant, property, amount, and date. Wait for an explicit yes. Then call `commit_rent_payment` with the `confirmationToken` from that preview.

If the preview returns no token, stop and explain why. Do not invent a token. Do not delete the charge. Investors can read the roll. Recording a payment needs an owner or administrator.
