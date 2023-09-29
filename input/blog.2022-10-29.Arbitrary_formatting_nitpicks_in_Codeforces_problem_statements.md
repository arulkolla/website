

---
## {{ page["post"] }}

#### *LaTeX pet peeves, but for CF*

*Posted on
<!--%
from datetime import datetime
print(datetime.strptime(page["date"], "%Y-%m-%d").strftime("%Y %B %d"))
%-->*

Codeforces has this [document](https://docs.google.com/document/u/0/d/e/2PACX-1vRhazTXxSdj7JEIC7dp-nOWcUFiY8bXi9lLju-k6vVMKf4IiBmweJoOAMI-ZEZxatXF08I9wMOQpMqC/pub) which you are supposedly supposed to follow when you create a round, but I don't think anyone does. Also, the document is quite dated, and there are a couple of new conventions that I think should be reflected. So here's my take on how to properly format things in statements. Note: these are just my personal opinions.[^1]

- **Common functions**: MEX, XOR, AND, OR should be written using `$~\mathsf{OP}~$` (for instance, $\mathsf{MEX}$, $\mathsf{XOR}$) if they are used only once or twice in the statement (for example, "the $\mathsf{MEX}$ of the array is $a$"). 
	- Otherwise, if they appear multiple times, it is okay to use $\oplus, \&, \mid$ for XOR, AND, OR respectively.[^2] 
	- MEX is a function, and not a binary operation, so it should never be abbreviated.
- **Strings**: there are two types of strings in a problem statement: those which are used for examples, and those which are part of the output format (for example, "output `YES` or `NO`").
	- In the former case, `$\texttt{string}$` should be used *in math mode!*[^3], like $\texttt{sample}$. Quotes surrounding the string should *not* be used.[^4]
	- In the latter case, `\t{string}` should be used outside of math mode. Quotes surrounding the string may be used, but it is recommended to omit them.
- **Input constraints**: these should be described line-by-line.
	- If a single line contains some constant number of integers, then they should be described like: "the only line of each test case contains two integers $x$ and $y$ ($1 \leq x \leq 10^9$; $1 \leq y \leq 10^{18}$)", with a semicolon between the constraints, if and only if the constraints on said variables are distinct.[^5]
	- Adding on, as few constraints as possible should be listed in the input format. For example, "$1 \leq x \leq 10^9$; $1 \leq y \leq x$" is bad, while "$1 \leq y \leq x \leq 10^9$" is good. The order of the variables in the constraint don't have to be in the same order as they are given in the input (but it is preferable).
- **Arrays**: only use square brackets and commas to denote arrays, like $[1, 2, 3]$. Never use parentheses $(1, 2, 3)$ or curly braces $\{1, 2, 3\}$.
- **Indexing**: by default arrays are $1$-indexed![^6]
- **Queries**: write queries of the form $1~~x~~y$ with `~~` between each pair of variables.
	- Interactive problems should use $?$ for queries and $!$ for answers as much as possible.[^7]

That's all I can think of for now, but consider this blog post very much living; as I see something pop up, I'll add it to this list!

[^1]: But I think it's better that *some* uniform style guide exists sooner rather than later. Hopefully this gets adapted in some sense.
[^2]: My personal opinion on this matter is that the traditional binary operations look quite bad, but I understand that $a_1~\mathsf{AND}~a_2~\mathsf{AND}~a_3~\mathsf{AND}~a_4$ can be daunting.
[^3]: The math mode looks much better for strings in examples, in my opinion. The font stands out enough to make it seem distinct from the rest of the statement. Also, it makes it easier to do things like underline and use color than `\t{}`.
[^4]: I don't like using quotes because of the clunky "without quotes" clause that needs to be included every time. Just omit them; the whole point of a different font is that the strings are already distinct enough from the rest of the text.
[^5]: I picked this up from [adedalic](https://codeforces.com/profile/adedalic). It's to distinguish from constraints like $1 \leq x, y \leq 10^9$.
[^6]: This is just standard on Codeforces, it seems (much to the chagrin of beginners, I presume).
[^7]: Plus, it makes the problem more exciting$!$
