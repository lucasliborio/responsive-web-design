# Primeiro Capitulo - The Essentials of Responsive web Design

## Repositorio com exemplos

<https://github.com/benfrain/rwd4>

### Definindo Design Responsivo

- Todo design responsivo é definido por três tecnicas
  - Area de layout flexivel
  - Imagens/Media flexiveis
  - Media queries

### Viewport

- é a area da janela do navegador que a pagina web está permitida a ocupar.
- a tag meta "viewport" simplesmente especifica que o conteudo da pagina web deve ser to tamanho da tela do dispositivo.

~~~~html
  <meta name="viewport" content="width=device-width,initial-scale=1.0" />
~~~~

### Imagens

- Para manter imagens responsivas utilizamos somente uma linha de codigo em css
- Não devemos usar width aqui, pois irá fazer com que a logo tambem tente ocupar 100%, esticando-a

~~~css
img {
  max-width: 100%;
}
~~~

### Adicionando Media queries

- Media queries são normas que nos permite isolar regras do CSS para determinadas condições, como por exemplo: Tamanho da tela.
- Cade media query possui um **breakpoint** que a é a condição que deverá ser suprida para que a CSS rules sejam executadas.

~~~css
@media screen and (min-width: 800px) {
  /* Ao adicionar essa media query com o BREAKPOINT min-width, a tela precisará ter ao menos 800 de width para que a regras aqui dentro sejam executadas*/
}
~~~~
