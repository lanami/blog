---
layout: page
title: Читаю
---

<ul class="post-list">
	{% for post in site.categories.books %} 
 	<li>
 		<a href="{{ site.url }}{{ post.url }}">{{ post.title }} <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time></span>{% if post.tldr %} <span class="excerpt">{{ post.tldr | remove: '\[ ... \]' | remove: '\( ... \)' | markdownify | strip_html | strip_newlines | escape_once }}</span>{% endif %}</a>
 	</li>
	{% endfor %}
</ul>

<ul class="post-list">
	{% for book in site.data.shelf %} 
 	<li>
 		<span class="book-title">{{ book.title }}</span> by <span class="book-author">{{ book.author }}</span><a href="http://asin.info/a/{{book.asin}}">http://asin.info/a/{{book.asin}}</a>
 	</li>
	{% endfor %}
</ul>