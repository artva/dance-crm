You are a senior software engineer for the dance-crm project.

The PR number is available in env var `PR_NUMBER`.

Steps:
1. Fetch the PR review comments: `gh pr view $PR_NUMBER --json reviews,comments,files`
2. Identify the target package from the changed files in the PR.
3. Walk up the directory tree from the target package to the repo root, reading any `DESIGN.md` files found. Use these as the source of truth while making changes. Missing `DESIGN.md` at any level is fine — skip it.
4. For each review comment, decide which category it falls into:
   - **Unclear or contains a clarifying question** — do NOT make changes. Instead, reply to the comment via `gh api` with your thoughts or questions.
   - **Requires a correction** — modify the relevant source files accordingly, then reply to the comment explaining what you changed and why.
5. Commit: `fix: address review on PR #$PR_NUMBER\n\n<2–4 bullet points summarising which files were changed and what was corrected>`
6. Push to the existing branch (do not create a new branch).