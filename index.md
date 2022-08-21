---
layout: default
---

<!-- Main Img Section -->
<div class="intro-header"></div>
<!-- End Main Img Section -->

<!-- Posts Section -->
<div class="container pt-5">
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

<!-- About Section -->
<div class="container pt-5" id="about">
  <div class="row">
    <div class="col-sm-12 col-md-12">
      <h2 class="main-titles">Henrique Panham</h2>
      <hr style="width:300px" class="main-titles">
      <p>Bacharel em Sistemas de Informação pela Universidade Paulista.</p>
      <p>Atuo como desenvolvedor web e venho estudando e criando projetos com a linguagem Ruby, com o objetivo de me especializar. Tenho muito interesse em desenvolver projetos novos e desafiadores, assim me incentiva a resolver problemas e aumentar meu know-how.</p>
      <p>Conhecimentos práticos em desenvolvimento de aplicações com metodologias ágeis, utlizando sempre as melhores práticas como cobertura de testes (Rspec, TDD, Capybara), princípios SOLID, uso de repositório de dados(GitHub), docker, continuous integration(Semaphore) e Linux como SO. Desenvolvendo nas linguagens Ruby on Rails, CSS, HTML e Javascript.</p>
    </div>
  </div>
</div>

<div class="container pt-5" id="about">
  <div class="row">
    <div class="col-sm-12 col-md-12" style="width:75%;">
      <h2 class="main-titles">My Skills</h2>
      <hr style="width:250px" class="main-titles">

      <p class="mt-2">Beber café</p>
      <div class="progress">
        <div class="progress-bar bg-warning" role="progressbar" aria-label="Warning example" style="width: 100%" aria-valuenow="100" aria-valuemin="0" aria-valuemax="100"></div>
      </div>

      <p class="mt-4">Ruby on Rails</p>
      <div class="progress">
        <div class="progress-bar bg-warning" style="width:50%;" role="progressbar" aria-label="Warning example" style="width: 75%" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100"></div>
      </div>

      <p class="mt-4">CSS</p>
      <div class="progress">
        <div class="progress-bar bg-warning" style="width:50%;" role="progressbar" aria-label="Warning example" style="width: 50%" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100"></div>
      </div>

      <p class="mt-4">Piloto</p>
      <div class="progress" style="margin-bottom:1rem">
        <div class="progress-bar bg-warning" style="width:50%;" role="progressbar" aria-label="Warning example" style="width: 25%" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100"></div>
      </div>
    </div>
  </div>
</div>

<!-- End About Section -->

<!-- Contact Section -->
<div class="container pt-5 pb-5" id="contact">
  <div class="row">
    <div class="col-sm-12 col-md-12">
      <h2 class="w3-text-orange main-titles">Entre em contato</h2>
      <hr style="width:300px" class="main-titles">

      <div class="">
        <p><i class="fa fa-map-marker fa-fw"></i> Brasil, SP</p>
        <p><i class="fa fa-envelope fa-fw"> </i> Email: henriquepjv@hotmail.com</p>
      </div>

      <form action="https://formspree.io/f/mjvlvevw" method="POST" class="pt-3">
        <p><input class="p-4 input-without-decoration contact-form" type="text" placeholder="Nome" required name="_name"></p>
        <p><input class="p-4 input-without-decoration contact-form" type="text" placeholder="Email" required name="_replyto"></p>
        <p><input class="p-4 input-without-decoration contact-form" type="text" placeholder="Assunto" required name="_subject"></p>
        <p><input class="p-4 input-without-decoration contact-form" type="text" placeholder="Mensagem" required name="_message"></p>
        <button class="btn btn-secondary mt-4" type="submit">
          <i class="fa fa-paper-plane"></i> Enviar
        </button>
      </form>
    </div>
  </div>
</div>
<!-- End Contact Section -->
