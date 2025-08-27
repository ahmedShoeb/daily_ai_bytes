---
layout: default
---

# Hi Ahmed

## Latest Blog Posts
{% assign sorted_posts = site.posts | sort: "name" %}
{% assign posts_per_page = 10 %}
{% assign page_num = page.page_num | default: 1 %}
{% assign start = posts_per_page | times: page_num | minus: posts_per_page %}
{% assign end = posts_per_page | times: page_num %}
{% for post in paginator.posts %}
  {% if forloop.index0 >= start and forloop.index0 < end %}
### [{{ post.title }}]({{ post.url | relative_url }})
<small>{{ post.date | date: "%B %d, %Y" }}</small>

>
[Read more »]({{ post.url | relative_url }})

  {% endif %}
{% endfor %}

<!-- Simple pagination links -->
<div class="pagination">
  {% if start > 0 %}
    <a href="/page{{ page_num | minus: 1 }}/">&laquo; Previous</a>
  {% endif %}
  {% if end < sorted_posts.size %}
    <a href="/page{{ page_num | plus: 1 }}/">Next &raquo;</a>
  {% endif %}
</div>

