# Lab Report #5 #

## Debugging and Working with Test Cases

This Lab Report revolves around markdown-parse again and using vim and other script commands, etc to help debug and find differences between two different implementations of MarkdownParse.java given around 652 different markdown files to test upon.

To compare these testfiles between two different implementations we first had to run **bash script.sh > results.txt**, which would store the outputs of each md testfile into a text file called *results.txt*. Afterwards we call vimdiff to compare these two implementations to which we get a multiple of files that the MarkdownParse.java implementation fails upon. 

Our group found two testfiles in particular to investigate further upon which are test: **32.md** and **194.md** 

### Test1: 32.md

[Link to md file](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/32.md)

Output of testfile **32.md** for both implementations:

![SS](/labrep5ss/Test2.png)

In this screenshot the left side corresponds to the the MarkdownParse.java implementation that was given to us while the right side corresponds to our group's custom implementation fo MarkdownParse.java. 

As we can see for the given markdown-parser we get an output of **[]**, but for my group's markdownparser we get **[/f & ouml;& ouml; "f& ouml;& ouml;"]**.
Without the spaces between **&** and **o**.

However, when we compare to the actual output we get:

![SS](/labrep5ss/test2expected.png)

Which shows that the expected output of the link is f&ouml;&ouml;. Hence both of our implementations of MarkdownParse.java is wrong. 

Lets look at the my groups MarkdownParse.java file and see what changes need to be applied. So we can see that there a patternwhich is that the **&** symbol + *o* + **ml;** produces the special character &ouml;. Hence we can add changes here that add this condition which checks for & + ml; which would change that character/word in between it to be a special character/word with an accent mark on top of it.

![SS](/labrep5ss/vscodetest2wheretofix.png)

So we would create another conditional(if statement) between the two if statements in the red cirlce to check if there are &ml in between open and closed parenthesis. We would also need to add a conditional that checks for two "" and ignore the text in between the two quotation marks.

### Test2: 194.md

[Link to md file](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/194.md)

![SS](/labrep5ss/Test1.png)

The outputs we get from our implementations of MarkdownParse is **[url]** for the given markdown-parser and **[]** for our group's implementation.

However, when we compare this to the expected output:

![SS](/labrep5ss/test1expectedoutput.png)

This expected output is my_(url) oddly enough. 

Let's see how we could maybe change our code in the given MarkdownParse.java to add this.

So first I started to play around with the md links format: 

![SS](/labrep5ss/playing.png)

To only realize how the forward slash **\ + ]] + :** causes the whole link to terminate/not appear. However, if we add the same format for the name of the link(**[hi\]]**) we would get a link that appears that contains everything after the colon(:) aside from ` or ".

If we look back to the MarkdownParse.java given to us: 

![SS](/labrep5ss/unsure.png)

We would need to change the last part of the statements and probably add another conditional checking for **\ + ]] + :**. If the link does contain it, we would need the same link name to be duplicate in order to add the link after the :. This would probably be a very complicated fix as it might break other things in our MarkdownParse.java