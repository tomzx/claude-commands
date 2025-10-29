TODAY=`date +%Y-%m-%d`

# Summarize GitHub Activity
Call `~/repos/git/personal-automation/others/summarize-github-activity tomzx {TODAY} {TODAY} Shopify,shop`.
Write the output to `~/repos/git/shopify-personal-notes/{YEAR}/{MONTH}/{DAY}.github.md`.

# Summarize Slack Activity
Summarize what I discussed on slack on {TODAY}?
Write the response to `~/repos/git/shopify-personal-notes/{YEAR}/{MONTH}/{DAY}.slack.md`.

# Summarize overall activity
Summarize my overall activity on {TODAY}?
Write the response to `~/repos/git/shopify-personal-notes/{YEAR}/{MONTH}/{DAY}.overall.md`.

The summary should be in the following format (each section as a bullet point list):

```
# Accomplishments

A summary of what I accomplished.

# Decisions

A summary of the decisions I made.

# Blockers/Waiting for

A summary of what I was blocked by or waiting for.

# For Your Information

A summary of what I should let others be aware of.

# Need to Discuss

A summary of what I need to discuss with others.

# Next Steps

A summary of what I need to do next.
```

Avoid repeating the same information said differently within the same section.
