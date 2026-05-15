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
<ul>
{% for post in site.publications reversed %}
  {% include archive-single-cv.html %}
{% endfor %}
</ul>

Talks
======
<ul>
{% for post in site.talks reversed %}
  {% include archive-single-talk-cv.html %}
{% endfor %}
</ul>

Teaching
======
Please see my [teaching page](/teaching/) for updates.
