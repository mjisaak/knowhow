# Git snippets

## GitHub CLI

### Install the CLI

Note: GH is the new (offical) GitHub CLI - there is also an unoffical CLI called hub.

[download and install](https://github.com/cli/cli#installation-and-upgrading)

### Clone a repo

A repository can be supplied as an argument in any of the following formats:

* OWNER/REPO
* by URL, e.g. `https://github.com/OWNER/REPO`

```bash
gh repo clone mjisaak/go-playground
```

## GIT Commands

### Git Tag

```git
git tag -a v0.0.2 -m "This release contains the first release of the chrome MVP Docs & Learn Champion extension."
git push origin --tags
```

### Fix "would clobber existing tag"

```git
git fetch --tags -f
```

### Throw away / Discard local commits

```git
git reset --hard origin/<branch_name>
```

### un-commit last un-pushed git commit without losing changes

In case you have not pushed the commit publicly yet:

```git
reset HEAD~1 --soft
```
