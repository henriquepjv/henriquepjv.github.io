---
title: "exec_query VS find_by_sql"
subtitle: "Funcionamento no Rails"
layout: posts
comments: true
published: false
related_image: /assets/img/git_and_jekyll.jpg
---

- Explicar se os dois vem do ActiveRecord
- find_by_sql é bom pela praticidade
- exec_query é bom em performance
- https://blog.lunarcollective.co/writing-sql-in-rails-speed-vs-convenience-e5d8c0ec25d9
- Bonus -> exec_query em uma transaction nao cria uma nova conexao com o banco
