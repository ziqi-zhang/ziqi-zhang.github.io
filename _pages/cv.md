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
  {% assign citation_parts = post.citation | split: ". " %}
  {% assign authors = citation_parts[0] %}
  <li>[{{ post.venue }}] {{ authors }}. {{ post.title }}.{% if post.paperurl and post.paperurl != "" %} <a href="{{ post.paperurl }}">[paper]</a>{% else %} <a href="{{ post.url }}">[details]</a>{% endif %}</li>
{% endfor %}
{% unless current_year == "" %}
  </ul>
{% endunless %}

Talks
======
<ul>
{% for post in site.talks reversed %}
  <li>{{ post.date | date: "%Y-%m-%d" }} — {{ post.title }}{% if post.venue %}, {{ post.venue }}{% endif %}{% if post.link %} <a href="{{ post.link }}">[link]</a>{% else %} <a href="{{ post.url }}">[details]</a>{% endif %}</li>
{% endfor %}
</ul>

Teaching
======
Please see my [teaching page](/teaching/) for updates.
