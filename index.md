---
layout: page
title: Welcome to my personal blog where I post about stuff I do
tagline: Supporting tagline
---

Nice that you're here. This is my personal blog and I post about things I do and I am interested in. Not regularly. If you have any questions I am happy you get in touch with me. Please see the [get in touch page](pages/get_in_touch.html).

## Latest Post
{% for post in site.posts limit:1 %}
  [{{ post.title }}]({{ root_url }}{{ post.url }})
{% endfor %}
## Recent Posts
{% for post in site.posts offset:1 limit:4 %}
  [{{ post.title }}]({{ root_url }}{{ post.url }})
{% endfor %}

## Work

After having had a very cool time at SinnerSchrader from May 2010 to December 2013, I am now working at [sum.cumo AG](http://sumcumo.com) with a great team. We are developing high traffic web portals especially for Swiss direct insurances and the German Toto Lotto societies.

## Apache CouchDB

I am a fan of CouchDB since 2008 when I heard the first talk about it. Since Oktober 2013 I am committer and in Feubruary I was invited to become a Apache CouchDB PMC member what I accepted with great hnour. 

I am actually working on the translation, documentation and marketing bits and have a lot of fun with a great team. If you're interested I invite you to visit [couchdb.org](http://couchdb.org)


