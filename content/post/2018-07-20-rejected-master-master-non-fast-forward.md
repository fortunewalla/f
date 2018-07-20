---
title: '! [rejected]        master -> master (non-fast-forward)'
author: fw
date: '2018-07-20'
slug: rejected-master-master-non-fast-forward
categories:
  - nt
tags:
  - error
  - git
  - github
  - master
  - origin
  - pull
  - push
---
* Added commit as another user in local and pushed to github master
* Now had to revert to previous to last commit and again push

```{bash}
X:\git\www>git rebase -i HEAD~2
Successfully rebased and updated refs/heads/master.

X:\git\www>git push -u origin master
OpenGL Warning: crPixelCopy3D:  simply crMemcpy'ing from srcPtr to dstPtr
fatal: TaskCanceledException encountered.
   A task was canceled.
Username for 'https://github.com': fortunewalla
Password for 'https://fortunewalla@github.com':
To https://github.com/rbind/f.git
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'https://github.com/rbind/f.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

X:\git\www>git remote add origin https://github.com/rbind/f.git
fatal: remote origin already exists.

X:\git\www>git fetch origin master
From https://github.com/rbind/s
 * branch            master     -> FETCH_HEAD

X:\git\www>git merge origin master
Updating ff314c0..039df58
Fast-forward
 config.toml                                           |   2 +-
 public/404.html                                       |   2 +-
 public/about/index.html                               |   2 +-
 public/categories/index.html                          |   2 +-
 public/categories/test/index.html                     |   2 +-
 public/index.html                                     |   4 ++--
 .../figure-html/pressure-1.png                        | Bin 8891 -> 7134 byt
 public/post/index.html                                |   2 +-
 public/post/test-post-for-blogdown/index.html         |   2 +-
 public/tags/index.html                                |   2 +-
 public/tags/r/index.html                              |   2 +-
 public/tags/test/index.html                           |   2 +-
 s.Rproj                                               |   2 +-
 .../figure-html/pressure-1.png                        | Bin 8891 -> 7134 byt
 14 files changed, 13 insertions(+), 13 deletions(-)

X:\git\www>git push -f origin HEAD^:master
fatal: TaskCanceledException encountered.
   A task was canceled.
Username for 'https://github.com': fortunewalla@yahmail.com
Password for 'https://fortunewalla@yahmail.com@github.com':
remote: Invalid username or password.
fatal: Authentication failed for 'https://github.com/rbind/f.git/'

X:\git\www>git push -f origin HEAD^:master
OpenGL Warning: crPixelCopy3D:  simply crMemcpy'ing from srcPtr to dstPtr
fatal: TaskCanceledException encountered.
   A task was canceled.
Username for 'https://github.com': fortunewalla@yahmail.com
Password for 'https://fortunewalla@yahmail.com@github.com':
Everything up-to-date

X:\git\www>git commit
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean

X:\git\www>git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean

X:\git\www>git rebase -i HEAD~2
Successfully rebased and updated refs/heads/master.

X:\git\www>git push -f origin HEAD^:master
fatal: TaskCanceledException encountered.
   A task was canceled.
Username for 'https://github.com': fortunewalla
Password for 'https://fortunewalla@github.com':
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/konkaniculture/www.git
 + a3156de...3f02fba HEAD -> master (forced update)

```