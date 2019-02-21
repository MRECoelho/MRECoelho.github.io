---
layout: default
---
{% for tag in site.tags %}
  <h1>{{ tag[0] }}</h1>
  <hr class="fat">
  <ul>
  {% for page in tag[1] %}
 
  {% assign link = site.url | append:page.url  %}





        <h2><strong><a href="{{ page.url }}">{{ page.title }}</a></strong></h2>
        {{ page.description }}<br>
        <span class="post-date"><strong>Date: </strong>{{ page.date | date: "%b %-d, %Y" }} | <strong>All tags: </strong>{%for ptag in page.tags%}<a href="{{ ptag | slugify | prepend: 'tag/' | relative_url }}">{{ptag}}</a>{% unless forloop.last %}<span class="sep">, </span>{% endunless %}{%endfor%} 
        | <strong>Read time: </strong> {{page.content.size | divided_by: 600}} minutes</span>






  {% endfor %}
  </ul>
{% endfor %}

