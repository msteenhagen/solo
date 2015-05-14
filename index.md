---
layout: default
---

{% for post in site.posts %}
{% capture nowunix %}{{'now' | date: '%s'}}{% endcapture %}
{% capture posttime %}{{post.date | date: '%s'}}{% endcapture %}
<article>       
        <div class="article-head">
            <font color="grey">{{ post.date | date: "%Y" }}</font>
            {% if post.details %}
                <a href="{{ site.url }}{{ post.url }}">'{{ post.paper }}'</a> 
            {% else %}
                '{{ post.paper }}'
            {% endif %}
            <p>
                {% if posttime > nowunix %} 
                        <sup><i class="fa fa-bullseye"><small> upcoming </small></i></sup>
                    {% else %} 
                {% endif %}
                <sup><i class="fa fa-calendar"><small> {{ post.date | date: "%b %d" }}</small></i></sup>
                {% if post.where %}
                    <sup><small> | {{ post.where }}</small></sup>
                {% endif %}
                {% if post.city %}
                    <sup><i class="fa fa-map-marker"><small> {{ post.city }}</small></i></sup>
                {% endif %}
            </p>
        </div>
</article>
{% if forloop.last %}{% else %}{% endif %}
{% endfor %}
