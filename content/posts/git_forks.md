---
title: "Simplify your git fork workflow with this easy hack"
slug: "git-fork-hack"
date: "2020-09-19"
---

Okay so the title is a clickbait. This is not a hack, it's just about setting git
configuration differently. However, a surprisingly small number of people knows
about it, even within ones who consider themselves git experts. If you already
know about this setup congratulations, you rock! If not, this is your chance to
become one of the [lucky ten thousand] and make your workflow less painful.

## What's the problem?

So you decided to contribute to a project that lives on GitHub or GitLab. The
typical setup here is to have the parent repo (to which you want to contribute)
and your fork of the repo where your changes live before they are merged. You keep
the parent and fork repos in sync and do all work in the fork. Easy, right? The
elephant in the repo is that it's really easy to forget to update your fork with
this flow. Get into the right directory, run `git pull`, create a new branch, do
the work, submit the pull request... oops old conflicts because you forgot that
you were working from your fork which was not updated!

## Harness the powers of `.git/config`

**Having to keep your fork in sync is a lie**. The only case when you need it is
when you have other people working from *your fork* instead of the parent repo,
which is a very specific use case irrelevant 99% of the time. Instead, you can
work directly from the main branch of the parent repo, ignoring your fork's main
branch completely because *you don't need it at all*.

How do you do it? Let's showcase what I'm talking about by an example of my own
`.git/config`:

```
[remote "origin"]
	url = https://gitlab.com/veruu/reporter
	fetch = +refs/heads/*:refs/remotes/origin/*
[remote "upstream"]
	url = https://gitlab.com/cki-project/reporter
	fetch = +refs/heads/*:refs/remotes/upstream/*
[branch "main"]
	remote = upstream
	merge = refs/heads/main
```

The `origin` remote points to my fork and the `upstream` one to the parent repo.
This is nothing special. What is worth noticing is the configuration of the
main branch (in this case the `[branch "main"]` section), which doesn't point to
my fork but instead to the `upstream` remote! That's literally all that's needed,
switching the remote the branch is pointing to!

After switching the config you can happily work the same way you'd with a single
repo without a fork. Your local main branch will follow the parent repo so all
you have to do to keep it in sync is running `git pull` as you'd before. Then you
can go on with creating a new branch and development, and by running
`git push origin <branch>` you update your fork with the changes.



[lucky ten thousand]: https://xkcd.com/1053/
