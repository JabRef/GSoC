---
# the default layout is 'page'
icon: fas fa-project-diagram
order: 5
title: Projects
---

{% assign project_posts = site.posts | where_exp: "item", "item.tags contains 'project-idea'" %}

{% for post in project_posts %}
  {% if post.tags contains 'size-small' %}
    {% assign size_score = 1 %}
  {% elsif post.tags contains 'size-medium' %}
    {% assign size_score = 2 %}
  {% elsif post.tags contains 'size-large' %}
    {% assign size_score = 3 %}
  {% else %}
    {% assign size_score = 9 %}
  {% endif %}
  {% capture post_with_score %}{{ size_score }}|{{ post.path }}{% endcapture %}
  {% if forloop.first %}
    {% assign sorted_post_strings = post_with_score %}
  {% else %}
    {% assign sorted_post_strings = sorted_post_strings | append: "," | append: post_with_score %}
  {% endif %}
{% endfor %}

{% assign sorted_post_strings = sorted_post_strings | split: "," | sort %}

{% for post_string in sorted_post_strings %}
{% assign post_path = post_string | split: "|" | last %}
{% assign post = site.posts | where: "path", post_path | first %}
### {{ post.title }}

{{ post.content }}

{% unless forloop.last %}
---
{% endunless %}
{% endfor %}
