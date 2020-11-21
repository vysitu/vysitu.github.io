---
layout: posts

# toc: true
# toc_label: "My Table of Contents"
# toc_icon: "cog"
---

an example of "contents"

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

## trying auto-toc also