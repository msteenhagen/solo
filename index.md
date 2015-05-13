---
layout: default
---

{% for post in site.posts %}
{% capture nowunix %}{{'now' | date: '%s'}}{% endcapture %}
{% capture posttime %}{{post.date | date: '%s'}}{% endcapture %}
  <article>       
        <div class="article-head">
        <h3><a href="{{ site.url }}{{ post.url }}">{{ post.paper }}</a> 
            {% if posttime > nowunix %} <i class="fa fa-bullseye fa-border"> upcoming</i> {% else %} {% endif %}</h3>
        <p><i class="fa fa-calendar"><small> {{ post.date | date: "%b %d, %Y" }}</small></i></br>
        <i class="fa fa-map-marker"><small> {{ post.where }}</small></i></p>
        </div>
    </article>
    {% if forloop.last %}{% else %}{% endif %}
{% endfor %}