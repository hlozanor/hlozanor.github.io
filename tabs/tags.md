---
title: Tags
type: tags
# All the Tags of posts.
# v2.0
# https://github.com/cotes2020/jekyll-theme-chirpy
# © 2017-2019 Cotes Chung
# MIT License
---

{% comment %}
  'site.tags' looks like a Map, e.g. site.tags.MyTag.[ Post0, Post1, ... ]
  Print the {{ site.tags }} will help you to understand it.
{% endcomment %}
<div id="tags" class="d-flex flex-wrap ml-xl-2 mr-xl-2">
{% assign tags = "" | split: "" %}
{% for t in site.tags %}
  {% assign tags = tags | push: t[0] %}
{% endfor %}

{% assign sorted_tags = tags | sort_natural %}

{% for t in sorted_tags %}
  <div>
    <a class="tag" href="{{ site.baseurl }}/tags/{{ t | replace: ' ', '-' | downcase | url_encode }}/">{{ t }}<span class="text-muted">{{ site.tags[t].size }}</span></a>
  </div>
{% endfor %}

</div>
<br>


{% comment %}
  Test to add the list of posts with specific tags
{% endcomment %}

{% assign sorted_tags = tags | sort_natural %}



  <div id="archives" class="pl-xl-2">
            {% for tag in sorted_tags %}
                <span class="lead"> id="{{tag}}">{{tag}}</span>
                <ul class="list-unstyled">
                    {% for post in site.posts %}
                        {% for otag in post.tags %}
                            {% if tag == otag %}
                                <li class="alink"><a href="{{ post.url }}" class="red-link">{{ post.title }}</a></li>
                            {% endif %}
                        {% endfor %}
                    {% endfor %}
                </ul>
            {% endfor %}



  </div>





