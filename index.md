---
layout: default
---

# Hi Ahmed

## Latest Blog Posts
{% assign sorted_posts = site.posts | sort: "name" | reverse %}
{% for post in sorted_posts limit: 15 %} 

### [{{ post.title }}]({{ post.url | relative_url }})
<small>{{ post.date | date: "%B %d, %Y" }}</small>

>
[Read more »]({{ post.url | relative_url }})

{% endfor %}

