---
title: "Criando Blog Jekyll no Windows Pt-2"
date: 2023-04-09T15:34:30-04:00
categories:
  - documentação
tags:
  - blog
  - configuração
  - windows
  - Jekyll
  - update
  - tutorial
---
Neste ano, senti necessidade de organizar as coisas que estou aprendendo e fazendo em um blog.  
Já havia criado um blog com Jekyll anteriormente e me lembrava de que era um processo tranquilo e rápido. Certa vez, durante um carnaval, SouEnzzo me apresentou ao Jekyll e, juntos, configuramos um blog em apenas algumas horas no Linux.  
Fazer isso em Windows sozinho não foi tão simples devido aos multiplos caminhos e configuração que são necessarias, dependendo de como esteja seu sistema Windows, pode ser algo simples ou trabalhoso.  
Aqui vou deixar um resumo de como configurar o sistema Windows e na Parte 2 vou falar um pouco do tema Minimal Mistakes, que escolhi devido à presença da busca global e outras funcionalidades refinadas que já estão pré-configuradas, o que facilita as coisas  

## Instalação
Ambiente de trabalho:
 - Sistema Operacional: Windows 10

#### Instalação Ruby

 O Jekyll é baseado em Ruby, portanto, é necessário instalá-lo para que funcione adequadamente. Faça o download através do link [Ruby][Ruby-Devkit]. Eu utilizei o Ruby+Devkit 3.2.2.1(x64). Durante a instalação, lembre-se de marcar a opção "Add Ruby Executables to your PATH".

Após a instalação, verifique se foi bem-sucedida, abrindo o cmd e executando o seguinte comando:
  ```powershell
 C:\> ruby -v
```
O retorno deve ser algo parecido com isso:

  ```powershell
ruby 3.2.2 (2023-03-30) [x64-mingw-ucrt]
```
Caso isso não ocorra, configure corretamente as variáveis de ambiente do Windows. Vá em Path nas variáveis do sistema e configure o caminho onde foi instalado o Ruby e adicione um path do Ruby/bin.

![Clique duas vezes em Path e configure o caminho do Ruby/Bin]({{ site.url }}{{ site.baseurl }}/assets/images/configpath1.jpg){: .align-center}

Deve ficar da seguinte forma:

![Configurando Path do Ruby]({{ site.url }}{{ site.baseurl }}/assets/images/configpath2.jpg){: .align-center}

Finalize a configuração adicionando a variável 'RUBYOPT' com o valor '-Eutf-8'.

![Adicione uma variável de nome RUBYOPT com valor -Eutf-8]({{ site.url }}{{ site.baseurl }}/assets/images/configpath3.jpg){: .align-center}

#### Instalação Jekyll Gem

A partir de agora, podemos utilizar as Gems do Ruby. O próprio Jekyll vem na forma de uma Ruby Gem, sendo um pacote de fácil instalação. Para isso, abra o cmd e execute o seguinte comando:

  ```powershell
C:\> gem install jekyll
```
Pressione Enter e aguarde todas as instalações. Isso pode demorar um pouco, portanto, certifique-se de manter a conexão com a internet durante o processo.

Ao finalizar a instalação execute 
  ```powershell
C:\> jekyll -v
```
O retorno deve ser algo parecido com isso:

  ```powershell
jekyll 4.3.2
```

Com isso, o sistema está pronto para executar o blog em Jekyll.
Escolha a pasta onde deseja armazenar seu blog, abra o prompt de comando (cmd) e execute:

  ```powershell
C:\blog\> jekyll new Nome-Do-Seu-blog
```
Ao termino do processo serão criados os seguintes arquivos:
  - Gemfile
  - Gemfile.lock
  - _config.yml
  - _posts
  - about.md
  - index.md  

Vou tratar um pouco sobre eles na Parte 2 para que a postagem não fique tão extensa.



[Parte2]:
[minimalmistakes]: https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide
[githubMinmalCreate]: https://github.com/mmistakes/mm-github-pages-starter/generate
[Ruby-Devkit]: https://rubyinstaller.org/downloads/ 
[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
