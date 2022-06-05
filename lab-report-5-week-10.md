# Lab Report 5 Week 10

## Comparing two different outputs from personal MardownParser and the MarkdownParser given:

There were two tests that produced different results as seen here: 

![Report1](Report5.1.png)
![Report2](Report5.2.png)

This was found by using the bash script and putting the output onto a new text file titled *results.txt*. For test file 135, the personal MarkdownParser returned an array with one value and the other did not. In test file 246, the personal MarkdownParser returned another array while the other one did not. 

> Note: the two images come from the file 159.md and 211.md. test 159.md can be found [here](https://github.com/brandoluu/markdown-parser/blob/main/test-files/159.md) and 211.md can be found [here](https://github.com/brandoluu/markdown-parser/blob/main/test-files/211.md). *

The output for the two markdown files are:
![159](159.png)
![211](211.png)

As seen from the two images, the two images show that there are no links. However when looking at the results from the earlier images, the personal MardownParser returned an array with links while the other one did not. Therefore there is a bug in the personal MarkdownParser. 

## Analyzing the bug in the code:
----------
As mentioned previously, there is a bug in the personal MarkdownParser where an array of links will be returned even if the markdown file doensn't have any links. 

A possible error for this is that the implementation does not check for a valid link even if there are parenthesis and brackets invovled. Before the loop to parse whatever is after the *[]*, there are checks to see if the correct brackets are present in the file as shown below:
![markdownparse.java](MarkdownParse8.png)

In order to make this implementation stronger, it would be a good idea to add a check if the brackets after the first square brackets are valid, in order to find a valid link. 
