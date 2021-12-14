---
layout: default
---

<!-- Main Img Section -->

<div class="intro-header">
  <div class="w3-container">
    <div class="w3-row">
      <div class="col-lg-12">
      </div>
    </div>
  </div>
</div>

<!-- End Main Img Section -->

<!-- Posts Section -->
<div class="w3-content w3-justify w3-text-grey w3-padding-64" id="posts">
  <h2 class="w3-text-orange">Posts</h2>
  <hr style="width:200px" class="w3-opacity">

  <div class="w3-third">
    <ul class="w3-ul w3-hoverable">
      {% for post in site.posts %}
        <a href="{{ post.url }}">
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

<!-- About Section -->
<div class="w3-content w3-justify w3-text-grey w3-padding-64" id="about">
  <h2 class="w3-text-orange">Henrique Panham</h2>
  <hr style="width:200px" class="w3-opacity">
  <p>Bacharel em Sistemas de Informação pela Universidade Paulista.</p>
  <p>Atuo como desenvolvedor web e venho estudando e criando projetos com a linguagem Ruby, com o objetivo de me especializar. Tenho muito interesse em desenvolver projetos novos e desafiadores, assim me incentiva a resolver problemas e aumentar meu know-how.</p>
  <p>Conhecimentos práticos em desenvolvimento de aplicações com metodologias ágeis, utlizando sempre as melhores práticas como cobertura de testes (Rspec, TDD, Capybara), princípios SOLID, uso de repositório de dados(GitHub), docker, continuous integration(Semaphore) e Linux como SO. Desenvolvendo nas linguagens Ruby on Rails, CSS, HTML e Javascript.</p>

  <h3 class="w3-padding-16 w3-text-orange">My Skills</h3>
  <p class="w3-wide">Beber café</p>
  <div class="w3-white">
    <div class="w3-dark-grey" style="height:28px;width:95%"></div>
  </div>
  <p class="w3-wide">Ruby on Rails</p>
  <div class="w3-white">
    <div class="w3-dark-grey" style="height:28px;width:75%"></div>
  </div>
  <p class="w3-wide">CSS</p>
  <div class="w3-white">
    <div class="w3-dark-grey" style="height:28px;width:55%"></div>
  </div>
  <p class="w3-wide">Cantor</p>
  <div class="w3-white">
    <div class="w3-dark-grey" style="height:28px;width:5%"></div>
  </div>
  <!-- End About Section -->
</div>

<!-- Contact Section -->
<div class="w3-padding-64 w3-content w3-text-black" id="contact">
  <h2 class="w3-text-orange">Entre em contato</h2>
  <hr style="width:200px" class="w3-opacity">

  <div class="w3-section">
    <p><i class="fa fa-map-marker fa-fw w3-text-dark-gray w3-xxlarge w3-margin-right"></i> Brasil, SP</p>
    <p><i class="fa fa-envelope fa-fw w3-text-dark-gray w3-xxlarge w3-margin-right"> </i> Email: henriquepjv@hotmail.com</p>
  </div><br>
  <p>Entre em contato:</p>

  <form action="https://formspree.io/f/mjvlvevw" method="POST">
    <p><input class="w3-input w3-padding-16" type="text" placeholder="Nome" required name="_name"></p>
    <p><input class="w3-input w3-padding-16" type="text" placeholder="Email" required name="_replyto"></p>
    <p><input class="w3-input w3-padding-16" type="text" placeholder="Assunto" required name="_subject"></p>
    <p><input class="w3-input w3-padding-16" type="text" placeholder="Mensagem" required name="_message"></p>
    <p>
      <button class="w3-button w3-light-grey w3-padding-large" type="submit">
        <i class="fa fa-paper-plane"></i> Enviar
      </button>
    </p>
  </form>
<!-- End Contact Section -->
</div>

