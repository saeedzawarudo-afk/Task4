# Task 4 — Version-Controlled DevOps Project

A small repo that demonstrates a clean **Git workflow** with:
- branches: `main`, `dev`, and `feature/*`
- pull requests (PRs) for all merges
- semantic commit messages
- tags for releases
- docs in Markdown

> This repository is used only to showcase process, not a large app.  
> A tiny `app/run.sh` script is included for commit/PR examples.

---

## 📦 Repository Structure

```
.
├─ app/
│  └─ run.sh               # tiny demo script
├─ docs/
│  ├─ TASK4.md             # task log / notes
│  ├─ Q&A.md               # quick interview answers
│  └─ screenshots/         # put screenshots here
│     ├─ 01-new-repo.png
│     ├─ 02-branches.png
│     ├─ 03-feature-pr.png
│     ├─ 04-merge-feature-to-dev.png
│     ├─ 05-merge-dev-to-main.png
│     ├─ 06-tag-v1.0.0.png
│     └─ 07-readme.png
├─ .gitignore
├─ README.md
└─ CONTRIBUTING.md
```

---

## ✅ Deliverables Checklist

- [ ] New repo created for Task 4  
- [ ] Branches: `main`, `dev`, and one `feature/*`  
- [ ] PR: `feature/*` → `dev`  
- [ ] PR: `dev` → `main`  
- [ ] Annotated tag (e.g., `v1.0.0`)  
- [ ] `.gitignore` present  
- [ ] Docs in `docs/` and this `README.md`  

---

## 🧭 Branching Model

- **`main`** – always stable, release-ready.
- **`dev`** – integration branch for completed features.
- **`feature/<short-description>`** – work happens here, branched off `dev`.

---

## 🚀 Quick Start (Linux)

```bash
# 0) Clone
git clone https://github.com/<your-username>/Task4.git
cd Task4

# 1) Create dev branch
git checkout -b dev
git push -u origin dev

# 2) Create a feature branch from dev
git checkout -b feature/add-hello
echo 'echo "hello from Task4!"' > app/run.sh
chmod +x app/run.sh
git add app/run.sh
git commit -m "feat(app): add hello script"
git push -u origin feature/add-hello

# 3) Open GitHub → PR: feature/add-hello -> dev  (merge)
# 4) Open GitHub → PR: dev -> main               (merge)

# 5) Tag a release
git checkout main
git pull
git tag -a v1.0.0 -m "Task4 first release"
git push origin v1.0.0
```

---

## 📝 Commit Message Style

We use **Conventional Commits**:

```
feat: add new capability
fix: correct a bug
docs: update readme
chore: tooling or housekeeping
refactor: code change without behavior change
```

Include scope when useful, e.g. `feat(app): add hello script`.

---

## 🧪 How to Run the Demo Script

```bash
./app/run.sh
```

*(This file exists only to have something meaningful to commit and review.)*

---

## 🖼️ Screenshots to Include (place under `docs/screenshots/`)

| File name                         | What to capture                                              |
|----------------------------------|--------------------------------------------------------------|
| `01-new-repo.png`                | New GitHub repo page                                         |
| `02-branches.png`                | Branch list showing `main` and `dev`                         |
| `03-feature-pr.png`              | PR from `feature/*` to `dev`                                 |
| `04-merge-feature-to-dev.png`    | Merge confirmation or PR conversation                        |
| `05-merge-dev-to-main.png`       | PR from `dev` to `main`                                      |
| `06-tag-v1.0.0.png`              | Releases/tags page showing `v1.0.0`                          |
| `07-readme.png`                  | Final README rendered on GitHub                              |

---

## 🔧 Troubleshooting

- **PR button disabled**: ensure your feature branch is **pushed** and **compares to `dev`**.  
- **Fast-forward merges** not shown: allow merge commits in repo settings or rebase your branch.  
- **Tag doesn’t appear**: confirm `git push origin v1.0.0` ran without errors.

---

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for branch/PR rules and review checklist.
