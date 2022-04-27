# Lab 3 Report

1) Code change diff:
![image](https://user-images.githubusercontent.com/103166380/164381005-92c914b3-0ed9-4499-8e23-3d28458f8f34.png)

[Test file](https://github.com/pranay-jha/markdown-parser/blob/main/test-file2.md) for *failure-inducing input*

Symptom of *failure-inducing input*: wrong output
```
[https://something.com, some-thing.html, dog.png]
```

The symptom of the code before the change was the wrong output of `[https://something.com, some-thing.html, dog.png]`. The failure-inducing input was when one of our lab members used colon instead of parentheses to reference a link. The bug was that the link that was referenced with colon was not printed. 

2) Code change diff:
![image](https://user-images.githubusercontent.com/103166380/164543916-8677749d-2107-4763-b084-ff6c100d7d9d.png)

[Test file](https://github.com/ehsly/markdown-parser/blob/main/test-file2.md) for *failure-inducing input*

Symptom of *failure-inducing input*: exception error
```
Exception in thread "main" java.lang.StringIndexOutOfBoundsException: begin 17, end -1, length 17
        at java.base/java.lang.String.checkBoundsBeginEnd(String.java:4601)
        at java.base/java.lang.String.substring(String.java:2704)
        at MarkdownParse.getLinks(MarkdownParse.java:19)
        at MarkdownParse.main(MarkdownParse.java:29)
```

The symptom of the code before changes were made was the exception error `IndexOutofBounds`. The failure-inducing input was when there is an incomplete set of brackets or parentheses within the file. The bug is that there was no link referenced within the file and the code couldn't run because it threw an exception error.

3) Code change diff:
![image](https://user-images.githubusercontent.com/103166380/164603187-3f0d6bea-1d5c-4c10-a681-195ecf3877d3.png)

[Test file](https://github.com/ehsly/markdown-parser/blob/main/test-file3.md) for *failure-inducing input*

Symptom of *failure-inducing input*: infinite loop

The bug was that nothing was printed since the program wouldn't stop because the symptom was the infinite while loop caused by the failure-inducing input which was not having a close parentheses in the markdown file. `currentIndex` was never updated because it `closeParen` was never found within the file.
