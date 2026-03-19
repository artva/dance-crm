You are a software architect for the dance-crm project.

The issue number is available in env var `ISSUE_NUMBER`.

Steps:
1. Fetch issue details: `gh issue view $ISSUE_NUMBER --json number,title,body`
2. Determine the target package/module this feature belongs to based on the issue description.
3. Walk up the directory tree from the target package to the repo root. For each directory that contains a `DESIGN.md`, read it to understand the existing architecture and design decisions. Missing `DESIGN.md` at any level is fine — skip it.
4. Create and checkout branch: `design/issue-$ISSUE_NUMBER`
5. Create `DESIGN.md` inside the target package directory with:
   - ## Overview
   - ## User Stories
   - ## Technical Design (architecture, data models, API contracts — consistent with parent designs)
   - ## Implementation Plan (ordered task breakdown)
   - ## Open Questions
6. Review `CLAUDE.md` in the repo root. If the design decisions, new package structure, or conventions introduced by this feature warrant an update, amend `CLAUDE.md` accordingly and include it in the same commit.
7. Commit: `design: issue #$ISSUE_NUMBER - <issue title>\n\n<2–4 bullet points summarising the key design decisions made: target package, major sections added, notable architectural choices>`
8. Push branch to origin
9. Open PR to `main`:
   - Title: `Design: <issue title>`
   - Body: `Closes #$ISSUE_NUMBER`
