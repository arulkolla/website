

---
## {{ page["post"] }}

#### *Local man realizes that Markdown parsers actually parse Markdown*

*Posted on
<!--%
from datetime import datetime
print(datetime.strptime(page["date"], "%Y-%m-%d").strftime("%Y %B %d"))
%-->*

As you might know, this website is built on [Poole](https://hg.sr.ht/~obensonne/poole). Poole is a simple static site generator that lets you write your content in Markdown and it will be converted to HTML and served up as a static website. One benefit of this is that Markdown supports footnotes[^1], which are basically nice alternatives to slightly-more-invasive parentheticals.

As such, it only made sense that Poole would magically make footnotes work; for me, Poole was some mystical black box that took Markdown as input and creates a website as output. It didn't.

As it turns out, Poole is actually just a neat *package* for the inbuilt Python Markdown-to-HTML parser to work its magic under. Poole neatly wraps everything up in a bow, but it's the Python underneath doing the actual Markdown-to-HTML processing.[^2] I ended up ragequitting after a very long StackOverflow session[^3], only to come back a month later and decide to actually look into what Poole was doing.

It turns out Poole just outsources its work to the `markdown` package, which converts it to HTML.[^4] And the `footnotes` option was missing from this conversion. One change to line 613 fixes it:

    page.html = markdown.Markdown(extensions=['footnotes']).convert(out)

As they say, web development is web development.[^5]

[^1]: This is a footnote. Yay!

[^2]: I also thought Poole was magic for doing this in less than 1000 lines. Then I realized it used a Python library, and the magic disappeared.

[^3]: Unsurprisingly, there is little documentation for a ten-year-old static website generator.

[^4]: Actually, I then thought that `markdown` was the magical one, somehow turning Markdown into HTML through the magic of Python shenanigans. Then I realized that this is, like, what a Markdown parser does. Yes, I know, it seems so obvious in retrospect, but it took me one month to realize this. Oops.

[^5]: Nobody says this.