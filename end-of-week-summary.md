TODAY=`date +%Y-%m-%d`

# Summarize Slack Activity
Summarize what I discussed on slack based on the notes (`.slack.md` files) taken during the week ending {TODAY} in the directory `~/repos/git/shopify-personal-notes`.
Write the response to `~/repos/git/shopify-personal-notes/{YEAR}/weekly/{WEEK}.slack.md`.

# Summarize #help-ml-infrastructure Slack Channel Activity
Summarize the activity in the #help-ml-infrastructure Slack channel during the week ending {TODAY}. (use slack MCP server to get the messages)
Write the response to `~/repos/git/shopify-personal-notes/{YEAR}/weekly/{WEEK}.slack.help-ml-infrastructure.md`.

Use the following format:
```
# Issue (one entry per issue)

## Link

A link to the slack message.

## Participants
A list of the participants in the conversations.

## Issue
A summary of the issue discussed.

## Key events
A summary of the key events discussed.

## Outcome
A summary of the outcome of the conversations.

# Overall

## Response Quality

A summary of the response quality of the conversations.

## Common Issues

A summary of the common issues identified in the conversations.

## Action Items

A summary of the action items generated from the conversations.
```

# Summarize Colleagues Slack Channel Activity
Summarize the activity of the following slack users during the week ending {TODAY}: !`scripts/get-env COLLEAGUES`. (use slack MCP server to get the messages)
Write the response to `~/repos/git/shopify-personal-notes/{YEAR}/weekly/{WEEK}.slack.colleagues.md`.

# Summarize Action Items
Summarize the action items I need to follow up on based on the notes taken during the week ending {TODAY} in the directory `~/repos/git/shopify-personal-notes`.
Write the response to `~/repos/git/shopify-personal-notes/{YEAR}/weekly/{WEEK}.action-items.md`.
