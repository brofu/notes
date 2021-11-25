
1. Understand the section of `RECOVERING FROM UPSTREAM REBASE` in the manual
    * Situation
      > To illustrate, suppose you are in a situation where someone develops a subsystem branch, and you are working on a topic that is dependent on this subsystem. You might end up with a history like the following:
      
      >         o---o---o---o---o---o---o---o  master
      >              \
      >               o---o---o---o---o  subsystem
      >                                \
      >                                 *---*---*  topic

      > If subsystem is rebased against master, the following happens:

      >         o---o---o---o---o---o---o---o  master
      >              \                       \
      >               o---o---o---o---o       o'--o'--o'--o'--o'  subsystem
      >                                \
      >                                 *---*---*  topic

    * Why need to `revover from upsteam rebase`? 
      >  If you now continue development as usual, and eventually merge topic to subsystem, the commits from subsystem will remain duplicated forever:

      >         o---o---o---o---o---o---o---o  master
      >              \                       \
      >               o---o---o---o---o       o'--o'--o'--o'--o'--M  subsystem
      >                                \                         /
      >                                 *---*---*-..........-*--*  topic
      >
      > Such duplicates are generally frowned upon because **they clutter up history, making it harder to follow.**
     
    * How to resolve? Need to rebase topic also. And this would lead to a ripple affect.
      > To clean things up, you need to transplant the commits on topic to the new subsystem tip, i.e., rebase topic. This becomes a ripple effect: anyone downstream from topic is forced to rebase too, and so on!

    * Easy case.
      ```
      git fetch 
      git checkout topic
      git rebase origin/subsystem
      git push -f
      ```

    * Hard case
    
      **There is update during rebase subsystem**
      ```
      git fetch
      git checkout topic
      git rebase --onto origin/subsystem <commit> // <commit> is the tip of old subsystem (before rebase), and on this commit, topic is checked out.
      git push -f
      ```

