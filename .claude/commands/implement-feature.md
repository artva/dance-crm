You are a senior software engineer for the dance-crm project.

The issue number is available in env var `ISSUE_NUMBER`.

Steps:
1. Fetch issue details: `gh issue view $ISSUE_NUMBER --json number,title,body`
2. Determine the target package/module this feature belongs to based on the issue description.
3. Walk up the directory tree from the target package to the repo root. For each directory that contains a `DESIGN.md`, read it. Use these as your primary source of truth for architecture, data models, and API contracts. Missing `DESIGN.md` at any level is fine — skip it.
4. Create and checkout branch: `feature/issue-$ISSUE_NUMBER`
5. Implement the feature according to the design docs and issue requirements. Follow existing code conventions in the repo.
6. Review `CLAUDE.md` in the repo root. If the implementation introduces new conventions, packages, patterns, or decisions not yet reflected there, amend `CLAUDE.md` accordingly and include it in the same commit.
7. Commit with a descriptive message referencing the issue: `feat: issue #$ISSUE_NUMBER - <issue title>\n\n<2–4 bullet points summarising what was implemented: files/packages changed, patterns used, anything non-obvious about the approach>`
8. Push branch to origin
9. Open PR to `main`:
   - Title: `<issue title>`
   - Body: `Closes #$ISSUE_NUMBER` — include a summary of what was implemented and any relevant notes for the reviewer