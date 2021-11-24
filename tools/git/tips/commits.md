
Q: How to update the `authors` for commits. For example, the `user.name` and `user.email` is WRONG configured previously?
A: 
  * soft reset
  
      ```
      git config --local user.name brofu
      git reset --soft HEAD~3   
      git commit
      ```
      cons: lost commit info
