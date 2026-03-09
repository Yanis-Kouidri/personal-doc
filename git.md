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

Clone a remote project (here an example with [Win11Debloat](https://github.com/Raphire/Win11Debloat.git))

```bash
git clone https://github.com/Raphire/Win11Debloat.git
```

## ACP cycle

ACP: Add, Commit, Push

To see what is modified, staged and your branch

### Add

```bash
git add myfile.py
```

### Commit

```bash
git commit -m "feat: add /user api endpoint"
```

### Push

```bash
git push -u origin main
```

Will push the local main branch over the remote main branch.

`-u` option allow saving the link between remote branch main and the local branch main. Thus, you will be able to only write `git push`.

## Branch

To see both remote and local branch

```bash
git branch -a
```

To see link between local and remote branch

```bash
git branch -vv
```

### Switch

To switch branch to `dev`

```bash
git switch dev
```

## Tags

While branch are an active line of development, tag are static pointer to a specific moment in your repo history.

Tags are immutable while branch are mutable.

When you are satisfied of your app, and you went to set a version run:

```bash
git tag -a v1.0.0 -m "First stable version with auth"
```

Then you have to push the tag.

```bash
git push origin v1.0.0
```

### Good workflow example

```bash
git add .
```

```bash
git commit -m "feat: add user logout"
```

```bash
git tag -a v1.0.0 -m "First version with auth"
```

```bash
git puhs origin main --follow-tags
```

This last command will push branch and tags.
