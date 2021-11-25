
Q: How to update the `authors` for commits. For example, the `user.name` and `user.email` is WRONG configured previously?
A: 
  * If only the latest commit need to update, may try `soft reset` or `commit --amend`
    * soft reset
        *  example
            ```
            git config --local user.name brofu
            git reset --soft HEAD^  
            git commit -c ORIG_HEAD
            ```
    * commit --amend
        * example
            ```
            git commit --amend --author="brofu <brofu@xx.com>" --no-edit    
            ```
