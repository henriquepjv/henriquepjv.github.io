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
      <ul class="without-style mt-5">
        {% for post in site.posts %}
          <a href="{{ post.url }}" class="without-decoration">
            <li class="list-item list-posts-width">
              <div class="row g-4 mt-3">
                <div class="col-sm-2 col-md-2" style="margin-top:10px;">
                  <img src="{{ post.related_image }}" class="" style="width:50px">
                </div>
                <div class="col-sm-10 col-md-10" style="margin-top:0px;">
                  <span class="w3-large">{{ post.title }}</span><br>
                  <span>{{ post.subtitle }}</span>
                </div>
              </div>
            </li>
          </a>
        {% endfor %}
      </ul>
    </div>
  </div>
</div>
