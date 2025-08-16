# Contributing Guide

Thanks for helping improve this Task4 repo! This project demonstrates a tidy Git workflow.

## 1. Ground Rules
- Keep `main` stable; merge to `main` only via PR from `dev`.
- Every change starts from **`dev`** on a **feature branch**.
- Write clear, small commits using **Conventional Commits**.
- All merges use **Pull Requests** with at least one review (self-review is fine for solo work).

## 2. Branching

- Base branch: `dev`
- Create features as: `feature/<short-description>`
  - Examples: `feature/add-hello`, `feature/update-readme`

```bash
git checkout dev
git pull
git checkout -b feature/add-hello
# ... make changes ...
git add .
git commit -m "feat(app): add hello script"
git push -u origin feature/add-hello
```

## 3. Pull Requests

1. Open PR: **base = `dev`**, **compare = `feature/*`**.  
2. Fill the PR description:
   - What changed?
   - Why?
   - How to test?
3. Address comments (if any) → **Merge**.
4. After several features are merged into `dev`, open PR **`dev` → `main`**.

### PR Checklist
- [ ] Branch name is `feature/<something-meaningful>`
- [ ] Commits follow Conventional Commits
- [ ] Build/tests (if any) pass
- [ ] README/docs updated when needed

## 4. Commit Messages (Conventional)

```
feat(<scope>): <what>
fix(<scope>): <what>
docs(<scope>): <what>
chore(<scope>): <what>
refactor(<scope>): <what>
```

Good: `feat(app): add hello script`

## 5. Releases & Tags

- After merging `dev` → `main`, create an **annotated tag**:

```bash
git checkout main
git pull
git tag -a v1.0.0 -m "Task4 first release"
git push origin v1.0.0
```

- Add release notes on GitHub if desired (attach screenshots under `docs/screenshots/`).

## 6. Keeping Your Feature Branch Up to Date

```bash
git checkout dev
git pull
git checkout feature/add-hello
git rebase dev   # or: git merge dev
# resolve conflicts if any, then:
git push --force-with-lease
```

## 7. Ignoring Files

Common ignores live in `.gitignore`:
- OS and editor junk
- `node_modules/`, `__pycache__/`, etc.
- Terraform state: `.terraform/`, `*.tfstate*`, `.terraform.lock.hcl`

## 8. Code of Conduct

Be kind and professional. Assume good intent. Keep discussions technical and respectful.

---

Happy collaborating!
