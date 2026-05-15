---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Profile
======
Postdoctoral researcher at the University of Illinois Urbana-Champaign (UIUC), working on AI security, trusted AI systems, software engineering, and software security.

Education
======
* Ph.D. in Computer Science, Peking University, 2018 - 2023
* B.E. in Computer Science, Peking University, 2014 - 2018

Appointments
======
* Postdoctoral Researcher, University of Illinois Urbana-Champaign

Research Areas
======
* Trusted AI and AI Security
* Trusted Execution Environments (SGX, TDX, TrustZone)
* AI4SE and SE4AI
* Software and Systems Security

Publications
======
{% assign current_year = "" %}
{% for post in site.publications reversed %}
  {% assign post_year = post.date | date: "%Y" %}
  {% if post_year != current_year %}
    {% unless current_year == "" %}
      </ul>
    {% endunless %}
    <h3>{{ post_year }}</h3>
    <ul>
    {% assign current_year = post_year %}
  {% endif %}
  {% assign authors = "" %}
  {% if post.authors %}
    {% assign authors = post.authors %}
  {% elsif post.citation and post.title and post.citation contains post.title %}
    {% assign citation_before_title = post.citation | split: post.title | first | strip %}
    {% assign authors = citation_before_title %}
  {% elsif post.citation and post.citation contains ". " %}
    {% assign citation_parts = post.citation | split: ". " %}
    {% assign authors = citation_parts[0] %}
  {% elsif post.citation %}
    {% assign authors = post.citation %}
  {% endif %}
  {% assign title_last_char = post.title | slice: -1, 1 %}
  {% assign title_suffix = "." %}
  {% if title_last_char == "." or title_last_char == "!" or title_last_char == "?" %}
    {% assign title_suffix = "" %}
  {% endif %}
  {% if post.paperurl and post.paperurl != "" %}
    {% assign publication_link = post.paperurl %}
    {% assign publication_link_text = "[paper]" %}
  {% else %}
    {% assign publication_link = post.url %}
    {% assign publication_link_text = "[details]" %}
  {% endif %}
  <li>
    [{{ post.venue }}]
    {% if authors != "" %}{{ authors }} {% endif %}
    {{ post.title }}{{ title_suffix }}
    <a href="{{ publication_link }}">{{ publication_link_text }}</a>
  </li>
{% endfor %}
{% unless current_year == "" %}
  </ul>
{% endunless %}

Talks
======
<ul>
{% for post in site.talks reversed %}
  {% if post.link %}
    {% assign talk_link = post.link %}
    {% assign talk_link_text = "[link]" %}
  {% else %}
    {% assign talk_link = post.url %}
    {% assign talk_link_text = "[details]" %}
  {% endif %}
  <li>
    {{ post.date | date: "%Y-%m-%d" }} — {{ post.title }}{% if post.venue %}, {{ post.venue }}{% endif %}
    <a href="{{ talk_link }}">{{ talk_link_text }}</a>
  </li>
{% endfor %}
</ul>

Teaching
======
Please see my [teaching page](/teaching/) for updates.
