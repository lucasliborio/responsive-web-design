# Chapter 2 - Writing HTML Markup

## Referencias

<https://html.spec.whatwg.org/multipage/>

### Estrutura HTML

- Tags HTML são representadas por elementos que possuem "<" ">"
- Esses elementos são divididos entre tags que se auto fecham e outras não.

~~~~html
<head></head> Abertura e fechamento
<img/> Self Closing
~~~~

### Começando pelo começo

- Essa aqui é uma estrutura basica de HTML.

~~~~html
<!DOCTYPE html> // Indicação que um arquivo HTML.
<html lang="pt-BR"> // Abertura da tag HTML e Linguaguem do documento para ajudar o navegador.
  <head> // Onde se concentram algumas das configurações

    <meta charset="utf-8" /> // O "enconding" que o navegador ira ler esse arquivo.

    <title>Web Page Structure</title> // Titulo que irá aparecer na aba do navegador.

  </head>
  <body></body> // Corpo do site, onde vem o conteudo que aparece no navegador
</html>
~~~~

- Não é necessario gravar exatamente como escrever cada tag, porem é importante saber o que ela faz.

### Tag \<a>

- ***Limitações***
  - Não encapsule outras tags interativas como ***\<button>*** dentro de uma tag ***\<a>***

- Exemplo de uso.

  ~~~html
  <!-- Melhor dessa forma-->
  <a href="index.html">
    <h2>The home page</h2>
    <p>This paragraph also links to the home page</p>
    <img src="home-image.png" alt="A rendering of the home page" />
  </a>
  ~~~

  ~~~html
  <!-- Jeito antigo-->
  <h2><a href="index.html">The home page</a></h2>
  <p><a href="index.html">This paragraph also links to the home page</a></p>
  <a href="index.html">
  <img src="home-image.png" alt="A rendering of the home page" />
  </a>
  ~~~

### Elementos Semanticos

- Existem 3 grupos que definem os elementos:
  - ***Elementos de seccionamento***
  
    - ***Elemento [\<main>](https://html.spec.whatwg.org/#the-main-element)***

      - É o elemento que define o ***conteudo principal***. Não deve ter conteudo que se repete como, navbars, search bar, forms, informações de copy, logos ou banners. A não ser que a pagina seja somente de pesquisa ou um form, nesse caso pode.

      - Só deve existir um ***\<main>*** na pagina

    - ***Elemento [\<section>](https://html.spec.whatwg.org/#the-section-element)***

      - Esse elemento deve ser usado para subdividir sua pagina em seções. Para saber quando usar, se pergunte se a ***\<section>*** que está criando deve conter um heading (***\<h1>...\<h6>***), caso não, você deve usar uma div mesmo.

      - Sections não devem ser utilizadas para estilização.

    - ***Elemento [\<nav>](https://html.spec.whatwg.org/multipage/sections.html#the-navelement)***

      - Esse elemento é direcionado para criar uma lista de navegação para paginas internas ou externas ao site.

    - ***Elemento [\<article>](https://html.spec.whatwg.org/multipage/sections.html#the-article-element)***

      - ***\<article>*** devem conter dentro deles conteudos completos e independentes. Quando tiver duvida, se pergunte se voce pode pegar esse conteudo e mudar de local e ele continuará fazendo sentido.

      - Articles podem existir dentro de articles, porem os articles de dentro devem ser relacionados com os articles de fora.

    - ***Elemento [\<aside>]( https://html.spec.whatwg.org/multipage/sections.html#the-aside-element)***

      - ***\<aside>*** deve conter conteudos relacionados com o conteudo ao redor. Pode ser um sidebar, alguma dica a respeito o assunto em um post. Podem tambem ser observações, pull quotes e um links relacionados. ***Não precisa estar ao lado rsrsrsrs***.

    - ***Elemento [\<header>](https://html.spec.whatwg.org/multipage/sections.html#the-header-element)***

      - Pode ser usado como cabeçalho para o site, ou uma introdução para qualquer conteudo, navbars ***\<section> | \<article>***
      - Não é de fato um elemento de seção

    - ***Elemento [\<footer>](https://html.spec.whatwg.org/multipage/sections.html#the-footer-element)***

      - Como o ***\<header>***, pode ser utilizado em qualquer seção ***\<section> | \<article>***. Utilizado para adicionar informações a respeito da sessão que se encontra, ***copy infos, links, botão de modificações***.
      - Não é de fato um elemento de seção

  - ***Elementos agrupadores***

    - ***Elemento [\<div>](https://html.spec.whatwg.org/multipage/grouping-content.html#the-div-element)***

      - Elemento \<div> não tem conveção, seu unico foco é agrupar coisas.

    - ***Elemento [\<p>](https://html.spec.whatwg.org/multipage/grouping-content.html#the-p-element)***

      - Elemento usado para construir paragrafos de qualquer tamanho.

    - ***Elemento [\<blockquote>](https://html.spec.whatwg.org/multipage/grouping-content.html#the-blockquoteelement)***

      - Elemento que deve envolver um fala de outra pessoa.

      - Pode ser tranquilamente usado dentro de uma tag ***\<p>***

    - ***Elemento [\<figure> and \<figcaption>](https://html.spec.whatwg.org/multipage/grouping-content.html#the-figure-elementt)***

      - Buscar entender melhor, parece meio sem sentido.

    - ***Elemento [\<details> and \<summary>](https://html.spec.whatwg.org/multipage/interactive-elements.html#the-details-element)***
  
      - Uma estrutura interativa de abrir e fechar quando clicada.

      - Deveria ser um otimo substitudo para o display: 'none' | 'block', porem existe alguns problemas na sua execução. como por exemplo não poder ter mais de um ***\<details>*** aberto.

      ~~~~html
      <details open>
        <summary>I ate 15 scones in one day</summary>
        <p>
        Of course I didn't. It would probably kill me if I did. What a way
        to go. Mmmmmm, scones!
        </p>
      </details>
      ~~~~

  - ***Elementos [Inline]( https://html.spec.whatwg.org/multipage/text-level-semantics.html#text-level-semantics.)***

    - ***Elemento [\<span>](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-span-element)***
      - É o elemento inline equivalente a uma ***\<div>***, não possui uma convenção. Ele é perfeito quando o proposito é estilizar algum texto.

    - ***Elemento [\<b>](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-b-element)***
      - Semanticamente falando a tag ***\<b>*** não é pra deixar as coisas em ***BOLD*** e sim representar um texto que você deve ter atenção para fins utilitarios.

    - ***Elemento [\<strong>](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-strong-element)***

      - Diferentemente do ***\<b>***, a tag ***\<strong>*** tem o intuito de demonstrar seriedade, urgencia e grande importancia para o conteudo demarcado

    - ***Elemento [\<em>](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-em-element)***
      - O elemento em representa a ênfase de seu conteúdo
      - O nível de ênfase que um determinado conteúdo tem é dado pelo seu número de elementos ancestrais.
      - A colocação de ênfase de estresse muda o significado da frase. O elemento forma assim uma parte integrante do conteúdo. A maneira precisa em que o acento é usado depende do idioma.

    - ***Elemento [\<i>](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-i-element)***
      - Representa um trecho de texto em uma voz ou humor alternativo, como uma designação taxonômica, um termo técnico, uma frase idiomática de outro idioma, transliteração, um pensamento ou um nome de navio em textos ocidentais.

  - ***Elemento [\<hgroup>](https://html.spec.whatwg.org/multipage/sections.html#the-hgroup-element.)***

    - ***\<hgroup>*** é um elemento que representa o titulos ***\<h1>...\<h6>*** e seus conteudos relacionadas ***\<p>***.

    - Pode usar ***\<hgroup>*** com uma ***\<h1> a \<h6>*** tag com qualquer numero de ***\<p>*** tags antes ou depois
  
    - Devemos evitar escrever textos assim quando necessitarmos de um ***titulo*** e um ***sub-titulo***

      ~~~~html
      <h1>Scones:</h1>
      <h2>The most resplendent of snacks</h2>
      ~~~~

      Do That

      ~~~~html
      <hgroup>
        <h1>Scones:</h1>
        <p>The most resplendent of snacks</p>
      </hgroup>
      ~~~~

### Acessibilidade

- ***Web Content Accessibility Guidelines (WCAG)***

  - Os documentos WCAG explicam como tornar o conteúdo da web mais acessível para pessoas com deficiência.

  - ***Links para documentação.***

    - [WCAG 2.1 em resumo](https://www.w3.org/WAI/standards-guidelines/wcag/)
    - [Referencias rapidas]( https://www.w3.org/WAI/WCAG21/quickref/)

- ***WAI-ARIA (Web Accessibility Initiative – Accessible Rich Internet Applications)***

  - O foco principal do ***WAI-ARIA*** é resolver o problema de fazer conteudo dinamico na web ser acessivel. Ele provê meios de descrever funções, estados e propriedades para widgets, tais como section dinamicas nas aplicações web.

  - ***Links para documentação***
    - [WAI-ARIA](https://www.w3.org/WAI/standards-guidelines/aria/)
    - [WC3 Guide](https://www.w3.org/TR/using-aria/)

#### Embedding media in HTML

- ***[Elemento \<video> and \<audio>](/chapter-02/media/index.html)***
  - Ambos elementos possuem funcionamento parecidos.
  - Como mostro no exemplo do [media](/chapter-02/media/index.html), podemos usar a tag ***\<source>*** para ter mais de extensão para a media que estamos disponibilziando, o navegador irá ler na ordem que está escrita e a primeira que for compativel será executada.
  - ***Existem atributos chaves para essa tag***.
    - ***controls***
      - para mostrar os controls.
    - ***autoplay***
      - para iniciar dando play no video.
    - ***muted***
      - para inciar mudo.
    - ***loading='lazy'***
      - O navegador só irá baixar a media no momento que for renderizada na tela.
      - serve para imagens, video, audio, iframes.

- ***[Elemento \<dialog>](https://html.spec.whatwg.org/multipage/interactive-elements.html#the-dialog-element)***
  - O elemento ****\<dialog>**** é um pop up com a finalidade de caixa de cadastro, login em algum serviço, etc... Vemos bastante em sites de noticias
  - Esse elemento tem uma sinergia com o elemento ***\<form>*** que quando tem a propriedade ***method="dialog"***, executa a função de fechar esse popup ao ser submitado.
  - Podemos abrir esse popup com javascript ou simplesmente setando a propriedade ***'open'*** dentro dessa tag.
  - exemplos se encontram na pasta [dialog](/chapter-02/dialog/example.html)
