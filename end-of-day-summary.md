BASE_DIR=~/repos/git/shopify-personal-notes
TODAY=`date +%Y-%m-%d`

# Summarize GitHub Activity
Call `~/repos/git/personal-automation/others/summarize-github-activity tomzx {TODAY} {TODAY} Shopify,shop`.
Write the output to `{BASE_DIR}/{YEAR}/{MONTH}/{DAY}.github.md`.

# Summarize Slack Activity
Summarize what I discussed on slack on {TODAY}?
Write the response to `{BASE_DIR}/{YEAR}/{MONTH}/{DAY}.slack.md`.

The slack summary should be in the following format (each section as a bullet point list):

```
# Summary

A summary of the key conversations.

# Key Conversations

A list of the key conversations (including a link to the conversation).

# Action Items Generated

A list of the action items generated.
```

# Summarize overall activity
Summarize my overall activity on {TODAY}?
Write the response to `{BASE_DIR}/{YEAR}/{MONTH}/{DAY}.overall.md`.

The overall summary should be in the following format (each section as a bullet point list):

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

# Timeline
Using the information collected, create a timeline of the day.

Write the response to `{BASE_DIR}/{YEAR}/{MONTH}/{DAY}.timeline.md`.

The timeline should be in the following format (each section as a bullet point list):

```
# Timeline

* Timestamp - Activity
```
