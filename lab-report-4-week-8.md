# Lab Report 4
## Sneaky Markdown Link Cases

For this Lab Report, we will be going over more test cases dealing with the Markdown Links format with a focus on the sneaky/edge cases to test our MarkdownParse file on these edge cases.

The two repositories that are used for this lab report is:

* [Our group's repo](https://github.com/alexlee39/new-md-parse)
* [Peer's repo](https://github.com/alexlee39/Peer-Review-MdParse)

### Snippet 1

Here is one Snippet of a markdown file with many edge cases down below.

![SS](/labrep4ss/Snip1Preview.png)

We see from this preview, that there are 3 correct md links in this md file, which correspond to "`google.com", "google.com", and "ucsd.edu"

So when I run it on my group's MarkdownParse.java file through a jUnitTest, if it is implemented correctly and can handle these edge cases, we should see the same output that we just mentioned. 

![SS](/labrep4ss/MDParseSnip1TestCase.png)

However, we don't and we see:

![SS](/labrep4ss/Snip1Output.png)

When I run on my peer's group's repo through the same jUnit Testcase we get:

![SS](/labrep4ss/PeerSnip1Output.png)

We see that in both repos, our MarkdownParse.java files aren't suited/implemented correctly to correctly identify which statements are in the proper md format. 

To fix this implementation of MarkdownParse.java, I believe that there would be a small code change. (Finish this!)

Get index of "`", 

### Snippet 2

Here is the Snippet given to us:

And when we preview this md file, we see:

![SS](/labrep4ss/Snip2Preview.png)

Which is based on md link format with nested parenthesis and additional brackets.

When I converted this into a jUnit test in my MarkdownParseTest.java file, I got:

![SS](/labrep4ss/MDParseSnip2Testcase.png)

For my group's implementation of MarkdownParse.java, we got this following error:

![SS](/labrep4ss/Snip2Output.png)

For our peer's group implementation of MarkdownParse.java, we got this following error: 

![SS](/labrep4ss/PeerSnip2Output.png)

Which means both my group and my peer's group implementation doesn't correctly identify the nested parenthesis in this Snippet md file.

I don't think there is a short, easy way to implement this change because the nested parenthesis are very tricky to follow....(FINISH THIS!)
### Snippet 3

For the last snippet md file, we preview it:

![SS](/labrep4ss/Snip3Preview.png)

This Snippet file dealt with issues regarding lines spacing with md links.

When I converted it into a jUnit Test in the MarkdownParseTest.java file, we get:

![SS](/labrep4ss/MDParseSnip3Testcase.png)

For my group's implementation of MarkdownParse.java, we got the following error:

![SS](/labrep4ss/Snip3OutputSmall.png)

For my peer's group implementation of MarkdownParse.java, they also got another error:

![SS](/labrep4ss/PeerSnip3Output.png)

I believe this implementation would be pretty easy and short to fix because you only need to account for (FINISH THIS!)