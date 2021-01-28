---
id: doc1
title: Development workflow
sidebar_label: Development workflow
---

## Before you start
You're going to be using git a lot so make sure that: 
1. [git](https://git-scm.com/) is installed on your host
1. You have a **solid understanding on what [git is](https://en.wikipedia.org/wiki/Git)** and you've understood 
commits, remote/local repositories, and [how to write good commit messages](#commiting-your-work). If you're not certain, visit 
[Github's resources](https://try.github.io/) and revisit basic git concepts and commands.
1. You are acquainted with the [GitFlow workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) and [Feature branches](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow).
Check this [interactive tutorial](https://learngitbranching.js.org/) on branching for some warm-up.

## Starting your task
Initiating a task means that by now, a [github/jira/whatever issue](https://guides.github.com/features/issues/) has been created
on a [project board](https://docs.github.com/en/github/managing-your-work-on-github/about-project-boards)
and that it was assigned to you. 

### Set task to `In progress`
Issues start at a `Todo` state and which indicates that no work has been done yet.
Move the issue to the `In progress` state and indicate that you've started working on it.

### Create a new branch 
As our branching model dictates, there are two branches of significance: 
- `master` branch (or `main` [as of quite recently](https://github.com/github/renaming)): holds all production releases.
This branch **receives no commits directly** and **branches created from it, are necessary only for bug fixes**.
- `development`: the main development branches. All feature branches are created from it and all feature branches are 
merged into it.

Create a new branch from the main development branch (a.k.a. the `develop` branch) using the following format:
```
{source branch}_{feature's short name/task description or the issue number}

Example branch name using issue number:
"development_issue-134"

Example branch name with issue/task description:
"development_modify_home_screen"
```

## During development
This is where coding starts. Make sure that you have developed a **solid understanding** of both the **technical aspect**
of the task as well as its **business impact** (or value). Ask your team openly on the project's slack channel or ask a senior
project member for guidance when issues arise. Prefer **posting questions to public channels instead of PMs** (Private messages) as this
will _make information widely available to the team_ and allow others to take benefit from it. 

## Commiting your work
Once you are confident that the implementation is finished you can commit your work.
Follow the commit checklist:
1. View your unstaged files one by one and:
    - Remove trailing spaces and unnecessary newlines
    - Get rid of commented out code
    - Undo changes that are irrelevant
2. Stage changes and review your files. Study the diff one more time.
3. Write a **good commit message**: 
    - Avoid long lines (50-60 characters per line)
    - Use [imperative mood](https://chris.beams.io/posts/git-commit/#imperative)
    - Be descriptive of what you did an _how_. Provide context information.
    - Provide relations to issue/task number (e.g. "_#55 Fix typo_")

    _Examples_

    Short commit message:
    ```
    #155 Remove Customer.VatNumber property
    ```

    Long commit message:
    ```
    #155 Remove VatNumber property

    - Update tests
    - Drop index from Customer.VatNumber table
    ```

    > A diff will tell you what changed, but only the commit message can properly tell you why
## Submit for review
1. Open a [Pull Request](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests)
and enable other team members to review and approve the implementation. Collective work leads to 
better results, so, feedback from the Team should be taken into account and may lead to 
code changes or re-writes.
2. Once the PR is approved, then **merge your feature branch into development**,
and delete the feature branch from the `remote`.
3. Move the related issue to `Done` state.
4. Pour some coffee and start from the beginning.

