---
parent: More info
nav_order: 800
description: Aider is tightly integrated with git.
---

# Git integration

Aider works best with code that is part of a git repo.
Aider is tightly integrated with git, which makes it easy to:

  - Use git to undo any aider changes that you don't like
  - Go back in the git history to review the changes that aider made to your code
  - Manage a series of aider's changes on a git branch

Aider specifically uses git in these ways:

- It asks to create a git repo if you launch it in a directory without one.
- Whenever aider edits a file, it commits those changes with a descriptive commit message. This makes it easy to undo or review aider's changes. 
These commits will have "(aider)" appended to their git author and git committer metadata.
- Aider takes special care before editing files that already have uncommitted changes (dirty files). Aider will first commit any preexisting changes with a descriptive commit message. 
This keeps your edits separate from aider's edits, and makes sure you never lose your work if aider makes an inappropriate change.
These commits will have "(aider)" appended to their git committer metadata.

## In-chat commands

Aider also allows you to use in-chat commands to `/diff` or `/undo` the last change.
To do more complex management of your git history, you cat use raw `git` commands,
either by using `/git` within the chat, or with standard git tools outside of aider.

## Disabling git integration

While it is not recommended, you can disable aider's use of git in a few ways:

  - `--no-auto-commits` will stop aider from git committing each of its changes.
  - `--no-dirty-commits` will stop aider from committing dirty files before applying its edits.
  - `--no-git` will completely stop aider from using git on your files. You should ensure you are keeping sensible backups of the files you are working with.


