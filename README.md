# RPG Crítico

## Descrição

**RPG Crítico** é um projeto de _front-end_ estático que simula uma página web (blog/portal) focada em notícias e análises de RPGs de mesa. O layout foi desenvolvido com foco em semântica HTML5, organização CSS3 moderna e responsividade, adaptando-se a diferentes tamanhos de tela.

A página é organizada para destacar os artigos principais (notícias e análises), fornecer conteúdo secundário (relacionados) e permitir interação do usuário (através de um formulário de contato).

---

## Tecnologias Utilizadas

O projeto foi construído utilizando as seguintes tecnologias:

- **HTML5:** Para a estruturação semântica do conteúdo.
- **CSS3:** Para a estilização, layout e responsividade.

---

## HTML5 (Estrutura e Semântica)

O HTML foi estruturado com foco total em **semântica**, garantindo que o documento seja acessível e facilmente interpretado por navegadores e leitores de tela.

> A estrutura principal divide a página em `<header>`, `<main>` e `<footer>`, delimitando o cabeçalho principal, o conteúdo principal e o rodapé da página.

As principais tags e sua lógica de uso são:

- **`<main>`:** Envolve todo o conteúdo central (notícias, análises, barra lateral e formulário), separando-o do cabeçalho e do rodapé.
- **`<section>`:** Utilizada para agrupar os blocos temáticos principais: "Novidades" (`#news`), "Análises" (`#reviews`) e "Contato" (`#contact`).
- **`<article>`:** Usada para encapsular cada notícia, análise ou item relacionado. Isso é semanticamente ideal, pois cada um desses blocos é um conteúdo independente que poderia ser distribuído isoladamente (como em um feed RSS).
- **`<header>` e `<footer>` (aninhados):** Dentro de cada `<article>`, tags `<header>` e `<footer>` são usadas para delimitar o cabeçalho do artigo (título e subtítulo) e seu rodapé (autor e data).
- **`<aside>`:** Agrupa o "Conteúdo Relacionado" (`#extra-content`), pois é um conteúdo tangencial ao fluxo principal de notícias e análises.
- **`<figure>` e `<figcaption>`:** Utilizadas para associar imagens de destaque (como capas de livros) às suas respectivas legendas.
- **`<nav>`:** Contém a navegação principal do site, com links de âncora que levam às seções da página.
- **`<details>` e `<summary>`:** Usadas nas análises para criar um _accordion_ ("Ver mais detalhes"), permitindo ao usuário expandir o conteúdo sem poluir a interface, usando apenas HTML nativo.
- **`<form>` e `<fieldset>`:** O formulário de contato é estruturado agrupando os campos (`<input>`, `<textarea>`) com suas `<label>`s dentro de um `<fieldset>` para melhor organização e acessibilidade.
- **`<address>`:** Utilizada no rodapé principal para fornecer informações de autoria do desenvolvedor da página.

---

## CSS3 (Estilização e Layout)

O CSS foi organizado de forma modular e escalável, seguindo uma abordagem _de cima para baixo_ (do global para o específico).

1.  **Importação de Fontes:** A fonte "DM Sans" é importada do Google Fonts.
2.  **Variáveis CSS (`:root`)**: O _design system_ é centralizado em variáveis (ex: `--color-primary`, `--base-shadow`, `--border-radius-main`). Isso facilita a manutenção e a alteração de temas, pois as cores, sombras e bordas principais estão definidas em um único lugar e são reutilizadas em todo ostylesheet com `var()`.
3.  **Reset Global e Padrões (`*`, `body`, `h1`, etc.)**: Uma pequena normalização é aplicada (`box-sizing: border-box`), e os estilos base de tipografia e elementos são definidos.
4.  **Layout Principal (`header`, `main`, `footer`)**: Estruturação macro da página.
5.  **Componentes Específicos**: Estilização de componentes reutilizáveis, como os _cards_ (`.news`, `.review`), o formulário (`.contact`) e a barra lateral (`.extra-content`).
6.  **Media Queries**: No final do arquivo, as regras de responsividade ajustam o layout para _tablets_ (`@media (max-width: 900px)`) e _dispositivos móveis_ (`@media (max-width: 600px)`).

### Técnicas de Layout

- **CSS Grid:** É a principal ferramenta de layout para as seções de conteúdo. O `.main-news` (2 colunas) e o `.reviews` (3 colunas) usam `display: grid` para criar os _layouts_ de "card". O próprio `<header>` principal usa Grid para alinhar o logo à esquerda e a navegação à direita. Nas _media queries_, o número de colunas do grid é alterado para `1fr` para empilhar o conteúdo em telas menores.
- **Flexbox:** É usado apenas nos _cards_ (`.news`, `.review`) com `flex-direction: column`. Isso permite que o rodapé do _card_ (`.news-footer`) seja alinhado perfeitamente na parte inferior, independentemente da altura do conteúdo, usando `margin-top: auto`.

### Seletores

O CSS utiliza uma variedade de seletores, priorizando **classes** para componentes (`.nav-item`, `.form-group`, `.card`). Também são usados seletores de tipo (`h2`, `textarea`), IDs para elementos únicos (`#main-header-logo`), seletores de atributo (`input[type="text"]`) e pseudo-classes (`:hover`, `:focus`) para garantir interatividade visual.

---

## Autor

Desenvolvido por **Roger Marllus Oliveira Leal**.
