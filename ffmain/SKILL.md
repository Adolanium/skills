---
name: ffmain
description: Fast-forward main from upstream, then push origin.
license: MIT
---

# Ffmain

Fast-forward this repo's main branch from `upstream`, then push it to `origin`. Fast-forward only.

Do not merge. Do not rebase. Do not stash. Do not add extra git flags.

## When to Use

- User says "/ffmain", "fast-forward main", "sync main from upstream", "update my fork's main."
- User wants local main to match upstream, then origin to match that.

Don't use for:

- Saving uncommitted work. Commit first, then come back.
- Merging a feature branch or a pull request.
- Rebasing local commits onto main.
- Force-updating a main that has diverged.

## Need first

- You are in a git repo.
- A remote named `origin` exists.
- Tracked files are clean. Uncommitted edits on tracked files mean stop.
- Network for fetch, push, and looking up origin's parent if `upstream` is missing.

## Steps

On a failed git command, print the output and stop. Do not retry with other flags.

### 1. Check the repo

Run `git rev-parse --show-toplevel`, `git remote`, and `git status -sb`.

Stop if this is not a git repo, or if `origin` is missing.

Done when `origin` is in the list.

### 2. Add upstream if missing

If `upstream` is already in `git remote`, skip this step.

Find origin's parent on the host. Do not ask the user to paste a URL.

- Read `git remote get-url origin`.
- On GitHub, run `gh repo view --json isFork,parent`. If that fails, open `https://api.github.com/repos/<owner>/<repo>` and read `parent`.
- On another host, use that host's fork-parent field.
- Do not guess from the repo name.

Use a clone URL in the same style as origin (ssh if origin is ssh). Then `git remote add upstream <url>`.

Stop if origin is not a fork, or the host gives no parent. Say what you opened.

Do not add a remote that matches origin's URL.

Done when `git remote` lists `upstream`.

### 3. Name the main branch

If `git show-ref --verify --quiet refs/remotes/upstream/main` works, the branch is `main`. If not, take the name after `upstream/` from `git rev-parse --abbrev-ref upstream/HEAD`.

Stop if you still do not have a name.

### 4. Confirm the tree is clean

Stop unless `git diff --quiet` and `git diff --staged --quiet` both work. Print `git status` if you stop.

### 5. Fetch

Record the current branch with `git branch --show-current`. Run `git fetch upstream <main>`.

Done when `upstream/<main>` is current.

### 6. Checkout and fast-forward

If you are not on `<main>`, check it out.

Run `git merge --ff-only upstream/<main>`.

Stop if that fails. Local main has diverged.

Done when local `<main>` points at `upstream/<main>`.

### 7. Push

Run `git push origin <main>`.

**Hard rule.** That is the whole push. If it fails, stop.

Done when `origin/<main>` is that same SHA.

### 8. Put them back

If step 6 switched branches, check out the branch you recorded.

## Watch for

- Asking the user to add `upstream` when you can look up the parent.
- Guessing the parent from the folder name.
- Setting `upstream` to origin's URL.
- Pushing while the tree is dirty.
- Adding `--force` or `--force-with-lease` after a rejected push.
- `git pull`, which can make a merge commit.
- Stashing so the tree looks clean.
- Pushing a branch that is not main.

## You're done when

- Local main is a fast-forward of `upstream`.
- `origin` has that SHA.
- They are on the branch they started on.
- Or you stopped, printed git's output, and did not work around it.
