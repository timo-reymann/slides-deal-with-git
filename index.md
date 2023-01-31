---
title: Deal with (g)it
description: Top 5 tips to make the best out of (g)it
author: Timo Reymann
paginate: true
theme: default
---

# Deal with (g)it
Top 5 tips to make the best out of (g)it

---

# #1 Sign your commits

Make visible you are the real owner of a commit.

---

# Are these commit from Linus?

- this is a real github repo
- these are real commits

[GitHub: Amog-OS/AmogOS](https://github.com/Amog-OS/AmogOS/commits?author=torvalds)

> Fellow linux redditors may now this already

![bg left:45% height:100%](./images/amog-us-commits.png)


---

# Anyone can be Linus!

- git config is not verifying anything

So you can set up your local config ...

```shell
git config --global user.name "torvalds"
git config --global user.email "torvalds@osdl.org"
```

... and be Linus:

```shell
touch proof
git stage proof
git commit -m "I am Linus!"
```

... at least thats what its going to look like

---

# Verified commits to the rescue!

![bg left:45% height:100%](./images/verified-commits.png)

- Signed with [GPG](https://gnupg.org/)
- Visible on all git hosting platforms
- Checkable with the git cli


> GPG stands for GNU Priavcy Guard and is a free tool to sign and encrypt
> things

---

# Setting it up is easy - 3 steps to victory

1. Create [GPG](https://gnupg.org/) key ([Tutorial](https://docs.github.com/en/authentication/managing-commit-signature-verification/generating-a-new-gpg-key))
2. Add the key to your user profile on the git hosting platform (e.g.
[GitHub](https://docs.github.com/en/authentication/managing-commit-signature-verification/adding-a-gpg-key-to-your-github-account))
3. Configure your local git installation:
  `git config --global user.signingkey <key-id>`

---

# #2 Keep your history clean

> accountants don't use erasers or they end up in jail

But luckily we are not accountants!

---

<!-- footer: Image for git squash: atlassian.com/git/tutorials/rewriting-history -->

# Squash your feature branches

- powerful feature allowing you to combine multiple commits
- supported by git hosters such as GitHub/GitLab on PRs

![bg left:50% height:300px](./images/git-squash.svg)
![bg left:50% height:250px vertical](https://blog.timo-reymann.de/content/images/2022/08/image-14.png)

---
<!-- footer: Image for git rebase: atlassian.com/git/tutorials/rewriting-history/git-rebase -->
# Rebase your changes

- local repo is not up to date
- main branch has evolved faster than feature branch
- smaller changes most of the time dont need to be merged

![bg left:50% height:50%](./images/git-rebase.svg)

---
<!-- footer: "" -->
# #3 Simplify your daily life

Git and your shell has more to offer than just builtin commands!

---

# Add helper tools

- Any command thats prefixed with `git-` can be a git command
- [git-semver-tag](https://github.com/timo-reymann/git-semver-tag) becomes `git semver-tag`

---

# Create alias in your git config

- can be a entire shell command
- or just a alias

e.g. here are mine:
```ini
[alias]
p = pull
squash-all = "!f(){ git reset $(git commit-tree HEAD^{tree} -m \"${1:-A new start}\");};f"
sync = "!f() { git pull --rebase && git push; };f"
```

---

# Alias entire git commands

- for the extreme lazy
- add to your shellrc

```shell
# use gpush
alias gpush = "git push"

# use commit "my message"
alias commit = "git stage . && git commit -m"
```

---

# #4 Use branches and tags wisely

> TBD

---

# #5 Rely on conventions

> TBD

---


![bg width:70%](./images/in_case_of_fire.png)
