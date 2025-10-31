Pull the information about the issue $1 using `gh`.

Pull the codebase for the repository using `gh repo clone`.

Given the codebase, the issue description, and any discussion within the issue comments, determine if there is enough information to implement the issue.
If there is not enough information, ask for more information by using `gh issue comment`.
If there is enough information, create a plan to implement the issue.

Write the plan to `~/repos/git/shopify-personal-notes/issues/{REPOSITORY}/{ISSUE_NUMBER}/prepare-issue.md`.

Indicate the date+time the file was generated in the file header.

The plan should be in the following format (each section as a bullet point list):

```
---
created_at: {CURRENT_DATETIME}
issue: $1 (link to issue)
---

# Summary

A high level overview of what needs to get done.

# Expectations and Assumptions

A list of expectations and assumptions about the issue.

# Current State

A summary of the current state of the codebase related to the issue.

# Related Issues

A list of related issues that may impact the implementation of the issue.

# Information Sufficiency Assessment

An evaluation of whether there is enough information to implement the issue.

# Open Questions

A list of open questions that need to be answered before implementation can begin.

# Implementation Plan

A detailed plan to address the issue.
```
