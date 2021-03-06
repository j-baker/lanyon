---
layout: post
title: Some quick Git tips
---

If you want to save yourself some time when using Git, try making a
few changes to your `.gitconfig`.

My current non-default recommendations are:

```
[pull]
	rebase = preserve
[branch]
	autosetupmerge = always
[remote]
	pushdefault = origin
```

## What do these do?

### `rebase = preserve`

This means that when we run a `git pull` it rebases any of our changes on top of what was pulled, whilst preserving our own merging structure.

### `autosetupmerge = always`

This means that when we do `git checkout -b newbranch` from develop, `newbranch`
is set to track `develop`.

### `pushdefault = origin`

Normally when we branch off develop, make a change, commit, and try to push,
we find that our new branch does not have a remote branch, and git prompts
us to set one. This automates that process, so one can branch, commit, and
immediately push to origin.

## What's the upshot?

I can `git checkout -b mynewfeature` to create a new feature, `git push` to push,
and `git pull origin develop` to grab new changes that others have made, whilst
not worrying about creating unnecessary merge commits.

Obviously these are only defaults - on feature branches etc. you probably want to be
using merges.
