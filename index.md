---
layout: default
---

<!-- ## this is the index file -->


{% for post in site.posts %}

<article class='post'>
  <h1 class='post-title'>
    <a href="{{ site.path }}{{ post.url }}">
      {{ post.title }}
    </a>
  </h1>
  {{post.description}}
  <div class="post-date"><strong>Date: </strong>{{ post.date | date: "%b %-d, %Y" }} | <strong>Tags: </strong>{%for tag in post.tags%}<a href="{{ tag | slugify | prepend: 'tag/' | relative_url }}">{{tag}}</a>{% unless forloop.last %}<span class="sep">, </span>{% endunless %} 
  {%endfor%} |<strong>Read time: </strong> {{post.content.size | divided_by: 600}} minutes
  </div> 
  
</article>

{% endfor %}



