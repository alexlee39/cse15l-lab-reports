# Lab Report #2

## Bugs with Markdown-Parse ##

### Bug #1 ###
![Screenshot](2nderror.png)

![Screenshot](2ndsol.png)

[Link to Error Commit](https://github.com/dmontefalcon/markdown-parser/commit/3575612d2b76784629c1ba44f4459d7c183d45c8) 

This is one of the bugs, our group saw in our lab #3. When we tested the file on test2.md which should print the two links in a list. However, when we ran the file, we got a symptom which tells us that java ran out of heap space, meaning that there was an infinete loop. We realised that the bug in this testfile was it didn't properly check when the file ended. Hence, we added a conditional that would break the while loop if the code couldn't find an open bracket.


![Screenshot](1sterror.png)

![Screenshot](1stsol.png)

[Link to 2nd Error Commit](https://github.com/dmontefalcon/markdown-parser/commit/ebc853d4ad03143444821d342b8920506932a8c8)

In this error that we found is that the code doesn't correctly identify links. In this example, we had a space between the brackets and the parenthesis for the link which should not correctly output a link in markdown. However, in our file we see the symptom that it does output the link after we run it. To fix this bug, we added another conditional that made sure the open parenthesis was next to the close bracket.

![Screenshot](3rderror.png)

![Screenshot](3rdsol.png)

[Link to 3rd Error Commit](https://github.com/dmontefalcon/markdown-parser/commit/896c5d2ea2a55952a644e14731fbf4dd98dcda3d)

![Screenshot](3rderrorsymptom.png)

In our final error, we realized another potential bug to our MarkdownParse java file is if there are brackets but aren't parenthesis. The symptom would output an IndexOutOfBounds exception because there are no parenthesis despite being brackets. Hence, when we run the line of code which adds the substring between the parenthesis, it would output our symptom because the IndexOf the parenthesis would be -1 which would be an invalid input for our line of code.