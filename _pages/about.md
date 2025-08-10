---
layout: about
title: About Me
permalink: /

profile:
  align: right
  image: wjh_pic_color.jpg
  image_circular: false # crops the image to make it circular
  more_info: >

news: true # includes a list of news items
selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page
---

I am a PhD student at [Monash University](https://www.monash.edu/), with a Master's degree from the [University of Electronic Science and Technology of China (UESTC)](https://www.uestc.edu.cn/), where I was supervised by Prof. [Guotai Wang](https://scholar.google.com.hk/citations?user=Z2sFN4EAAAAJ&hl=en) and Prof. [Shaoting Zhang](https://scholar.google.com.hk/citations?user=oiBMWK4AAAAJ&hl=en). I am a member of [HiLab](https://hilab.uestc.edu.cn/). 

I focus on post-training adaptation of medical AI models, ranging from lightweight deep learning networks to large-scale foundation models. My research explores domain adaptation, test-time training, and self-supervised learning to enhance the reasoning-time robustness and generalizability of visual, language, and multi-modal systems in real-world medical scenarios.

<!-- ===== Single-page sections (add to About page) ===== -->

<hr/>
<h2 id="cv">Curriculum Vitae</h2>
{% assign cv = site.data.cv %}
{% if cv %}
  <!-- Education -->
  {% if cv.education %}
  <h3>Education</h3>
  <ul>
  {% for ed in cv.education %}
    <li>
      <strong>{{ ed.degree | default: ed.title }}</strong>, {{ ed.institution | default: ed.organization }}
      {% if ed.location %} — {{ ed.location }}{% endif %}
      {% if ed.start or ed.end %} ({{ ed.start | default: ed.year }}{% if ed.end %} – {{ ed.end }}{% endif %}){% endif %}
      {% if ed.description %}<details><summary>More</summary><p>{{ ed.description }}</p></details>{% endif %}
    </li>
  {% endfor %}
  </ul>
  {% endif %}

  <!-- Experience -->
  {% if cv.experience %}
  <h3>Experience</h3>
  <ul>
  {% for ex in cv.experience %}
    <li>
      <strong>{{ ex.position | default: ex.title }}</strong>, {{ ex.organization | default: ex.company }}
      {% if ex.location %} — {{ ex.location }}{% endif %}
      {% if ex.start or ex.end %} ({{ ex.start }}{% if ex.end %} – {{ ex.end }}{% endif %}){% endif %}
      {% if ex.description %}<details><summary>More</summary><p>{{ ex.description }}</p></details>{% endif %}
    </li>
  {% endfor %}
  </ul>
  {% endif %}

  {% if cv.awards %}
  <h3>Awards & Honors</h3>
  <ul>
  {% for a in cv.awards %}
    <li><strong>{{ a.title }}</strong>{% if a.organization %}, {{ a.organization }}{% endif %}{% if a.year %} ({{ a.year }}){% endif %}{% if a.description %}: {{ a.description }}{% endif %}</li>
  {% endfor %}
  </ul>
  {% endif %}

  {% if cv.skills %}
  <h3>Skills</h3>
  <ul>
  {% for s in cv.skills %}
    <li><strong>{{ s.category }}</strong>: {{ s.tools | array_to_sentence_string }}</li>
  {% endfor %}
  </ul>
  {% endif %}
{% endif %}

<hr/>
<h2 id="publications">Selected Publications</h2>
{% bibliography --file papers --query @*[selected=true] %}

<p style="margin-top:1rem">
  <a href="{{ '/publications/' | relative_url }}">See all publications →</a>
</p>


<hr/>
<h2 id="projects">Projects</h2>
{% include projects.html %}

<hr/>
<h2 id="news">News</h2>
{% include news.html %}
