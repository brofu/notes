

* start-point

  > git branch [--set-upstream | --track | --no-track] [-l] [-f] &lt;branchname&gt; `[<start-point>]`
  >
  > The command's second form creates a new branch head named <branchname> which points to the current HEAD, or <start-point> if given.

  *Example*

  * Setup new branch from a specific commit
   ```
   git branch original_branch
   git branch -b new_branch_name commit_id
   ```
