# Lab Report #2 :Bugs with Markdown-Parse #


## Bug #1 ##

This is the first error, my group had when working on lab#3. 
[Link to Error Commit](https://github.com/dmontefalcon/markdown-parser/commit/3575612d2b76784629c1ba44f4459d7c183d45c8) 

![Screenshot](/screenshots/2nderror.png)

The symptom we saw after running the Markdown-parse file with a new markdown file was that we got an out of Memory Error. This commit change shows that the file had a space after the 2nd link which gives us an infinite loop in our Markdown-parse file and code. Thus the bug in this case was that the while loop didn't end which there was another line at the end of new markdown file. To solve this bug, we added an conditional that checked if there was any openBracket in the line. If there was none, it would end the loop.

This is our solution to the first bug.
![Screenshot](/screenshots/2ndsol.png)

## Bug #2 ##

This is our second error, we found as a group. [Link to 2nd Error Commit](https://github.com/dmontefalcon/markdown-parser/commit/ebc853d4ad03143444821d342b8920506932a8c8)

In this screen shot, the test file outputs a link after running it through our Markdown-parse file despite it being in the incorrect markdown format for a link.
![Screenshot](/screenshots/1sterror.png)

In this error that we found is that the code doesn't correctly identify links. In this example, we had a space between the brackets and the parenthesis for the link which should not correctly output a link in markdown. However, in after running our java file we see that it does output the link after we run it. Hence, our symptom in this case is that it incorrectly identify links even though it might not be in a correct format. To fix this bug, we added another conditional that made sure the open parenthesis was next to the close bracket.

This is what we added to fix the 2nd error.
![Screenshot](/screenshots/1stsol.png)


## Bug #3 ##
For this errorcase, we checked if there would be any symptoms if we had the brackets for a link but not the parenthesis. [Link to 3rd Error Commit](https://github.com/dmontefalcon/markdown-parser/commit/896c5d2ea2a55952a644e14731fbf4dd98dcda3d) 

![Screenshot](/screenshots/3rderror.png)

This is the symptom after running the Markdown-Parse java file.
![Screenshot](/screenshots/3rderrorsymptom.png)

After seeing this symptom of an IndexOutOfBound Exception, our group identified that we got this symptom because there was no parenthesis. Therefore, the bug was that it gets the substring between the parenthesis which were both at the index of -1 which gave us the symptom. To fix this, we added a conditional that made sure if there was no open parenthesis(i.e: the index is -1) that we would break the while loop.

![Screenshot](/screenshots/3rdsol.png)



