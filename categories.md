---
layout: default
---
{% for tag in site.tags %}
  <h2>{{ tag[0] }}</h2>
  <ul>
  {% for page in tag[1] %}
 
  {% assign link = site.url | append:page.url  %}


  <a href="{{link}}">{{page.title}}</a><br>


  {% endfor %}
  </ul>
{% endfor %}

