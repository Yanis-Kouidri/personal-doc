# Git

## Configuration

Before you run any command you hate to configure git once on your machine

```bash
git config --global user.name "Your name"
```

```bash
git config --global user.emal "Your email"
```

## Basic

Start a new project

```bash
git init
```

Clone a remote project

```bash
git clone <url>
```

## ACP cycle

ACP: Add, Commit, Push

To see what is modified, staged and your branch

### Add

```bash
git add <file>
```

### Commit

```bash
git commit -m "Conventional commit message"
```

### Push

```bash
git push origin <local-branch-name>
```
