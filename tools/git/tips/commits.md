
Q: How to update the `authors` for commits. For example, the `user.name` and `user.email` is WRONG configured previously?

A: 
* If only the latest commit need to update, may try `soft reset` or `commit --amend`
    * soft reset
      ```
      git config --local user.name brofu
      git reset --soft HEAD^  
      git commit -c ORIG_HEAD
      ```
    * commit --amend
      ```
      git commit --amend --author="brofu <brofu@xx.com>" --no-edit    
      ```
* Amend multiple commits
    ```
    git rebase -i HEAD~3
    // change the `pick` to `edit` for each commit.
    git commit --amend --author="brofu <brofu@xx.com>" --no-edit    
    git rebase --continue
    // repeat the above 2 steps, till all the commits are amended.
    git push -f
    ```
* Refer
    * https://www.git-tower.com/learn/git/faq/change-author-name-email
    * https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History#Changing-Multiple-Commit-Messages

