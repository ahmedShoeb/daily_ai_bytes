---
layout: default
---

# Hi Ahmed

## Latest Blog Posts
{% for post in site.posts limit: 20 %} 

### [{{ post.title }}]({{ post.url | relative_url }})
<small>{{ post.date | date: "%B %d, %Y" }}</small>

>
[Read more »]({{ post.url | relative_url }})

{% endfor %}

