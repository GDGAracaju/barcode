*[Click here to read the English version](https://github.com/maurogeorge/conf_boilerplate_ruby/blob/master/README.md)*

---

# Conf Boilerplate Ruby

---

O projeto tem como objetivo ajudar aqueles que querem organizar conferências/eventos e não tem muito tempo para criar o site disso.

* [Como funciona?](#como-funciona)
* [Estrutura](#estrutura)
* [Primeiros passos](#primeiros-passos)
* [Customização](#customizao)
* [Deploy](#deploy)
* [Inspiração](#inspirao)

## Como funciona?

Desenvolvido em [Jekyll](https://github.com/mojombo/jekyll), um static generator em Ruby, para criar esse modelo extremamente simples de customizar. Além disso, a hospedagem é gratuita via [Github Pages](http://pages.github.com) e você ainda pode usar seu próprio domínio *(mais informações sobre isso em [Deploy](#dom%C3%ADnio-personalizado))*.

Por padrão, definimos as seguintes seções:

* *About* - Para que você possa descrever o objetivo do seu evento.
* *Location* - Para que você possa exibir a localização do seu evento através do Google Maps.
* *Speakers* - Para que você possa listar informações sobre os palestrantes.
* *Schedule* - Para que você possa mostrar a agenda do evento.
* *Sponsors* - Para que você possa fazer propaganda dos seus patrocinadores.
* *Partners* - Para que você possa fazer propaganda dos seus apoiadores.

*OBS 1: Não há integração com nenhum sistema de inscrição e/ou pagamento. Por conta disso, indicamos o [Eventick](http://eventick.com.br/).*

*OBS 2: Para formulários de contato, indicamos o [Wufoo](http://wufoo.com/).*

## Estrutura

A estrutura básica do projeto se dá na seguinte forma:

<pre>
.
|-- .ruby-version
|-- .ruby-gemset
|-- _config.yml
|-- _includes/
|   |-- header.html
|   |-- nav.html
|   |-- section/
|-- _layouts/
|-- _site/
|-- css/
|-- Gemfile
|-- Gemfile.lock
|-- img/
|-- index.html
|-- js/
</pre>

### .ruby-version e .ruby-gemset

São os arquivos responsáveis pelo gemsite do projeto.

### _site/

É onde os arquivos gerados são armazenados, uma vez que o Jekyll tenha sido rodado. Porém, esse diretório se torna desnecessário no versionamento, por isso está ignorado ([.gitignore](https://github.com/maurogeorge/conf_boilerplate_ruby/blob/master/.gitignore)).

### [index.html](https://github.com/maurogeorge/conf_boilerplate_ruby/blob/master/index.html)

Contém o arquivo responsável por importar todas as seções da aplicação.

### [css](https://github.com/maurogeorge/conf_boilerplate_ruby/tree/master/css)

Possui os arquivos de CSS.

### [img](https://github.com/maurogeorge/conf_boilerplate_ruby/tree/master/img)

Possui os arquivos de imagens.

### [js](https://github.com/maurogeorge/conf_boilerplate_ruby/tree/master/js)

Possui os arquivos de JavaScript.

### [_layouts](https://github.com/maurogeorge/conf_boilerplate_ruby/tree/master/_layouts)

Contém o template padrão da aplicação.

### [_includes](https://github.com/maurogeorge/conf_boilerplate_ruby/tree/master/_includes)

São blocos de código utilizados para gerar a página principal do site ([index.html](https://github.com/maurogeorge/conf_boilerplate_ruby/blob/master/index.html)).

### [_config.yml](https://github.com/braziljs/conf-boilerplate/blob/master/docpad.cson)

Armazena de forma fácil a maior parte das configurações da aplicação.

### [Gemfile](https://github.com/braziljs/conf-boilerplate/blob/master/package.json)

Lista as dependências de módulos do Ruby.

### [Gemfile.lock](https://github.com/braziljs/conf-boilerplate/blob/master/package.json)

Arquivo gerado pelo Gemfile.


## Primeiros passos

1. Instale o [Git](http://git-scm.com/downloads)

2. Instale o [RVM](https://rvm.io/) e o Ruby

3. Clone o projeto:

    git clone git@github.com:maurogeorge/conf_boilerplate_ruby.git

5. Depois vá para pasta do projeto:

    cd conf_boilerplate_ruby

6. Instale as dependências:

    bundle

7. E finalmente rode:

    jekyll server

Agora você irá ver o site rodando em `localhost:4000` :D

## Customização

O projeto já vem com um template visual pronto, use-o à vontade, mas nós recomendamos que você crie seu próprio, a fim de colocar sua própria cara no evento.

De qualquer forma, nós preparamos algo altamente customizável para você, portanto para maioria das alterações do projeto basta ir até o `_config.yml` e alterar o valor das variáveis.

### Informações básicas sobre a conferência

Quer alterar o nome, data, endereço, cidade ou preço do evento? É só mudar.

```
conf:
  name: "Conference name"
  description: "Conference description"
  date: "November 15"
  price: "$100"
  address: "Boulevard Kukulcan, 30, México"
  venue: "Coco Bongo"
  city: "Cancún"
```

### Informações básicas sobre o site

Quer mudar a imagem de capa, código do Google Analytics ou o favicon? Vá em frente!

```
site:
  url: "http://confboilerplate.com"
  favicon: "http://braziljs.org/favicon.ico"
  googleanalytics: "UA-33656081-1"
  images:
    cover: "http://f.cl.ly/items/2X28422q1e3w0C2U1P3H/866591_24254643.jpg"
    facebook: "http://braziljs.org/img/fb-share.jpg"
```

### Seções ativas

Ainda não definiu a programação completa do evento? Não tem problema, basta alterar a variável `schedule` para `false`.

Ainda não sabe quem irá palestrar? Tudo bem, basta alterar a variável `speakers` para `false`.

E por aí vai.

```
sections:
  about: true
  location: true
  speakers: true
  schedule: true
  sponsors: true
  partners: true
  contact: false
```

### Lista de Palestrantes

Para incluir/alterar/excluir um palestrante também é igualmente simples, basta recorrer ao `schedule`.

```
schedule:
  -
    name: "Linus Torvalds"
    photo: "http://f.cl.ly/items/2A3p1N0C3c0n3N3R1w2B/speaker.jpg"
    bio: "Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo"
    company: "Linux Foundation"
    twitter: "linus"
    presentation:
      title: "Digging into a Linux Kernel"
      description: "Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo"
      time: "10h00"
```

Quer listar mais algum atributo do palestrante que não está ali? Tudo bem, é só adicionar no `_config.yml` e depois exibí-lo com `{{ speaker.seuNovoAtributo }}` no [speakers.html](https://github.com/maurogeorge/conf_boilerplate_ruby/blob/master/_includes/section/speakers.html).

### Lista de outros itens da Agenda

Para alterar os horários de check-in, almoço e coffee-break, é só recorrer as variáveis de `schedule`.

```
schedule:
  -
    name: "Check-in / Breakfast"
    time: "9h00"
```

Mas se você quiser adicionar mais um coffee-break ou qualquer outro tipo de item na agenda do evento, é só acrescentar mais um item nessa lista.

### Lista de Patrocinadores/Apoio

Para adicionar qualquer patrocinador ou apoio no evento, é só recorrer as variáveis `sponsors` e `partners`.

```
partners:
  -
    name: "BrazilJS"
    logo: "http://f.cl.ly/items/2N3i2W0X2f3c2g2Z2N0f/Untitled-1.png"
    url: "http://braziljs.org"
```

## Deploy

Nós não gostamos de centralizar o poder de deploy em uma pessoa, portanto utilizaremos o recurso de [Github Pages](http://pages.github.com) que ainda é gratuito.

* Mande o seu código para o seu repositório com `git push`

Espere alguns minutos até que o Github lhe envie um e-mail avisando que tudo ocorreu bem. Depois é só acessar: `http://seuUsuario.github.com/seuFork`

### Domínio personalizado

Caso você não queira utilizar o domínio do Github, é possível usar seu próprio com alguns passos.

1. Crie o arquivo `CNAME` na raíz do seu projeto e preencha com o nome do seu domínio: `seuevento.com`. [Veja o exemplo](https://github.com/braziljs/conf-boilerplate/blob/master/src/files/CNAME).
2. Altere o DNS do seu domínio seguindo as [instruções do Github](https://help.github.com/articles/setting-up-a-custom-domain-with-pages).

### Como fazer sem Deploy utilizar Github Pages

Se você prefere utilizar seu próprio servidor para hospedar o site:

* Rode `jekyll build` na raíz do projeto.

Esse comando irá gerar uma pasta `_site` contendo apenas arquivos estáticos, depois é só fazer o upload do conteúdo dessa pasta para sua hospedagem.

## Inspiração

Criado a partir do projeto [Conf Boilerplate](https://github.com/braziljs/conf-boilerplate) que é uma iniciativa da [BrazilJS Foundation](http://braziljs.org).
