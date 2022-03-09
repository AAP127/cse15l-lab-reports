# Week 10 Lab Report: MarkdownParse Implementation Differences

To understand the differences between my implementation and the instructors' implementation of markdown-parse, I ran a bash script which parsed all 652 files, and then saved the results to a file, for both implementations. 

I originally used `diff` to determine the differences between these files, however ran into discrepancies in file formatting. For the following output differences, I ended up just manually searching for differences, using `diff` to give me an idea of generally where they might be.


## Output Difference 1: `571.md`
In the instructors' implementation, test file 571 returns as an empty list, while my implementation returns a list containing `[url "title"]`. The file's actual contents are as follows:

```
![foo](/url "title")
```

Given the break within the "url" of the link, this is an invalid link, and MarkdownParse should return an empty list. In this case, the instructors' implementation was more accurate.









1043c1040        /url "title" 571   :empty 571
1053c1050         not a link  :empty 567
921c910         /url 'title "and" title'    : empty508