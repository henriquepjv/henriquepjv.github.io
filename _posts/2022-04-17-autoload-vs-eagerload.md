---
title: "Autoload VS Eagerload"
subtitle: "Como funciona no Rails"
layout: posts
comments: true
related_image: ./assets/img/autoload_vs_eagerload.png
---

<div class="container">
  <img src="/assets/img/autoload_vs_eagerload.png" alt="Autoload vs Eagerload" class="post-main-img w3-card w3-round">
</div>

<div class="container default-width mt-5 mb-5">
  <h2 class="main-titles blog-subtitle mb-3">Dúvida inicial</h2>
  <p markdown="1">Tenho visto muitas dúvidas sobre quando utilizar `require`
por exemplo em um controller ou como especificar no Rails para uma classe ser 
carregada automaticamente.</p>
  <p>Outro ponto importante é como conseguir testar 
o local de uma forma que também funcione em produção.</p>

  <h2 class="main-titles blog-subtitle mb-3">Como funciona no Rails</h2>
  <p markdown="1">Tudo o que estiver dentro do path `/app` será carregado automaticamente 
através do `autoload`.</p>
  <p markdown="1">Para versões mais novas do Rails podemos utilizar o [zeitwerk](https://edgeguides.rubyonrails.org/autoloading_and_reloading_constants.html)
 que carrega os arquivos de uma forma mais inteligente.</p>
  <p>Mas para versões mais antigas (anterior a 5) temos que tomar cuidado ao 
utilizar o autoload ou eagerload.</p>
  <p>Com isso geralmente temos que nos preocupar com essa parte quando 
for necessário carregar diferentes arquivos dentro do diretório /lib.</p>

  <h2 class="main-titles blog-subtitle mb-3">Comportamento dependente do ambiente</h2>
  <p>O ambiente de desenvolvimento tem um carregamento de arquivos diferente
 do de produção com isso fica complicado de testar caso não haja um ambiente de 
pré produção para testar se o carregamento está correto.</p>
  <p markdown="1">As duas opções para definir dentro de `config/application.rb` são:</p>
  {% highlight ruby %}
    config.autoload_paths << Rails.root.join('lib')
  {% endhighlight %}
  <p>Porém é necessário passar o path de cada arquivo.</p>

  {% highlight ruby %}
    config.eager_load_paths << Rails.root.join('lib')
  {% endhighlight %}
  <p>Que irá carregar tudo o que existe dentro de /lib</p>

  <h2 class="main-titles blog-subtitle mb-3">Como testar</h2>
  <p markdown="1">Uma forma de destar o carregamento de um arquivo em
desenvolvimento é executar o `RAILS_ENV=production rails c` e quando o console
carregar basta chamar o nome da classe ou módulo criado.</p>

  {% highlight ruby %}
    RAILS_ENV=production rails c
  {% endhighlight %}
</div>
