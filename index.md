---
layout: default
---



[Link to another page](./another-page.html).


# Hi Ahmed

## Latest Blog Posts
{% for post in site.posts limit: 5 %} 

[{{ post.title }}]({{ post.url | relative_url }})
<small>{{ post.date | date: "%B %d, %Y" }}</small>

{{ post.excerpt | strip_html | truncatewords: 50 }}
[Read more »]({{ post.url | relative_url }})

{% endfor %}

