---
layout: post
title: "Linear Git History With Git Rebase"
---

A lot of consumers of hosted source control solutions like GitHub or BitBucket have a very straightforward workflow around handling pull requests. They do some code review, maybe ask for a few changes, and then, when the pull request is approved, they hit the "merge" button and move on with their days. This workflow "just works". Code that a developer writes will find its way into the primary branch of your repository this way, sure - there's no denying that. If you have a very active development team, though, you'll find that all of those extraneous merge commits can make the history of your master branch very noisy and difficult to follow. This is where `git rebase` can help us, as source control maintainers.

Merging and rebasing are both solutions to the same problem. They both exist to integrate changes from one branch into another branch. Merging solves this problem in a non-destructive fashion, by generating a 'merge commit' and merging the histories of the two branches together. Rebasing instead attempts to 'replay' all of the commits in the working branch on top of the target branch. This is considered a destructive operation, since you're rewriting the history of your branch - so be warned!

Rebasing allows me, as one of the maintainers of our project repositories, to keep a clean, easily traceable history across multiple projects. By enforcing good commit message standards, the log of commits in master is easily traversable, understandable, and free from extraneous merge commits. By performing interactive rebases, I can also edit commit messages during the pull request merging process to add references to GitHub issues, JIRA tasks, and more. I have much more power over how code gets into master than I would if I was just clicking the merge button on GitHub.
