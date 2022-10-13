# 🎩 Contributing

---

## Setting up for development

### 🦫 Go module

```bash
go mod download
```

### 🪡 Git hooks

```bash
curl --fail -o .git/hooks/commit-msg https://raw.githubusercontent.com/hazcod/semantic-commit-hook/master/commit-msg \
  && chmod 500 .git/hooks/commit-msg
```

## 🏃 Run

### ✅ Run tests

```bash
go test ./...
```

### 🔱 Run pre-commit hooks

```bash
go install golang.org/x/tools/cmd/goimports@latest
go install github.com/fzipp/gocyclo/cmd/gocyclo@latest
go install -v github.com/go-critic/go-critic/cmd/gocritic@latest
pre-commit install
pre-commit run -a
```

### 🧪 Generate table test

```bash
gotests -all -w <file_name>
```