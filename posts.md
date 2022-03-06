---
layout: posts
---

<!-- Posts Section -->
<div class="w3-content w3-justify w3-text-grey w3-padding-64" id="posts">
  <h2 class="w3-text-orange">Posts</h2>
  <hr style="width:200px" class="w3-opacity">
  <div class="w3-third">
    <ul class="w3-ul w3-hoverable">
      {% for post in site.posts %}
        <a href="{{ post.url }}" class="without-decoration">
          <li class="w3-padding-16">
            <img src="{{ post.related_image }}" class="w3-left w3-margin-right" style="width:50px">
            <span class="w3-large">{{ post.title }}</span><br>
            <span>{{ post.subtitle }}</span>
          </li>
        </a>
      {% endfor %}
    </ul>
  </div>
</div>
