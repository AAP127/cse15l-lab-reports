# Week 4 Lab Report: Testing and Debugging


## Code Change 1
Failure inducing input: https://github.com/AAP127/markdown-parse/blob/main/test-file2.md

The first major code change occurred to account for MarkdownParse.java returning no output when running on test-file2.md. The program would freeze when trying to parse the file, likely due to it's incorrect formatting.

![FirstIniniteLoop](week_4_source/InfiniteLoopFreeze.PNG)

Upon printing the value of `nextCloseBracket`, we saw that "-1" was constantly being printed to the terminal, leading us to suspect something was causing an infinite loop.

![SecondIniniteLoop](week_4_source/InfiniteLoopNums.PNG)

To allow the program to account for the formatting of test-file2.md, we added a statement to check if a left bracket can be found; the program with inform the user of invalid input.

![GithubInvalidInput](week_4_source/GithubInvalidInput.PNG)

The main issue with this test case was that the improper formatting, missing a right bracket, led the program to hang trying to find it. The "bug" of the program- it requires a rigid structure- meant that this situation would lead the program to give no response when running test-file2.md. 

## Code Change 2
Failure inducing input: https://github.com/AAP127/markdown-parse/blob/main/test-file2.md

After changing the code to not completely stall the MArdownParse.java, it would run test-file2.md, but still had some problematic results, showing up as incorrect output.