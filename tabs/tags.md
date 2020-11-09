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
    <a class="tag" href="#{{ t | downcase }}">{{ t }}<span class="text-muted">{{ site.tags[t].size }}</span></a>
  </div>
{% endfor %}

</div>
<br>
<hr>

{% comment %}
  Test to add the list of posts with specific tags
{% endcomment %}

{% assign sorted_tags = tags | sort_natural %}



  <div id="archives" class="pl-xl-2">
            {% for tag in sorted_tags %}
                <h3 id="{{tag}}"> <i class="fa fa-tag fa-fw text-muted"></i> {{tag}}</h3>
                              
                <ul class="post-content pl-0">
                    {% for post in site.posts %}
                        {% for otag in post.tags %}
                            {% if tag == otag %}
                                <li class="d-flex justify-content-between pl-md-3 pr-md-3"> <a href="{{ post.url }}" class="red-link">{{ post.title }}</a> <span class="dash flex-grow-1"></span> <span class="text-muted small">Aug 9, 2019</span> </li>
                            {% endif %}
                        {% endfor %}
                    {% endfor %}
                </ul>
            {% endfor %}



  </div>





