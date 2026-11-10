---
name: github-publishing
description: Publish a project and its sibling repositories as public GitHub repositories, with the siblings linked from the root as submodules.
---

# Publish project repositories to GitHub

Use this skill when asked to publish this root project and its sibling projects to GitHub.

## Repository set and names

- Treat the current project root as the parent repository and the named sibling projects as independent repositories.
- For the example project family, use `thuta` for the root and `thuta-api`, `thuta-app`, and `thuta-mobile` for the `api/`, `app/`, and `mobile/` siblings. If the project prefix or sibling list differs, use the names the user gives and confirm any unresolved mapping before publishing.
- Publish every repository as **public**. Resolve the GitHub owner from the connected GitHub account or `gh auth status`; do not infer it from local author email.

## Workflow

1. Inspect each project directory, Git status, current branch, remotes, ignored files, and existing Git history. Preserve unrelated local changes. Include the requested project contents in the publication commits, but never add credentials, `.env` files, tokens, private keys, dependency directories, build output, or unrelated sibling directories. Review ignore rules and scan candidate tracked files for obvious secrets before committing.
2. Check for a connected GitHub repository-management integration and use it when it supports the required repository and Git operations. Otherwise use `gh` and Git. Verify authentication and the owner before creating repositories; if authentication is unavailable, stop external publishing and report the exact `gh auth login -h github.com` recovery step.
3. For each sibling, preserve its existing repository and history. Create a Git repository only if it does not already exist. Commit the intended contents when needed, create the matching public GitHub repository only when absent, set an existing repository public when required by the request, add or correct its `origin`, and push its current branch. Do not overwrite an existing remote with unrelated history; inspect and reconcile it first.
4. Create or use a Git repository at the project root. Add `.gitmodules` entries for each published sibling using `https://github.com/<owner>/<sibling-repo>.git`, and record each sibling directory as a Git submodule at its matching commit. When converting already-present nested repositories, preserve their work and history; do not delete or replace a directory until its contents and Git metadata are safely retained. Commit the root contents, submodule links, and `.gitmodules` after reviewing the staged diff.
5. Create the root repository as public, add or correct its `origin`, and push the root branch. Confirm each remote URL, public visibility, pushed branch, and submodule URL/commit. Report repository links and any remaining blocker.

## Boundaries

- A direct request to publish the named projects publicly authorizes creating those repositories, pushing their requested contents, and making those repositories public. Do not publish other directories or repositories discovered nearby.
- Stop before a destructive overwrite, history replacement, deletion, or publication of a detected secret or clearly unrelated/private content. Explain the specific blocker and keep safe local preparation intact.
- Never expose credentials in command output or commit content. Avoid repeating authentication attempts after a rejected or invalid credential; use the login recovery step instead.
