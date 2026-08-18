---
layout: archive
title: "Curriculum Vitae"
permalink: /cv/
author_profile: true
---

[Download the full CV (PDF)](/files/Cai_CV.pdf){: .btn .btn--primary}

Education
======
* **PhD, Business Administration** (concentration in Real Estate) — Georgia State University, 2021–2027 (expected)
* **MSc, Business and Finance** — University of Warwick, 2019–2020
* **BA, Accounting** — Hong Kong Baptist University, 2015–2019

Research interests
======
Household Finance · Mortgages · Urban Economics · Commercial Real Estate · Generative AI

Publications
======
{% assign papers = site.publications | sort: 'date' | reverse %}
{% for p in papers %}{% if p.category == 'manuscripts' %}
**{{ p.title }}**<br>
{{ p.authors }} · *{{ p.status }}*<br>
<span style="opacity:.8">{{ p.excerpt }}</span>
{% endif %}{% endfor %}

Working papers
======
{% for p in papers %}{% if p.category == 'jobmarket' or p.category == 'workingpapers' %}
**{{ p.title }}**{% if p.category == 'jobmarket' %} — *Job Market Paper*{% endif %}<br>
{{ p.authors }}{% if p.status contains 'under revision' %} · *under revision*{% endif %}<br>
<span style="opacity:.8">{{ p.excerpt }}</span>
{% endif %}{% endfor %}

Full abstracts for all papers are on the [Research](/publications/) page.

Teaching
======
Instructor for four undergraduate real estate courses at Georgia State University
(Market Analysis, Investments, Finance, Asset Management), 2024–2026, with a mean student
rating of **4.79 / 5.00**. Teaching assistant for Real Estate Principles at Georgia State
University, 2022–2024, and Corporate Finance at BNU–HKBU United International College, 2020.
Course-by-course evaluations are on the [Teaching](/teaching/) page.

Conference presentations
======
AREUEA–ASSA, Cambridge Real Estate Finance and Investment Symposium, ARES, JRER/UCF, and
the Homer Hoyt Institute, 2026–2027. Full list with dates and papers is on the
[Presentations](/talks/) page.

Honors, fellowships, and awards
======
* GSU Graduate Teaching Assistant Teaching Excellence Award, 2026
* ARES Doctoral Travel Grant, 2026
* RERI Student Stipend Award, 2024
* Wolverton Doctoral Award, 2024
* HKBU Scholastic Awards, 2019
* HKICPA Qualification Program Scholarship, 2018
* First-Class Scholarship, 2016, 2017, 2018

Service
======
* Referee, *Journal of Commodity Markets*, 2025
* Organizer, GSU Finance PhD Meeting Series, 2024–25

Software and data
======
**Software** — Stata · SAS · Python · ArcGIS · LaTeX

**Data** — Revelio Labs LinkedIn · CoreLogic housing transactions · ATTOM housing
transactions · Zillow ZTRAX · HMDA · MLS · Fannie Mae and Freddie Mac loan performance ·
CoStar · Cook County (IL) property tax assessment records

Additional
======
**Languages** — Chinese (native), English (professional)

**Volunteer** — Georgia Aquarium
