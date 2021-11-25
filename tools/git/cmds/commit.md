


* --amend


* --author
  > --author=<author>
  >
  > Override the commit author. Specify an explicit author using the standard `A U Thor <author@example.com>` format. Otherwise <author> is assumed to be a pattern and is used to search for an existing commit by that author (i.e. rev-list --all -i --author=<author>); the commit author is then copied from the first such commit found.
  
  * Can be used to reset author  
 

* --no-edit
  > --no-edit
  >
  > Use the selected commit message without launching an editor. For example, git commit --amend --no-edit amends a commit without changing its commit message. 

* *Examples*
  ```
  git commit --amend author="brofu <brofu@xx.com>" --no-edit
  ```

