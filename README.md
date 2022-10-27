# 📦 Gitlab golang package template

This is cookiecutter template for generation golang package
project with gitlab ci/cd included.

---

## 🎂 How to use it

`pip install cookiecutter`

`cookiecutter https://github.com/KochankovID/Gitlab-golang-package-template.git`

## ⚙️️ GitLab CI/CD environs

> You need to set these variables in the repository settings.

- **GITLAB_TOKEN** - personal access token for GitLab. Needed for making version
  bumping commits from ci/cd.

## 🧸 Summarise

1. `pip install cookiecutter`
2. `cookiecutter https://github.com/KochankovID/Gitlab-golang-package-template.git`
3. Fill ci/cd variables

## ✨ Features

- [x] GitLab CI/CD
- - [x] Linters (pre-commit)
- - - [x] go-fmt
- - - [x] go-imports
- - - [x] go-cyclo
- - - [x] golangci-lint
- - - [x] go-critic
- - - [x] go-unit-tests
- - - [x] go-build
- - - [x] go-mod-tidy
- - [x] Tests
- - [x] Release (tag version bumping)
- - [x] Documentation (golds)
- [x] Pre-commit hooks
- [x] Readme
- [x] Contributing
- [x] License
- [x] docs.go file for documentation

