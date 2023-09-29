
menu-position: 9
title: Blog
---
## Archive

<!--%
from datetime import datetime
posts = [p for p in pages if "post" in p] # get all blog post pages
posts.sort(key=lambda p: p.get("date"), reverse=True) # sort post pages by date
for p in posts:
    date = datetime.strptime(p.date, "%Y-%m-%d").strftime("%Y %B %d")
    print("  * **[%s](%s)** — %s" % (p.post, p.url, date)) # markdown list item
%-->