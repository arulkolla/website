
menu-position: 9
title: Blog
---
<!--%
from datetime import datetime
posts = [p for p in pages if "post" in p] # get all blog post pages
posts.sort(key=lambda p: p.get("date"), reverse=True) # sort post pages by date
datezero = datetime.strptime(posts[0].date, "%Y-%m-%d").strftime("%Y %B %d")
print( "<center><h4>Most recent post (%s):</h4></center>" % datezero)
print( "<center><h4>**[%s](%s)**</h4></center>" % (posts[0].post, posts[0].url))
print()
print( "#### Archive")
for p in posts:
    date = datetime.strptime(p.date, "%Y-%m-%d").strftime("%Y %B %d")
    print("  * **[%s](%s)** — %s" % (p.post, p.url, date)) # markdown list item
%-->