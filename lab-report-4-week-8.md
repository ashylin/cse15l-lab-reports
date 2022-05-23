# Lab Report 4

[My markdown-parse repository](https://github.com/ehsly/markdown-parser)

[markdown-parse reviewed in week 7](https://github.com/ehsly/markdown-parser)

## Snippet 1
```
`[a link`](url.com)

[another link](`google.com)`

[`cod[e`](google.com)

[`code]`](ucsd.edu)
```
- markdown-parse should produce:
```
`google.com, google.com, ucsd.edu
```
- Code for how I turned it into a test in MarkdownParseTest.java

![image](https://user-images.githubusercontent.com/103166380/169741181-13d7e2d2-0bb2-4b45-8022-b5189934d9a3.png)

- My implementation

![image](https://user-images.githubusercontent.com/103166380/169744793-badb4713-b521-43e4-ac35-9c1f9fc01860.png)

- Implementation reviewed in Week 7

![image](https://user-images.githubusercontent.com/103166380/169746584-c16d081a-8564-42c5-a6e0-cf0bd86a4439.png)

- Small change (<10 lines)? Yes

Check if there is an odd number of backticks within the brackets. If there is, don't print the link following the brackets.

## Snippet 2
```
[a [nested link](a.com)](b.com)

[a nested parenthesized url](a.com(()))

[some escaped \[ brackets \]](example.com)
```
- markdown-parse should produce:

`a.com, a.com, example.com`

- Code for how I turned it into a test in MarkdownParseTest.java

![image](https://user-images.githubusercontent.com/103166380/169741301-31ef023d-a4f6-4cff-9d60-7d4b8d6504df.png)

- My implementation

![image](https://user-images.githubusercontent.com/103166380/169744842-7620682c-f49b-4375-ba18-56b94ff44379.png)

- Implementation reviewed in Week 7

![image](https://user-images.githubusercontent.com/103166380/169748011-555f4151-6fc5-47ae-bb62-4fe4d56583b5.png)

- Small change (<10 lines)? Yes

As long as there are an even number of brackets, the link in the parentheses should be printed and another edge case to not include the parentheses within the link until the last parentheses.

## Snippet 3
```
[this title text is really long and takes up more than 
one line

and has some line breaks](
    https://www.twitter.com
)

[this title text is really long and takes up more than 
one line](
https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule
)


[this link doesn't have a closing parenthesis](github.com

And there's still some more text after that.

[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/



)

And then there's more text
```
- markdown-parse should produce:

https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule

- Code for how I turned it into a test in MarkdownParseTest.java

![image](https://user-images.githubusercontent.com/103166380/169741412-8f125d9a-a31e-4fb1-aac6-57cfa2988a4e.png)

- My implementation

![image](https://user-images.githubusercontent.com/103166380/169744929-12e4c060-7709-479b-809b-4b8b04a91094.png)

- Implementation reviewed in Week 7

![image](https://user-images.githubusercontent.com/103166380/169748048-a2d388f5-5547-4dff-bb0b-8fe26a152a58.png)

- Small change (<10 lines)? Yes

To check for line breaks after the open parentheses and close parentheses, and to not print the strings within the parentheses if these lins breaks exist.
