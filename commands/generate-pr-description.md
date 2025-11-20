Generate a PR description using the follow changes.

!`git diff $(gt parent)..HEAD` (use `gt`, which is the graphite CLI)

The PR description should be in the following format:

```
# What

A summary of the changes in this PR.
Use the present tense.

# Why

A summary of the reason for the changes in this PR.

# How to test

A summary of how to test the changes in this PR.

# References

To be filled by the user.
```

The returned response should be returned within a markdown code block.
Each sentence should be its own line.
