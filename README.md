# website

Este documento visa a descrever rapidamente como foi a criação do site pangaio.com.br

Resumidamente comecei um repositório para testes, e com ele aprendi muita coisa na tentativa e erro, e quando fiz aqui este site, ele já estava quase todo pronto.

Deixo aqui os passos seguidos e relacionado os arquivos de configuração, assim como os comentários das dificuldades.

1. Criação do repositório no Github;
2. Instalação dos módulos, para isso podemos utilizar arquivo `requirements.txt` que está neste repositório;
3. Após a instalação dos módulos, foi a etapa de iniciar o projeto, que foi com o comando `mkdocs create`, que está documentado no makefile, também aqui no repositório, e que pode ser executado através do `make create`;
4. A criação do conteúdo vai de cada um, então essa é uma etapa pessoal;
5. Aquisição do domínio `pangaio.com.br` foi feito no `registro.br` e foi vinculado ao Github Pages da minha conta, gerando o arquivo CNAME;
    1. Houve uma etapa de configuração no `registro.br` também, e pra isso segui esse tutorial [aqui](https://youtu.be/FoKixG86msg?si=vNfAcNGdMWZSCmnl).
    2. Movi o arquivo pra dentro da pasta docs, pois mais pra frente, quando o *pipeline* for criado, se esse arquivo estiver de fora, o site ao ser atualizado perdia a referência do domínio personalizado;
6. Criação do *pipeline* para atualização automática do site, nesse ponto apenas segui o passo-a-passo descrito na própria [documentação](https://squidfunk.github.io/mkdocs-material/publishing-your-site/) do Material for MkDocs;
    1. Um ponto aqui que apanhei um pouco foi com a criação do *secret* para a chave do *Google Analytics*, mas depois que vi que esse *secret* é criado dentro da configuração do próprio repositório e declarado no proprio yml do *pipeline*, funcionou bem. Exemplo no arquivo `.github/workflos/ci.yml`;
7. Não realizei a ativação da informação de quem editou o o commit/revisão pois como a seção de Glossário tem MUITOS artigos, acaba estourando o limite de requisições do Github free;
8. Para ativar os comentários, eu segui o passo a passo do [James Willett](https://youtu.be/pPEUhfTZswc?si=BXe5V0tAIh5Q2RVY);

Esse site é um perfeito exemplo de documentação como código, onde eu poderia postar documentação de um software por exemplo. No caso, estou postando artigos em um blog e itens em um glossário, da mesma que um desenvolvedor faria, utilizando uma **IDE** para **codificar**, utilizando o github para **versionar**, usando um **pipeline** para automatizar o meu **deploy** e disponibilizando para que possa ser revisto por outras pessoas.

## Referências

- https://youtube.com/playlist?list=PLw_jGKXm9lIaJCD8YClu6cAz1TcFdJdIf&si=3UyegbkErcoA3WZN
- https://squidfunk.github.io/mkdocs-material/