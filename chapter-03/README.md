# Chapter 3 - Media Queries and Container Queries

## Referencias

- Iremos utilizar incialmente esse site para entendermos um pouco da nessecidade do media queria para a responsividade.
  - ***[Site do livro](<https://rwd.education/>)***
  - ***[Media Query 3](https://www.w3.org/TR/mediaqueries-3/)***
  - ***[Media Query 4](https://www.w3.org/TR/mediaqueries-4/)***
  - ***[Media Query 5](https://www.w3.org/TR/mediaqueries-5/)***

### Media queries

- Media queries nos permite segmentar estilos CSS dependendo dos recursos do dispositivo. Alguns desses recursos são

  - ***Largura da janela***
  - ***Proporção de tela***
  - ***Orientação da tela (paisagem ou retrato)***
  - Entre outras.

### Tag meta="viewport"

- Vamos começar entendendo melhor a meta tag.

~~~~html

<meta name="viewport" content="width=device-width, inital-scale=1.0">
~~~~

- ***"initial-scale=x"***
  - O zoom inicial que será renderizada a pagina.

- ***"width=device-witdh"***
  - Informa ao browser que a largura deve ser igual a largura do dispositivo.

- ***"maximum-scale=x, minimum-scale=x"***
  - Escala maxima de zoom e escala minima de zoom

- ***"user-scalable="no""***
  - Impede que o usuario dê zoom na pagina. O que não é muito util mas existe essa opção.

### Media query sintax

- Media query funciona como se fosse uma ***condicional*** e no momento que essa condicional é atingida teremos a regra de CSS aplicada.

- No exemplo ***[basic-conditional](/chapter-03/basic-conditional/index.html)*** nós vemos a media query sendo utiliziada com a condicional ***min-width***. Então sempre que a tela for maior que o valor descrito na condicional o css será aplicado.

- Parece estranho porque a condional fala de ***min-width*** mas começa a fazer sentido depois.

media_types and media feature

#### Formas de aplicar o media query

- ***Media queries in link tags***
  - Podemos importar diretamente do arquivo html passando qual será a condicional.

  ~~~html
  <link 
    rel="stylesheet" 
    media="screen and (orientation: portrait)"
    href="css/portrait-screen.cs"
  >
  ~~~

- ***Media query on an @import at-rule in CSS File***
  - Podemos importar dentro de um arquivo CSS determinado estilo mediante condicional.

  ~~~css
  @import url("css/portrait-screen.css") screen and (orientation: portrait);
  ~~~

- ***Media queries in a CSS file***
  - Esse aqui é o mais comum de vermos.

  ~~~CSS
  @media screen and (orientation: portrait) {
    /*styles here*/
  }
  ~~~

#### Invertendo a logica do media query

- Usando a keyword ***not*** podemos inveter a logica da media query
  - Interessante mas não muito util. O jeito padrão acaba sendo mais viavel.

  ~~~html
  <link
    rel="stylesheet"
    media="not screen and (orientation: portrait)"
    href="css/portrait-screen.css"
  />
  ~~~

#### Combinando media queries

- Podemos combinar condicionais de media queries

  ~~~html
  <link
    rel="stylesheet"
    media="screen and (orientation: portrait) and (min-width: 800px)"
    href="css/800wide-portrait-screen.css"
  />  
  ~~~

#### Lista de media queries

- Podemos ter uma lista de media queries. Caso qualquer uma da lista for ***true***, a media query será aplicada.
- A lista é separada por ***virgulas***

  ~~~html
    <link
      rel="stylesheet"
      media="screen and (orientation: portrait) and (min-width: 800px),projection"
      href="800wide-portrait-screen.css"
    />
  ~~~

### 