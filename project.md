---
layout: default
title: Project
---

<div id="project">
  <h1 class="pageTitle">Project</h1>

  <div class = "project">
    <li class="project_item">
      <a href="{{ post.url | prepend: site.baseurl }}">
        <img class="project_img" src="{{ '/assets/img/helloseoul.png' | prepend: site.baseurl }}">
        <p class="project_title">설로</p>
        <div class="project_info">
          <h1 class="project_slogan">우리는 서울로 갑니다, 설로</h1>
          <p class="project_summary">Open API를 이용한 서울시 관광 어플</p>
          <p class="project_body">TestTestTestTestTestTestTestTest</p>
        </div>
    </li>
  </div>

  <ul class="posts noList">
    {% for post in paginator.posts %}
      <li>
        <span class="date">{{ post.date | date: '%B %d, %Y' }}</span>
        <h3><a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h3>
        <p>{% if post.description %}{{ post.description }}{% else %}{{ post.excerpt | strip_html }}{% endif %}</p>
      </li>
    {% endfor %}
  </ul>
  <!-- Pagination links -->
  <div class="pagination">
    {% if paginator.previous_page %}
      <a href="{{ paginator.previous_page_path | prepend: site.baseurl }}" class="previous button__outline">Newer Posts</a> 
    {% endif %}
    {% if paginator.next_page %}
      <a href="{{ paginator.next_page_path | prepend: site.baseurl }}" class="next button__outline">Older Posts</a>
    {% endif %}
  </div>
</div>