---
layout: default
---

{% for post in site.posts %}
{% capture nowunix %}{{'now' | date: '%s'}}{% endcapture %}
{% capture posttime %}{{post.date | date: '%s'}}{% endcapture %}
  <article>       
        <div class="article-head">
        <!--Added this restriction to be a bit selective about the links that show up-->
        <font color="grey">{{ post.date | date: "%Y" }}</font>
        {% if post.details %}
        <a href="{{ site.url }}{{ post.url }}">'{{ post.paper }}'</a> 
        {% else %}
        '{{ post.paper }}'
        {% endif %}
        <!--End of the temporary restriction-->
        <p>
        {% if posttime > nowunix %} <sup><i class="fa fa-bullseye"><small> upcoming</small></i></sup> {% else %} {% endif %}
        <sup><i class="fa fa-calendar"><small> {{ post.date | date: "%b %d" }}</small></i></sup>
        <sup><i class="fa fa-map-marker"><small> {{ post.where }}</small></i></sup>
        </p>
        </div>
    </article>
    {% if forloop.last %}{% else %}{% endif %}
{% endfor %}
