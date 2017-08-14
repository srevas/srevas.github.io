---
layout: default
title:  "Filmography"
date:   2001-12-25 00:00:00
tags: music filmography
categories: pages
linktitle: "filmography"
---

## Filmography

<table>
<tr>
<td style="width:34px;background:#f0f0f0;"><h4>Year</h4></td>
<td style="width:205px;background:#f0f0f0;"><h4>Title</h4></td>
<td style="width:16px;background:#f0f0f0;"><h4>Language</h4></td>
<td style="width:151px;background:#f0f0f0;"><h4>Production house</h4></td>
<td style="width:16px;background:#f0f0f0;"><h4>Links</h4></td>
<td style="background:#f0f0f0;"><h4>Credits</h4></td>
</tr>


{% for f in site.data.filmography %}

<tr>

<td>{{ f.year }}</td>
<td>{{ f.title }}</td>
<td>{{ f.language }}</td>
<td><a href="{{ f.productionurl }}">{{ f.production }}</a></td>

<td>
{% if f.song %}
<a href="{{ f.song }}">Song</a>
{% endif %}

{% if f.imdb %}
<a href="{{ f.imdb }}">IMDB</a>
{% endif %}

{% if f.movie %}
<a href="{{ f.movie }}">Movie</a>
{% endif %}

{% if f.teaser %}
<a href="{{ f.teaser }}">Teaser</a>
{% endif %}

{% if f.ost %}
<a href="{{ f.ost }}">Soundtrack</a>
{% endif %}

</td>
<td>{{ f.credits }}</td>

</tr>

{% endfor %}

</table>
<br />
