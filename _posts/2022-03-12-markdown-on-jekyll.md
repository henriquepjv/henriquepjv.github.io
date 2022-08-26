---
title: "Markdown no Jekyl"
subtitle: "Blocos de código top"
layout: posts
comments: true
related_image: /assets/img/markdown-top.png
---

<div class="row">
  <div class="col-sm-12 col-md-12">
    <div class="container">
      <img src="/assets/img/markdown-top.png" alt="git and jekyll" class="post-main-img w3-card w3-round">
    </div>

    <div class="container default-width mt-5 mb-3">
      <h2 class="main-titles blog-subtitle mb-3">Preocupação inicial</h2>
      <p>Um ponto que influência muito na qualidade de um post de tech, na minha
      opinião, são os blocos de códigos bem formatados e que também esteja fácil de
      copiar para a área de transferência.</p>
      <p markdown="1">Por esse motivo, procurei entender o que poderia ser usado para
    deixar os blocos deste site iguais ao [desse aqui](https://dev.to/hoverbaum/how-to-add-code-highlighting-to-your-devto-posts-2lp6) </p>


      <h2 class="main-titles blog-subtitle mb-3">Como funciona no Jekyll</h2>
      <p markdown="1">A partir do jekyll 3 ele já vem com o [Rogue](https://github.com/rouge-ruby/rouge) incorporado, que fica responsável por destacar os trechos de código de acordo com a linguagem informada (possui algo em torno de 100 linguagens).</p>
      <p>E como engine para entender e processar o markdown o Jekyll utiliza o kramdown que já vem por padrão configurado.</p>

      <h2 class="main-titles blog-subtitle mb-3">Ativando o Markdown</h2>
      <p markdown="1">Para "ativar" o markdown em uma página específica, verifique se ela possui a extensão `.md` e além disse podemos usar as seguintes configurações:</p>

      {% highlight ruby %}
      # de forma global no arquivo "_config.yml"
        kramdown:
          parse_block_html: true

      # Ou adicionar no inicio do arquivo .md
        {::options parse_block_html="true" /}

      # Ou adicionar markdown="1" em algum bloco html
        <article markdown="1"></article>

      {% endhighlight %}

      <h2 class="main-titles blog-subtitle mb-3">Hora de configurar o Rogue</h2>
      <p>Toda essa parte de cima foi para ativar o Markdown, porém ao utiliza-lo para destacar um trecho de código ele fica muito simples e ruim de ler.</p>
      <p markdown="1">Com isso vi que o Rogue possui alguns [templates](https://jwarby.github.io/jekyll-pygments-themes/languages/ruby.html) com CSS jã montados e com muitas opções disponíveis.</p>
      <p markdown="1">Escolhi o [monokai](https://github.com/henriquepjv/henriquepjv.github.io/blob/main/assets/stylesheets/monokai.css) e ainda customizei mais um pouco para ficar igual ao do `dev.to`</p>
      {% highlight css %}
        .highlight pre {
          background-color: #272822;
          border-radius: 7px;
          padding: 10px;
          width: 80%;
          margin: 0;
          overflow: auto;
        }
      {% endhighlight %}

      <br>

      <p>E para finalmente especificar o trecho de código que queremos destacar bastar utilizar esse padrão:</p>
      {% highlight ruby %}
        {{ "{%" }} highlight ruby %}
          # trecho que deverá aparecer formatado
            def soma(numero1, numero2)
              numero1 + numero2
            end
        {{ "{%" }} endhighlight %}
      {% endhighlight %}

      <h2 class="main-titles blog-subtitle mb-3">Impressão final</h2>
      <p>Tudo funcionou muito bem e fica fácil de configurar com apenas o que eu
    preciso. Lembrando que ainda podemos adicionar coisas como número de linhas,
    linguagem utilizada e melhorar o estilo.</p>
    </div>
  </div>
  <div class="col-sm-12 col-md-12">
    <div class="container default-width mt-5 mb-5">
      <h2 class="main-titles">Leia mais...</h2>
      {% include related_posts.html %}
    </div>
  </div>
</div>
