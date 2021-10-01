# Text Processing

This article records the text-processing skills based on shell tools. Use cases will be recorded with task need to handle

  ## Case 1
  * Task. 
  Have text like this
  > details: {"Items":{"OnlyInSource":["419299832-4085646730-1618320738","419299832-6585602434-16183072
47"],"OnlyInDestination":["419299832-6585602434-1618301144","419299832-4085646730-1618316684"]}}|

  * Objective.
  Get 4085646730, 6585602434, 6585602434, 4085646730 and **remove the duplicate**

  * Tools involved:
  **grep, awk, sort, uniq**

  ```
  grep -a '(?<=OnlyInSource":\[").+(?="\],)' text_file -oP | awk -F',' '{for(i=1;i<=NF;i++) {print $i}}' | awk -F'-' '{print $2}' >> result_file 
  grep -a '(?<=OnlyInDestination":\[").+(?="\])' text_file -oP | awk -F',' '{for(i=1;i<=NF;i++) {print $i}}' | awk -F'-' '{print $2}' >> result_file
  sort result_file | uniq > result_file_without_duplicate
  ```
  * Key Points
    * Util **(?<=pattern)** and **(?=pattern)** of perl get grouped match. Refer to: https://perldoc.perl.org/perlre#Extended-Patterns

  * Task Version 2 
      * What if get `"419299832-4085646730`? Remove the `-` and `"` ?
        ```
        grep -a '(?<=OnlyInSource":\[").+(?="\],)' text_file -oP | awk -F',' '{for(i=1;i<=NF;i++) {print $i}}' | awk -F'-' '{print $1, $2}' | sed 's/"//' >> result_file
        ```

  ## Case 2
  * Task.
  Have multiple log files which contains the following
  >2021-05-09 21:59:05.058832|INFO|-|logger_tool.go:23|xx.go:226|data source. get data shopid: 409980694| 

  * Objective
  Get the sum of all the `shopid`

  * Tools involved:
  **grep, awk**

  ```
  grep "get data shopid" data.log* -c | egrep ":[0-9]+" | awk -F':' '{sum+=$2} END {print sum}'
  ```


  * Key Points
    * Difference of `sum` and `$2` of `awk`
 
