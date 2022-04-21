# Lab 3 Report

## Code changes:

1) Code diff:
![image](https://user-images.githubusercontent.com/103166380/164381005-92c914b3-0ed9-4499-8e23-3d28458f8f34.png)
[Test file](https://github.com/pranay-jha/markdown-parser/commit/9a6d50cca290dc103e1ad45ab2f82a81f6ee7828)

Failure-inducing input:
![image](https://user-images.githubusercontent.com/103166380/164381202-1cb1d207-9b09-4da3-8fd6-836b33ad9a6c.png)
Line 3

Symptom of failure-inducing input: wrong output

`[https://something.com, some-thing.html, dog.png]`

The symptom of the code before the change was the wrong output of `[https://something.com, some-thing.html, dog.png]`. The failure-inducing input was when one of our lab 
members used colon instead of parentheses to reference a link. The bug was that the link that was referenced with colon was not printed. 

2) Code diff: 
![image](https://user-images.githubusercontent.com/103166380/164546773-4e854ba7-ac7d-4259-84f7-e08edba997eb.png)
[Test file](https://github.com/KSB2003/markdown-parser/commit/04ddf65f8ba6847fd337df19d2f85624a16dde75)

Failure-inducing input:
![image](https://user-images.githubusercontent.com/103166380/164546900-5c09c9ff-c16e-4a10-974b-fe1b2fc72464.png)

Symptom of failure-inducing input: wrong output

`[https://www.youtube.com/watch?v=5_2DRVYNxYI]`

The symptom of the code before changes were made was the wrong output. Similar to the one, the failure-inducing input was referencing a link with colon instead of 
parentheses. The bug was that the link referenced with a colon was not printed when the code was ran.

3) Code diff:
![image](https://user-images.githubusercontent.com/103166380/164543916-8677749d-2107-4763-b084-ff6c100d7d9d.png)
[Test file](https://github.com/ehsly/markdown-parser/commit/1f8aaa2d7e203e0c68a1768812fa37643ee007bd)

Failure-inducing input: 
![image](https://user-images.githubusercontent.com/103166380/164544038-f2d8d8f3-17e2-49d6-b278-a928806649ab.png)

Symptom of failure-inducing input: exception error
```
Exception in thread "main" java.lang.StringIndexOutOfBoundsException: begin 17, end -1, length 17
        at java.base/java.lang.String.checkBoundsBeginEnd(String.java:4601)
        at java.base/java.lang.String.substring(String.java:2704)
        at MarkdownParse.getLinks(MarkdownParse.java:19)
        at MarkdownParse.main(MarkdownParse.java:29)
```

The symptom of the code before changes were made was the exception error `IndexOutofBounds`. The failure-inducing input was when there is an incomplete set of brackets or
parentheses within the file. The bug is that there was no link referenced within the file and the code couldn't run because it threw an exception error.
