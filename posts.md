---
layout: posts
comments: false
---

<!-- Posts Section -->
<div class="container pt-5" id="posts">
  <div class="row g-4">
    <div class="col-sm-12 col-md-12">
      <h2 class="main-titles">Posts</h2>
      <hr style="width:150px" class="main-titles">
      <ul class="without-style">
        {% for post in site.posts %}
          <a href="{{ post.url }}" class="without-decoration">
            <li class="w3-padding-16 list-item list-post-width">
              <img src="{{ post.related_image }}" class="" style="width:50px">
              <span class="w3-large">{{ post.title }}</span><br>
              <span>{{ post.subtitle }}</span>
            </li>
          </a>
        {% endfor %}
      </ul>
    </div>
  </div>
</div>
