# Network

  Record the tools/skills about networking


## Case 1
  * Task
  
    Find out which process is taking the network bound


  * Tools 

  **iftop, netstat/ss, ps**

  * Cmd

  ```
  iftop -n -P // get the top traffic host:port
  ss -nap | grep "host:port" // find the process which owns the port
  ```

  * Key Points 
  
    * Meaning of `iftop` output


