


1. reset soft or hard?

With `--hard`, the changes would be dropped, and while with `--soft`, the changed would be kept instead.

>--soft
>
>Does not touch the index file or the working tree at all (but resets the head to <commit>, just like all modes do). This leaves all your changed files "Changes to be committed", as git status would put it.
>
>--hard
>
>Resets the index and working tree. Any changes to tracked files in the working tree since <commit> are discarded.

Example:

```
// same as git commit --amend
git reset --soft HEAD^
// do some updates
git commit -c ORIG_HEAD
```

