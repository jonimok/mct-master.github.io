---
layout: page
title: DSP Workshop
permalink: /dsp/
---

The blog posts of this section relate to the workshop **DSP** in the course **MCT4000 Introduction to Music, Communication and Technology**. The aim of the course is to explore basic signal processing techniques, physical models and waveguides, implement these techniques for practical experimentation in own projects, and combine as well as creatively utilize these tools for new applications.

<br />

{%- if site.posts.size > 0 -%}
  <!-- <h2 class="post-list-heading">{{ page.list_title | default: "Posts" }}</h2> -->
  <ul class="post-list">
    {%- for post in site.categories.DSP -%}
    <li>
      {%- if post.image -%}
      <img src="{{ post.image | prepend: site.baseurl }}" alt="{{ post.title }}" title="{{ post.title }}">
      {%- endif -%}
      {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
      <span class="post-meta">{{ post.date | date: date_format }}</span>
      <span class="post-meta">• {{ post.author }}</span>
      <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">
          {{ post.title | escape }}
        </a>
      </h3>
      {%- if site.show_excerpts -%}
        {{ post.excerpt }}
      {%- endif -%}
      <h4>
      <strong><a href="{{ post.url | relative_url }}">
        »Read more
      </a></strong>
      </h4>
    </li>
    {%- endfor -%}
  </ul>
  {%- endif -%}