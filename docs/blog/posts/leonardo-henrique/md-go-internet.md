---
date:
  created: 2021-07-14
authors:
  - leonardo-henrique
categories:
  - Leonardo Henrique
comments: true
slug: md-go-internet
tags:
  - Desenvolvimento
  - How-to
---

# Como subir sua aplicação Golang gratuitamente para a internet

![Gophers, os macostes do Go](../../../images/blog/leonardo-henrique/md-go-internet-art.png)  
*Gophers, os macostes do Go*

Nesse texto vou descrever o passo a passo que você vai seguir para poder colocar seu projeto pessoal — e quem sabe até um projeto pelo qual você tenha sido contratado — em um servidor 100% gratuito. Para isso, vamos utilizar o Heroku, uma plataforma robusta voltada para deploy de servidores.

<!-- more -->

## Passo 1 — Preparando o terreno

Vamos iniciar pelo começo. Precisaremos de algumas coisas antes de efetivamente subir o servidor.

1º — Git: para conseguirmos versionar nosso código e enviar nossas alterações para o servidor, precisaremos ter o Git instalado em nossa máquina. A instalação é bem simples e você pode baixar através do [site oficial](https://git-scm.com/downloads), escolhendo seu sistema operacional e seguindo o passo a passo padrão.

2º — Conta no Heroku: claro, se vamos utilizar os serviços do Heroku, precisamos de uma conta nele 🤣 A criação de conta é bem tranquila, basta entrar no site oficial , clicar em “Sign up” e seguir o processo.

3º — Heroku CLI: Ufa! Chegamos à terceira e última ferramenta que precisamos ter. O Heroku CLI é a aplicação em linha de comando que possibilita que “conversemos” com o Heroku. É a partir dela que iremos criar nossos servidores e subir nossos arquivos.

- **Se você está em um ambiente Windows** 64 bits, você pode baixar o instalador [aqui](https://cli-assets.heroku.com/heroku-x64.exe) e se estiver com um Windows 32 bits, basta baixar por [aqui](https://cli-assets.heroku.com/heroku-x86.exe)
- **Se você está usando macOS** basta executar `brew tap heroku/brew && brew install heroku`
- **Caso você esteja em um ambiente Ubuntu**, execute `sudo snap install --classic heroku`

Para verificar se a instalação ocorreu de fato, reinicie seu terminal e rode `heroku login`, se tudo der certo você verá essa mensagem *“Press any key to open up the browser to login or q to exit”*, basta apertar qualquer tecla e fazer login com seu email e senha no Heroku na janela do navegador que acabou de abrir.

## Passo 2 — Subindo sua aplicação

Agora chegou a hora de efetivamente “subirmos” nossa aplicação em um servidor no Heroku. Se você já tem uma aplicação desenvolvida e quiser usá-la nesse passo-a-passo, fique à vontade. Mas se você não possuir uma, não se preocupe, deixei em meu Github uma mini aplicação já pronta para você utilizar (clique aqui). Basta fazer o clone em sua máquina e seguir o tutorial 👌

Esse é um passo crucial. Há um detalhe muito importante ao trabalharmos com Heroku: o arquivo Procfile. É ele o responsável por dizer ao nosso servidor como ele vai iniciar nossa aplicação. Basta criar ele na raiz de seu projeto, apenas com o nome Procfile. Isso mesmo, sem extensão, sem nada. O conteúdo dele será:

`web: bin/nome-do-go-mod`

***nome-do-go-mod** é o nome que você deu para o seu módulo*

Arquivo criado, é hora de enviarmos nossa aplicação para o Heroku e deixar ela online!

1. Abra seu terminal e aponte para a raiz da sua aplicação. Precisaremos, primeiro, inicializar o git na pasta rodando o comando `git init`
2. Agora, adicionaremos os arquivos no staging area (se você não conhece a terminologia, não precisa se preocupar imediatamente mas sinta-se livre para pesquisar). Para isso, usaremos o comando `git add .`
3. Vamos escrever um mensagem para indicar as mudanças que faremos, no caso, como é a primeira vez que vamos enviar arquivos para o servidor, podemos utilizar o famoso “first commit”. O código é `git commit -m "first commit"`
4. É hora de fazer login no Heroku. Utilizamos aquele comando lá de trás, o `heroku login` para fazê-lo. Aperte qualquer tecla, insira suas credenciais na página aberta no navegador e você já pode retornar ao terminal
5. Vamos criar agora o servidor em que ficará nossa aplicação. Você pode utilizar o `heroku create`, que vai gerar um servidor com nome aleatório ou `heroku create nome-super-bacana` para escolher um nome que quiser (esse nome deve ser único, por isso, há a possibilidade do Heroku te avisar que o nome já estar sendo usado. Nesse caso, basta inserir o comando novamente com um novo nome). Escolhi para o meu servidor o nome de *golang-app-tutorial*, então ao final, vou acessá-lo por *golang-app-tutorial.herokuapp.com*. **É um padrão: nome-do-app.herokuapp.com**
6. Hora da verdade! Rodamos `git push heroku master` e enviamos nossa aplicação para o servidor.

Se você utilizou os arquivos que disponibilizei, acessando a url da aplicação você verá um “Olá! Seja muito bem vindo(a)!”. Caso tenha utilizado seus próprios arquivos, veja se tudo correu como quando você utiliza sua aplicação localmente. Mas chegando à esse ponto: **parabéns, você fez seu primeiro deploy no Heroku, 100% gratuito!**

*_texto original publicado em [medium.com](https://medium.com/c%C3%B3digo-palavras/como-subir-sua-aplica%C3%A7%C3%A3o-golang-gratuitamente-para-a-internet-57321cfcbaa0)*