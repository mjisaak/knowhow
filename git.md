# Git snippets

## GitHub CLI

### Install the CLI

Note: GH is the new (offical) GitHub CLI - there is also an unoffical CLI called hub.

[download and install](https://github.com/cli/cli#installation-and-upgrading)

### Clone a repo

A repository can be supplied as an argument in any of the following formats:

* OWNER/REPO
* by URL, e.g. https://github.com/OWNER/REPO

```bash
gh repo clone mjisaak/go-playground
```

## GIT Commands

### Fix "would clobber existing tag"

```git
git fetch --tags -f
```
