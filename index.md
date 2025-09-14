---
layout: default
---

# Hi Ahmed

## Latest Blog Posts
{% if paginator.posts %}
  {% for post in paginator.posts %}
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
  {% endfor %}

  {% if paginator.total_pages > 1 %}
    <div class="pagination">
      {% if paginator.previous_page %}
        <a href="{{ paginator.previous_page_path }}">&laquo; Prev</a>
      {% endif %}

      {% for page in (1..paginator.total_pages) %}
        {% if page == paginator.page %}
          <span class="current">{{ page }}</span>
        {% elsif page == 1 %}
          <a href="/">{{ page }}</a>
        {% else %}
          <a href="{{ site.paginate_path | replace: ':num', page }}">{{ page }}</a>
        {% endif %}
      {% endfor %}

      {% if paginator.next_page %}
        <a href="{{ paginator.next_page_path }}">Next &raquo;</a>
      {% endif %}
    </div>
  {% endif %}
{% else %}
  <p>There are no posts to display.</p>
{% endif %}