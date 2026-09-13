---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

{% assign latest = site.posts.first %}
<article>
  <h1>{{ latest.title }}</h1>
  <p>{{ latest.date | date: "%-d %B %Y" }}</p>
  {{ latest.content }}
</article>
