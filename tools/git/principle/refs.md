

* Content of `refs/heads`

```
➜ ls -al .git/refs
192 Nov 26 12:48 .
512 Jan 14 19:26 ..
512 Jan 11 11:26 heads
96 Aug  3  2020 remotes
41 Nov 26 12:48 stash
576 Jan 11 11:26 tags
```

* CMD related
> git update-ref

* Nature of `branch`
> A ref points to a `pointer` or `reference`, which actually a commit
> When a new branch set up, with `git branch <branch>`, `git update-ref` would be actually called.

* For example

```
➜ cat .git/refs/heads/test
c7e1be0ea101d6c7c960f7f36846f12daad57e97

➜ gco test
Switched to branch 'test'
Your branch is behind 'origin/test' by 113 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

➜ ssp git:(test) cat .git/$(cat .git/HEAD | sed 's/ref: //')
c7e1be0ea101d6c7c960f7f36846f12daad57e97

```

* `HEAD` reference

* `tag` reference


