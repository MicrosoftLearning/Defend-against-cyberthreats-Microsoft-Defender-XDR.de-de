---
title: Übungsanweisungen
permalink: index.html
layout: home
---

# Übungen

Auf dieser Seite sind Übungen aufgeführt, die mit Microsoft-Qualifizierungsinhalten in [Microsoft Learn](https://learn.microsoft.com) verknüpft sind

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %} {% for activity in labs  %}
- [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) {% endfor %}

