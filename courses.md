---
layout: default
permalink: /courses/
---

## Courses

### Linear Algebra MIT 18.06SC (OCW)

{% for category in site.categories %}
  {% if category[0] == "Mathematics" %}
  <h3>{{ category[0] }}</h3>
  <ul>
    {% for post in category[1] %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
  {% endif %}
{% endfor %}
