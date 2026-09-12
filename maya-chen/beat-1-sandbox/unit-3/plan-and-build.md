MARKER: beat-1-sandbox/unit-3/plan-and-build.md (maya)

# Unit 3 — Plan and Build

**GitHub username**

sarcb

**Plan comment**

https://github.com/codepath/ai301-fetch-smoketest/issues/1

**Branch**

fix/1-probe-the-pr-fetcher

**Run history**

11/20, then 15/20, then 18/20

**Package analysis**

pkg-03: my rubric said accept, the gold label said reject, because my scope
check only counted files instead of reading what the change touched.

**Check rationale**

My check reads "every changed file is named in the plan". I tightened it from
an earlier version that only required a file count to match.

**Trade-offs**

It will miss a change that renames a file the plan named, since the new name
never appears in the plan.
