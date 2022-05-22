# Lab Report 4

This lab report talks about how to use junit to debug `MarkdownParser.java` through writing junit tests for edge cases.

Links to my repo and the reviewed repo:
* [my MarkdownParse repo](https://github.com/Rena2025/markdown-parser-new)
* [reviewed MarkdownParse repo](https://github.com/ayushs2725/markdown-parser)

## Snippet 1
* Preview on VScode: ![image](lab4-2.png)
* Expected output: [`google.com, google.com, ucsd.edu]

* Junit test:
![image](lab4-5.1.png)

* My implementation did not pass the junit test:
![image](lab4-5.1.2.png)

* Reviewed repo's implementation also did not pass the junit test:
![image]()

* Possible solution: Since my implemenation worked for all the links except the first one, I need to focus on that case. When there is a back tick right in front of the open bracket, search for the next open bracket and update `openBracket` with the index of the most recent open bracket found.

## Snippet 2
* Preview on VScode: ![image](lab4-3.png)
* Expected output: [a.com, a.com(()), example.com]

* Junit test:
![image](lab4-5.2.png)

* My implementation did not pass the junit test:
![image](lab4-5.2.2.png)

* Reviewed repo's implementation also did not pass the junit test:
![image]()

* Possible solution: Since my implemenation worked for all the links except the second one, I need to focus on that case. The error was generated because my implementation wrongly recorded the index of the first close parenthesis instead of the third one, so I could use a while loop to find the index of the last close parenthesis of this link. In other words, if `closeParen + 1 == ')'`, then I increment the index of closeParen, given that index don't go out of bounds. 

## Snippet 3
* Preview on Commonmark: ![image](lab4-snippet3.png)
* Expected output: [https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule]

* Junit test:
![image](lab4-snippet3junit.png)

* My implementation did not pass the junit test:
![image](lab4-snippet3error.png)

* Reviewed repo's implementation also did not pass the junit test:
![image]()

