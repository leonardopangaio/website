---
date:
  created: 2025-01-13
authors:
  - leonardo
categories:
  - Leonardo Pangaio
comments: true
slug: como-criei-meu-site
tags:
  - Inspiração
  - História
---

# Como criei meu site

Resolvi escrever este post depois de ver o que acabei aprendendo durante o processo de criação do meu site. Não que eu tenha virado um dev, ou devops ou um webmaster (denunciei a idade), nesse caminho, que começou ali em outubro de 2024.

<!-- more -->

## O Glossário

Começou quando eu pensei em publicar uma página, pra ser o glossário, de graça e me lembrei do Github Pages, que eu já tinha feito uns testes básicos no início do ano passado. A ideia do glossário era poder criar uma página com conteúdo, mas sem ter que escrever um site em HTML e ter algum trabalho para subir isso para um serviço de hospedagem de forma manual. O Github Pages resolveu os dois de uma vez só, pra criar uma página, só preciso subir o arquivo readme.md e usar o próprio GP pra publicar o site.

Beleza, com isso eu já tinha resolvido três problemas, o do conteúdo ser apenas um arquivo de texto livre ([markdown](https://www.markdownguide.org/)) e da hospedagem ser gratuita ([Github](https://github.com/)) e da publicação ser facilitada (Github Pages), mas ainda ficou uma questão, o glossário, por padrão, é em ordem alfabética, e eu tinha uma infinidade de termos pra criar. Desta dificuldade nasceram algumas soluções que eu aprendi:

- Criação de templates e/ou blocos de código no VS Code;
- Utilização de variáveis em Snippets de código do VS Code;
- Script em Python para criar um readme.md baseado nos arquivos markdown que eu criava de cada um termo;
- Pipeline com o Github Actions para executar esse script Python;
- Configurações de secrets e utilização deles no Github Actions;
- Makefile para simplificar algumas coisas que são repetitivas. Nesse tópico eu consegui vendo uma [playlist](https://youtube.com/playlist?list=PLLCFxfe9wkl-tCZvSCbzQGcNv9nSN5ZAP&si=-KVgSufivzJ-qGNl) sobre makefile que achei no canal [Geofisicando](https://www.youtube.com/@Geofisicando) do youtube;

Com isto eu já tinha a forma de criar o meu glossário, e bastaria eu ir criando cada item do jeito que eu queria, uma breve explicação (até dois parágrafos) e algumas referências mais confiáveis que a minha palavra e/ou uma busca no [ChatGPT](https://chatgpt.com).

Perfeito, com o [glossário](https://leonardopangaio.github.io/glossario/) já publicado, me veio a ideia, poxa, o glossário eu só dou uma breve explicação do termo e as referências, mas nele eu não tenho espaço pra apresentar novas ideias, publicar algum artigo, guia, passo-a-passo, discutir sobre algum assunto e etc... Daí nasceu a ideia de criar o blog.

## O Blog

Numa busca rápida, caí num canal do [youtube](https://www.youtube.com/) de um camarada chamado [Renato Faria](https://www.youtube.com/@RenatoFariaPro) que tem uma [playlist](https://youtube.com/playlist?list=PLYVsHDrAWfs7VDzGaMNVZ-lRmpvZ0iQed&si=Z1NImhlCIR3cXuYA) só de como criar um blog no [Blogger](https://www.blogger.com), e ele explica além de como criar o blog, como funciona um pouco do sistema de buscas do Google ([Google Search Console](https://search.google.com)) e do [Google Analytics](https://analytics.google.com).

Mas com esse cenário, me veio uma outra dificuldade, o Blogger, da Google, aceita basicamente texto livre ou HTML, e os textos em markdown são meio do caminho, a formação é devido a marcação feita no texto, mas não chega a ser um HTML e também não é um texto puro, sem nada. Com isto, eu tive que criar um script que convertesse MD pra HTML, o que não deixava o texto muito bom, mas era melhor do que redigir ele todo, toda vez que eu quisesse fazer uma publicação. De todo modo o [blog](https://almanaquedotech.blogspot.com/) foi lançado, e subi duas postagens nele, consegui fazer as configurações do Google Analytics e Search Console.

De qualquer forma, acabava ficando com dois ambientes, e além de serem de formas diferentes, tecnologias diferentes, em repositórios diferentes diferentes e o upload de um deles de forma manual também tinha o fato de que ambos não tinham uma unidade, não tinham uma "carinha" única.

## O Site

Depois de algumas semanas com esses dois ambientes, caí num vídeo de youtube de um cara chamado [NetworkChuck](https://www.youtube.com/@NetworkChuck), onde o [vídeo](https://youtu.be/dnE7c0ELEH8?si=J8GAMCbSL5PRvspc) que ele falava era sobre a criação de um blog em pleno 2024. O vídeo basicamente é ele apresentando toda a stack que ele utilizou pra fazer o pipeline dele, para que o blog fosse um repositório de documentação, onde ele iria se preocupar apenas com os textos em markdown e o restante os sistemas que ele tinha escolhido e o pipeline que ele tinha montado iria subir pro repositório, iniciar o pipeline e subir o site pronto para a hospedagem.

Durante o vídeo ele usa o Github como repositório do código, o [Obsidian](https://obsidian.md/) para realizar a escrita dos artigos em markdown e usa o [Hugo](https://gohugo.io/) para realizar a conversão dos markdown em um site estático. Esse vídeo me mostrou que existem ferramentas que foram criadas para isso, para gerar sites "bonitos" para documentação, principalmente focada em documentação de sistemas. Ferramentas como [Docusaurus](https://docusaurus.io/), do Facebook, [Sphinx](https://www.sphinx-doc.org), Hugo, [Jekyll](https://jekyllrb.com/), [MKDocs](https://www.mkdocs.org/) e alguns outros.

Dando uma pesquisada melhor, e fazendo alguns testes, vi que o MKDocs era desenvolvido em Python (gosto, tenho alguma facilidade) e que ele era basicamente um arquivo YML de configuração e o conteúdo, o deploy seria com um comando e pronto, todo o meu site estava pronto. Olhando um pouco melhor, acabei caindo num canal de youtube de um cara chamado [James Willett](https://www.youtube.com/@james-willett) que tem uma [playlist](https://youtube.com/playlist?list=PLw_jGKXm9lIaJCD8YClu6cAz1TcFdJdIf&si=Wv5hmY0OTrayg8mm) inteira sobre como usar um tema do MKDocs chamado [Material Theme for MKDocs](https://squidfunk.github.io/mkdocs-material/), inclusive ele é citado na documentação oficial do tema. Esse tema aumentava em muito a quantidade de funcionalidades do site, inclusive a quantidade de personalizações.

Levei uns 2 ou 3 finais de semana testando o Material for MKDocs com o MKDocs, testando organização, testando formatos de conteúdo, testando as funcionalidades dos dois, sobe pro Github, testa novamente, testa local e faz comparação, sobe imagem, sobe mídia, testa integração com Analytics, testa feed RSS, testa isso, testa aquilo e vamos que vamos. Como trabalho ha um tempo com sustentação e operação de TI acabei dando uma exagerada nos testes das funcionalidades e também fui tentando dar uma automatizada, ou pelo menos uma facilitada no meu trabalho, daí fui também testando um cadinho do pipeline sugerido mais um [makefile](https://www.gnu.org/software/make/manual/make.html) pra facilitar um pouco a vida. 

Beleza fui pra última parte do planejado, que era adquirir um domínio, o [pangaio.com.br](https://pangaio.com.br) no [Registro.br](https://registro.br/), comprei o domínio e aí? Como usa? Como faço pra configurar esse meu domínio no Github Pages? Eu nunca tinha configurado um domínio personalizado em lugar nenhum só aqueles gratuitos tipo NO-IP e coisas do gênero, que basicamente era a instalação de um cliente no computador e ele fazia todo o resto. Com isso, e a documentação não tão clara assim pra mim (leigo nas configurações do Github), encontrei um [vídeo](https://youtu.be/FoKixG86msg?si=-j7wAbHaKLH6iTmh) de um canal chamado [Dotcode](https://www.youtube.com/@DotcodeEdu) no youtube, que ele ensina justamente a fazer isso, a configurar um registro do Registro.br no Github Pages.

Mas ainda faltava um item, ainda tive um probleminha com os deploys e a perda da configuração do CNAME para o funcionamento do site, pois como o MKDocs faz o deploy do site em uma branch específica pro Github Pages, essa branch não tinha o arquivo de configuração, pois nela só tinham os arquivos que estavam dentro da pasta onde eu criava a documentação que o MKDocs faria a conversão. A solução foi simples, porém depois de um tempo procurando em ChatGPT, Google e [Stack Overflow](https://stackoverflow.com/), onde resolvi movendo o arquivo CNAME para dentro da pasta docs do meu projeto, com isto, o MKDocs faz a cópia do CNAME para a branch correta, e assim o Github Pages continua com o domínio personalizado.

Esse foi o meu trajeto até agora, ainda tenho um backlog que gostaria de implementar no site.

Não tenho pretensões de ser um site extremamente bonito, bem diagramado, nem cheio de funcionalidades. Tenho o desejo de que seja um site útil, de fácil navegação e que eu consiga ajudar, nem que seja dando ideias, para outras pessoas.