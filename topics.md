---
layout: page
title: Topics
permalink: /topics/
---

## Categories

<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <h3 id="#{{ category_name | slugize }}">{{ category_name }}</h3>
    {% for post in site.categories[category_name] %}
      <article class="archive-item">
        <h4><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h4>
        <p class="post-meta">
          <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
        </p>
      </article>
    {% endfor %}
  </div>
{% endfor %}
</div>

## Tags

<div id="archives">
{% assign sorted_tags = site.tags | sort %}
{% for tag in sorted_tags %}
  <div class="archive-group">
    {% capture tag_name %}{{ tag | first }}{% endcapture %}
    <h3 id="#{{ tag_name | slugize }}">{{ tag_name }}</h3>
    {% for post in site.tags[tag_name] %}
      <article class="archive-item">
        <h4><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h4>
        <p class="post-meta">
          <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
        </p>
      </article>
    {% endfor %}
  </div>
{% endfor %}
</div>
