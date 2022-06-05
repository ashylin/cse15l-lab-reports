# Lab Report 5

- Explaination:

I used vim to find the tests with different results but I did not search through it manually.

- Link to test file with different results:

[test-file-1](https://github.com/nidhidhamnani/markdown-parser/edit/main/test-files/41.md)

[test-file-2](https://github.com/nidhidhamnani/markdown-parser/edit/main/test-files/481.md)

## test-file-1

My implementation was not correct but the one provided was.

- actual output: [url "tit"]
- expected output: []

![image](https://user-images.githubusercontent.com/103166380/172074910-ecba77ec-e5b3-4a42-aa1b-79b4fc74a891.png)

![image](https://user-images.githubusercontent.com/103166380/172074411-8d18570b-eac4-4ebe-90f7-f80df2e53c75.png)

- Code that should be fixed:

![image](https://user-images.githubusercontent.com/103166380/172074503-9742515a-8dc2-43c2-9993-423cbe990d18.png)

I am getting the wrong output because my code looks for the strings within openParen "(" to closeParen ")". This is not necessarily always the correct output. To fix that
I would need to implement code that would check if the strings within the parentheses contain any space and if they do it will not subString into the the links toReturn.

## test-file-2

My implementation was correct but the given implementation was not.

- actual output: []
- expected output: [/uri "title"]

![image](https://user-images.githubusercontent.com/103166380/172075538-31fd2df9-ff7a-4232-a473-f57f8b40b00c.png)

![image](https://user-images.githubusercontent.com/103166380/172074796-199b9d4a-3cb2-4a1c-ab14-c394017942f1.png)

- Code that should be fixed:

![image](https://user-images.githubusercontent.com/103166380/172075656-9033f7e6-5d39-41ab-8263-24b413502b34.png)

The code results in no output because of the empty line after the link on line two, which causes the openParen to not be found. This results in an infinite loop 
because the openParen count did not increment. To fix this, an if statement could be added inside the while loop so that if a closeParen is found then the loop breaks.
