---
name: issue-fix
description: Required instructions for filing an issue
---

Read over the issue, and create a multica issue for it summarizing the intent of the change.

Then add the following checklist to the issue:

1. Determine if the issue is worth accepting. If it is requesting features or design changes, then work out the best design.
2. In the first agent run, add the bare minimum tests reproduce the issue, that follow repo conventions.
    - Tests should be in the correct file - avoid one-off test files that do not align with conventions.
3. In a second run, add the implementation.
4. In a third pass, review the PR. If there are findings then fix them. Rinse and repeat until no findings.
5. Get Architect to do a simplification pass
