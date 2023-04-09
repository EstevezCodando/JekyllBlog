---
title: "Criando Blog Jekyll no Windows Pt2"
date: 2023-04-08T16:34:30-04:00
categories:
  - documentacao
tags:
  - blog
  - configuração
  - windows
  - Jekyll
  - update
  - tutorial
---

Ao executar o comando
  ```powershell
 C:\> jekyll new nome-do-blog
```
o bundler realizou as instalação de todas as dependencias que serão utilizadas.
O blog inicial é gerado com base no tema **minima**, para observar onde a gem está instalada e o que tem nela podemos executar:
  ```powershell
 C:\> bundle show minima
```  

Com isso veremos o caminho em que a gem contendo o tema do blog está localizada, permitindo-nos configurar o layout e outros aspectos do blog.
- _includes
- _layouts
- _sass
- assets

Ao copiar esses arquivos para a pasta do blog, podemos personalizá-los de acordo com nossas necessidades:

- **_includes**  
  Os arquivos "_includes" são partes/pedaços do blog que podem ser chamados e replicados em todas as páginas. Esses arquivos incluem elementos como cabeçalho, rodapé, entre outros.

- **_layouts**  
  Os "_layouts" definem as estruturas básicas das páginas do blog, determinando como elas são organizadas visualmente.

- **_sass**  
  A pasta "_sass" contém os arquivos de estilo do blog. Ao executar o comando `jekyll build`, os arquivos SASS são automaticamente convertidos em arquivos CSS.

- **assets**  
  A pasta "assets" armazena os arquivos de estilo e CSS que podem ser modificados para alterar a aparência do blog.




[minimalmistakes]: https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide
[githubMinmalCreate]: https://github.com/mmistakes/mm-github-pages-starter/generate
[Ruby-Devkit]: https://rubyinstaller.org/downloads/ 
[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
