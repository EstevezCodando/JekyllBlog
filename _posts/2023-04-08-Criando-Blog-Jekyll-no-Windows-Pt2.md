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
## Estrutura Minima
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


## Iniciando o blog

Agora que todas as pastas estão organizadas, fica mais fácil realizar todas as configurações necessárias. Inicialmente, temos as seguintes pastas e arquivos na pasta do blog:

  - Gemfile
  - Gemfile.lock
  - _config.yml
  - _posts
  - about.md
  - index.md 
  - _includes
  - _layouts
  - _sass
  - assets  

Dentro desta pasta, abra o terminal (cmd) e execute o comando:

  ```powershell
 C:\blog\>  bundle exec jekyll build
```
O Bundle resolve diversas incompatibilidades e inconsistências que podem ocorrer, checando os dados das gems do Gemfile e _config.yml. Com isso, ele gera a estrutura completa do site.

Para visualizar o site localmente, basta executar o comando:

  ```powershell
 C:\blog\>  bundle jekyll serve
```
Se tudo correr bem, será disponibilizado um caminho semelhante a:
http://127.0.0.1:4000/

Caso contrário, é provável que exista alguma gem faltando ou inconsistência na configuração.
verifique a mensagem que ele enviou, no caso da gem adicione-a ao arquivo gemfile.
exemplo
```
source "https://rubygems.org"

gem "github-pages", group: :jekyll_plugins

gem "tzinfo-data"
gem "wdm", "~> 0.1.0" if Gem.win_platform?

# If you have any plugins, put them here!
group :jekyll_plugins do
  gem "jekyll-paginate"
  gem "jekyll-sitemap"
  gem "jekyll-gist"
  gem "jekyll-feed"
  gem "jemoji"
  gem "jekyll-include-cache"
  gem "jekyll-algolia"
  gem 'webrick'
end 
```

Em seguida execute os comandos
  ```powershell
 C:\blog\>  bundle update
```

  ```powershell
 C:\blog\>  bundle install
```
## Configurando o Site

O arquivo **_config.yml** é o arquivo de configuração para toda estrutura do site; é desse arquivo que é distribuida a configuração para o resto do site, é importante saber que ele não é recarregado automaticamente, sendo necessario reiniciar o servidor quando houver alguma alteração.


[minimalmistakes]: https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide
[githubMinmalCreate]: https://github.com/mmistakes/mm-github-pages-starter/generate
[Ruby-Devkit]: https://rubyinstaller.org/downloads/ 
[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
