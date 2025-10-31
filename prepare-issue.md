Pull the information about the issue $1 using `gh`.

Pull the codebase for the repository using `gh repo clone`.

Given the codebase and the issue description, determine if there is enough information to implement the issue.
If there is not enough information, ask for more information by using `gh issue comment`.
If there is enough information, create a plan to implement the issue.

Write the plan to `~/repos/git/shopify-personal-notes/issues/{REPOSITORY}/{ISSUE_NUMBER}/prepare-issue.md`.

Indicate the date+time the file was generated in the file header.

The plan should be in the following format (each section as a bullet point list):

```
# Plan

A plan to implement the issue.
```
