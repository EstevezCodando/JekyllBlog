---
title: "Criando meu Blog com Jekyll"
date: 2023-04-08T15:34:30-04:00
categories:
  - blog
tags:
  - Jekyll
  - update
---

Neste ano, senti uma grande necessidade de organizar minhas atividades em um blog e ter um espaço para compartilhar testes e ferramentas aprendidas. Já havia criado um blog com Jekyll anteriormente e me lembrava de que era um processo tranquilo e rápido. Certa vez, durante um carnaval, meu amigo Enzzo me apresentou ao Jekyll e, juntos, configuramos um blog em apenas algumas horas no Linux.  
Fazer isso em Windows sozinho não foi tão simples devido aos multiplos caminhos e configuração que são necessarias, dependendo de como esteja seu sistema Windows, pode ser algo trabalhoso. Optei pelo tema Minimal Mistakes devido à presença da barra de navegação e busca global e outras funcionalidades refinadas que já estão pré-configuradas, o que facilita bastante a vida.  

## Instalação
 - Sistema Operacional: Windows 10

#### Instalação Ruby

 O Jekyll é baseado em Ruby, portanto, é necessário instalá-lo para que funcione adequadamente. Faça o download através do link [Ruby][Ruby-Devkit]. Eu utilizei o Ruby+Devkit 3.2.2.1(x64). Durante a instalação, lembre-se de marcar a opção "Add Ruby Executables to your PATH".

Após a instalação, verifique se foi bem-sucedida, abrindo o cmd e executando o seguinte comando:
  ```powershell
ruby -v
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
gem install jekyll
```
Pressione Enter e aguarde todas as instalações. Isso pode demorar um pouco, portanto, certifique-se de manter a conexão com a internet durante o processo.

Ao finalizar a instalação execute 
  ```powershell
jekyll -v
```
O retorno deve ser algo parecido com isso:

  ```powershell
jekyll 4.3.2
```

Com isso, o sistema está pronto para executar um blog em Jekyll.
Escolha a pasta onde deseja armazenar seu blog, abra o prompt de comando (cmd) e execute:

  ```powershell
jekyll new Nome-Do-Seu-blog
```
Ele vem com os seguintes arquivos:
  - Gemfile
  - Gemfile.lock
  - _config.yml
  - _posts
  - about.md
  - index.md  

O arquivo *Gemfile* é onde fica armazenado todas as gems utilizadas na pagina, que pode ser entendido como extensões e plugins utilizadas. Exemplo, para o funcionamento eu utilizo o wdm para verificar as alterações em tempo real *gem "wdm"*, e para busca estou utilizando o plugin *gem "jekyll-algolia"*.   
  

Ao iniciar o blog com *new* o Jekyll inicia com o thema Minima, e rodando o comando:

  ```powershell
gem show minima
```
é possivel ver o caminho dos arquivos de layout utilizados para o blog criado.
é possivel copiar os arquivos para pasta do blog e configurar eles individualmente.
apos realizar as configurações desejadas basta rodar:
  ```powershell
bundle exec jekyll s 
```
para iniciar o server Jekyll, no meu caso eu optei por outro thema e realizei a hospedagem pelo githubpages

#### Criando em Minimal Mistakes

Agora que todo o sistema está em funcionamento é possivel escolher um diferente com algumas configurações já predefinidas, e hospedar no githubpages.
utilizando o seguinte link: 
[Exemplo Minimal Mistakes][githubMinmalCreate]
E aqui tem todas as informações necessarias para [configurar o Minimal Mistakes] [minimalmistakes]




Você pode olhar a documentação do Jekyll em [Jekyll docs][jekyll-docs]


[minimalmistakes]: https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide
[githubMinmalCreate]: https://github.com/mmistakes/mm-github-pages-starter/generate
[Ruby-Devkit]: https://rubyinstaller.org/downloads/ 
[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
