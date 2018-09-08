---
#
# Here you can change the text shown in the Home page before the Latest Posts section.
#
# Edit jekyll-theme-simple-blog's home layout in _layouts instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
#
layout: home
permalink: /index.html
header:
  image: /assets/img/home-header.jpg
tagline: > # this means to ignore newlines until "repository:"
  
excerpt: >
  안드로이드 개발자...
repository:
  is_project_page: false
  show_downloads: false
  # repository_url: https://gitlab.com/lorepirri/jekyll-theme-simple-blog
  # zip_url: https://gitlab.com/lorepirri/jekyll-theme-simple-blog/repository/master/archive.zip
  # tar_url: https://gitlab.com/lorepirri/jekyll-theme-simple-blog/repository/master/archive.tar.gz  
ref: home
lang: kr
---

<h1>Recent Posts</h1>
<div>&nbsp;</div>
{% include list-category-posts.html lang=page.lang category="articles" max_posts=3 max_post_tags=3 %}

---

<h1>Projects</h1>
<div>&nbsp;</div>
{% include list-category-posts.html lang=page.lang category="projects" max_posts=3 max_post_tags=3 %}
