---
layout: default
---

<div class="upcoming"><sup><small><i class="fa fa-asterisk"> Upcoming</i></small></sup></div>
{% for post in site.posts %}
{% capture nowunix %}{{'now' | date: '%s'}}{% endcapture %}
{% capture posttime %}{{post.date | date: '%s'}}{% endcapture %}    
<article> 
            <div class="article-head">
                {% if post.details %}
                    <h6><a href="{{ site.url }}{{ post.url }}">'{{ post.paper }}'</a>
                {% else %}
                    <h6>'{{ post.paper }}'
                {% endif %}
                {% if posttime > nowunix %} 
                    <sup><small><i class="fa fa-asterisk"></i></small></sup>
                {% endif %}
                </h6>
                <div class="dateline"> 
                    <p class="date"><sup><small> {{ post.date | date: "%A, %B %-d, %Y" }} </small></sup></p> 
                    <p class="datediv"><sup><small> > </small></sup></p>    
                    {% if post.where %}
                        <p class="date"><sup><small> {{ post.where }}</small></sup></p>
                    {% endif %}
                    {% if post.city %}
                        <p class="datediv"><sup><small> in</small></sup></p>    
                        <p class="date"><sup><small> {{ post.city }}</small></sup></p>
                    {% endif %}
                </div>
            </div>
</article>
{% if forloop.last %}{% else %}{% endif %}
{% endfor %}
