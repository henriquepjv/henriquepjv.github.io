---
title: "Hash With Indifferent Access"
subtitle: "Performance"
layout: posts
comments: true
related_image: /assets/img/rosca_maca.jpeg
---

<div class="row">
  <div class="col-sm-12 col-md-12">
    <div class="container">
      <img src="{{page.related_image}}" class="post-main-img w3-card w3-round">
    </div>

    <div class="container default-width mt-5 mb-3">
      <h2 class="main-titles blog-subtitle mb-3">{{page.title}}</h2>
      <p markdown="1">Utilizando o Ruby puro nós podemos utilizar uma classe
chamada Hash que será responsável por disponibilizar uma estrutura de
chave/valor.</p>
      {% highlight ruby %}
        hash = Hash.new
        hash[:banana] = 123  # chave do tipo symbol
        # { banana: 123 }

        hash = Hash.new
        hash["banana"] = 123  # chave do tipo string
        # "{ 'banana' => 123 }"
      {% endhighlight %}
      <p markdown="1">Porém a chave desse hash pode ser acessada ou criada de
duas maneiras, symbol `(:banana)` ou string `("banana")`. Com isso após ter
escolhido o tipo da chave do seu hash ele só poderá ser acessado por um valor
daquele tipo escolhido. Com isso podemos ter alguns erros inesperados ao
utilizar um hash.</p>
    </div>

    <div class="container default-width mt-5 mb-3">
      <h2 class="main-titles blog-subtitle mb-3">Ajuda no Rails</h2>
        <p markdown="1">Se você utiliza o framework Rails junto com o Ruby,
existe uma opção para evitar esse problema. O módulo `ActiveSupport` possui uma
classe para lidar com essa situação
`ActiveSupport::HashWithIndifferentAccess`.</p>
      {% highlight ruby %}
        hash = HashWithIndifferentAccess.new(banana: 123)
        # ou
        hash = Hash.new(banana: 123)
        hash.with_indifferent_access
        # Dessa forma será possível ler hash[:banana] ou hash['banana']
      {% endhighlight %}
    </div>

    <div class="container default-width mt-5 mb-3">
      <h2 class="main-titles blog-subtitle mb-3">Nem tudo são flores</h2>
        <p markdown="1">Uma coisa que nós sempre encontramos na programação
independente da linguagem ou framework são trade-offs. Sempre vamos ouvir que
não existe bala de prata para um determinado problema, ao usar uma abordagem nós
sempre temos que nos atentar ao lado bom e principalmente ao lado ruim.</p>
       <p markdown="1">Com isso, trazendo para esse caso do Hash, ele não é
indicado para ser usado a todo momento, pois por ser mais versátil ele irá
consumir mais processamento. Portanto será muito importante analisar o local que
o HashWithIndifferentAccess irá habitar e se ele é realmente necessário. Ou se
não seria melhor estabelecer um padrão de hash recebido por aquela classe.</p>
    </div>

    <div class="container default-width mt-5 mb-3">
      <h2 class="main-titles blog-subtitle mb-3">Benchmark</h2>
        <p markdown="1">Para não ficar muito abstrato, vou deixar o trecho de
código que utilizei para fazer esse estudo entre `Hash` e
`HashWithIndifferentAccess`</p>
      {% highlight ruby %}
        # Demorou @real=6.957362000001012 segundos
        Benchmark.measure do
          1_000_000.times do
            hash = HashWithIndifferentAccess.new(banana: 123, laranja: 321, maca: 333)
            hash.merge(pera: 222)
            hash.merge('uva' => 222)
          end
        end

        # Demorou @real=3.021720999997342 segundos
        Benchmark.measure do
          1_000_000.times do
            hash = Hash.new(banana: 123, laranja: 321, maca: 333)
            hash.merge(pera: 222)
            hash.merge(uva: 222)
          end
        end
      {% endhighlight %}
    </div>
  </div>
  <div class="col-sm-12 col-md-12">
    <div class="container default-width mt-5 mb-5">
      <h2 class="main-titles">Leia mais...</h2>
      {% include related_posts.html %}
    </div>
  </div>
</div>
