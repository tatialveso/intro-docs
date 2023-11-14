<h1 align="center">Introdução ao CSS</h1>

> *CSS significa **Cascading Style Sheet**, que quer dizer Folha de Estilo em Cascata. É utilizada para descrever a aparência da linguagem de marcação HTML a partir de regras formada por propriedades e valores, ou seja, o CSS é toda a parte visual e estilizada do nosso site.*
>

# 🩻 Estrutura básica do CSS
Essencialmente, uma regra CSS é composta pelas seguintes partes:

```css
seletor {
	propriedade: valor;
}
```

- O `seletor` se refere ao elemento HTML que deseja ser alterado ou formatado;
- A `propriedade` é o que deve ser modificado;
- O `valor` é o resultado que queremos no elemento.

# ✍️ Comentários no CSS
É possível fazer comentários no nosso código, servindo de apoio para nos comunicarmos entre equipe e indicar partes do nosso código ou para ocultar algo do código que não queremos que seja exibido no navegador.

O comentário é feito pela indicação `/* */` , sendo o comentário escrito entre os sinais.

# Como devemos unir HTML e CSS?

Para que as regras do CSS sejam implementadas no HTML precisamos referenciá-lo no documento HTML. Existem três formas de fazer isso:

- **CSS Inline**
    
    A regra é informada dentro da tag de abertura do elemento desejado no arquivo HTML.
    
    ```html
    <tag style="propriedade: valor">
    ```
    

- **CSS Interno**
    
    A regra é informada dentro de uma tag `<style>` no `<head>` do documento HTML.
    
    ```html
    <style>
    	seletor {
    		propriedade: valor;
    	}
    </style>
    ```
    

- **CSS Externo**
    
    Cria-se um documento com .css e com um link no `<head>` se referencia esse documento CSS no documento HTML.
    
    ```html
    <link rel="stylesheet" href="style.css">
    ```
    

A melhor forma de utilizar a referência CSS vai de acordo com cada projeto. Por exemplo, um projeto com diversas páginas mas que possuem formação igual pede por um **CSS Externo**, pois podemos usar uma única regra CSS para diversas páginas HTML; enquanto uma mudança em uma única página com regras específicas pode ser usada o **CSS Interno**.

# Seletores CSS

Os seletores são identificadores dos elementos HTML que queremos formatar ou alterar de acordo com as regras CSS implementadas.

Os seletores básicos podem ser separados por três categorias:

- **Seletores de tag**
    
    O indicado no seletor é a tag HTML. As regras ditadas são implementadas em todas as tags iguais existentes no arquivo.
    
    ```css
    p {
    	font-size: 20px;
    }
    ```
    

- **Seletores de id**
    
    O indicado no seletor é um id, que é um atributo HTML com o valor sendo um nome customizado. As regras ditadas são implementadas no elemento específico com este ID.
    
    ```css
    #contato {
    	color: #ff0000;
    }
    ```
    

- **Seletores de classe**
    
    O indicado no seletor é uma classe, que é um atributo HTML `class` com o valor sendo um nome criado. As regras ditadas são implementadas em todos os elementos que possuem esse atributo.
    
    ```css
    .titulo {
    	text-align: center;
    }
    ```
    

É sempre preferível utilizar classe do que id, uma vez que o id pode ser utilizado em apenas um único elemento. Ele é um identificador único, enquanto a classe agrupa diferentes elementos que possuem a mesma formatação, podendo ser utilizado mais de uma vez.

## Pseudo-seletores

São usados para definir o estado de formatação de um elemento ao acontecer um evento.

```css
seletor:pseudo-seletor {
	propriedade: valor;
}
```

Alguns dos mais usados pseudo-seletores são o `:hover`, que determina as regras do elemento quando o mouse for passado pelo elemento e o `:focus`, que é quando o foco estiver no elemento (quando clicado por exemplo).

# Propriedades CSS

## Cor

As cores são modificadas através da propriedade `color`, que podem ter um valor hexa, rgb, rgba, hsl ou hsla.

## Texto

Algumas propriedades são usadas para formatar o texto dos elementos. O `text-align` altera o alinhamento do texto, seja ele centralizado, justificado ou para os lados.

O `text-decoration` determina a decoração do texto, é usado para colocar sublinhado ou risca no texto. Enquanto o `text-transform` determina se o texto será em caixa alta ou em letras minúsculas.

## Largura e altura

O `height` e o `width` determina a altura e a largura do elemento respectivamente, podendo ser setados por diversas unidades de medida dependendo da responsividade e tela apropriada.

## Fundo

Há algumas propriedades que podemos utilizar para formatar o fundo da página.

O `background-color` especifica qual a cor do fundo de um elemento, que pode ter os mesmos valores da propriedade `color`.

O fundo de um elemento também pode ser uma imagem, que é identificada pela propriedade `background-imagem`, onde passamos `url("#")` e o caminho ou link dessa imagem. Podemos setar os padrões da imagem com propriedades como `background-size` para o preenchimento, `background-repeat` para a repetição e `background-position` para posição.

## Fonte

As propriedades de fonte estão ligadas com a aparência da fonte, enquanto as de texto são voltadas para uma aparência geral dos elementos que possuem texto.

A propriedade `font-family` altera o tipo de fonte, podendo ser usado fontes nativas do navegador ou fontes importadas de lugares externos como o Google Fonts.

Já o `font-weight` determina a espessura da fonte, como o negrito; enquanto o `font-style` determina o estilo da fonte como o itálico.

Outras propriedades CSS podem ser acessadas [**neste link**](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference).

# CSS Box Model

No HTML todos os elementos podem ser considerado caixas. No CSS, esses elementos podem ser formatados e alterados de acordo com o modelo de caixa (box model). 

![https://miro.medium.com/max/725/1*FqGQIGmGdW5EetfS3HFkvA.png](https://miro.medium.com/max/725/1*FqGQIGmGdW5EetfS3HFkvA.png)

O modelo de caixa utiliza três propriedades que altera o em torno do elemento. O conteúdo em si do elemento pode ser alterado com as propriedades de altura e largura.

O `padding` é a área de preenchimento dentro do elemento, entre o conteúdo e a borda. O `border` é a borda do elemento, que separa o padding e a margem. A `margin` é a distância entre um elemento e o outro.

Tanto o `padding` quanto a `margin` podem ter o mesmo valor dos quatro lados, ou dois valores determinando o primeiro para o `top` e o `bottom` e o segundo para o `left` e `right`, ou quatro valores determinando o `top`, `right`, `bottom` e `left` respectivamente.

Já o `border` é usado com três valores, onde o primeiro determina a espessura da borda, o segundo a forma da borda e o terceiro a cor da borda.

# CSS Display

A propriedade `display` controla o layout da página, ou seja, ela determina a disposição dos elementos de uma página, auxiliando na visualização do site.

## Flexbox

Ao determinar um elemento com `display: flex` fazemos com que seus filhos sejam itens flex, o que os fazem serem formatados com outras propriedades que irão auxiliar na sua disposição. Com o flexbox damos a liberdade para os elementos filhos se organizarem com mais liberdade.

Com o `flex-direction` determinamos a direção dos elementos filhos, seja em coluna ou linhas, reversas ou não. O `flex-wrap` determina a quebra de linha dos elementos, sendo que por padrão eles não quebram a linha, ou seja ultrapassam o fim do elemento pai e quando são `flex-wrap: wrap` eles se organizam para quebrarem a linha e se organizarem com o espaço do elemento pai.

O `justify-content` alinha a disposição dos elementos filhos (itens flex) dentro do espaço do elemento pai. O `align-items` alinha os itens dentro do elemento flex, enquanto o `align-content` alinha os itens dentro do elemento flex na vertical. Já o `align-self` alinha um item flex específico dentro do elemento flex.

## Grid

O `display: grid` oferece um layout da página a base de grade.

Com o `grid-template-columns` determina o número total de colunas na grid, podendo ser calculadas individualmente ou usado a função `repeat(x, y)` onde será determinado o total de colunas e depois o tamanho de todas as colunas. O `grid-template-rows` determina o número total de linhas da grid. Outra alternativa é o `grid-template-areas`, que define áreas específicas da grade. O `gap` determina o espaço entre um elemento e o outro dentro da grade.

# Media Query

A Media Query é um conjunto de regras CSS que permite a página se adaptar a diferentes tamanhos de telas conforme determinado dentro da regra. Para a utilização da `@media` é preciso determinar se a página será *Mobile First* ou *Desktop First*, ou seja, se o padrão do projeto será feito para dispositivos móveis (*Mobile First*) ou telas grandes (*Desktop First*).

```css
@media (tamanho: valor) {
	seletor {
		propriedade: valor;
	}
}
```

Na estrutura da media query determinamos o tamanho da tela que as regras ali dentro começarão a ser obececidas. O tamanho pode ser `min-width`, que são usadas para quando o tamanho padrão seja *mobile first*, ou `max-width`, quando as regras padrões são *desktop first*.

Dentro dos colchetes da `@media`, seguimos com a estrutura básica da regra comum de CSS, então quando a tela aumentar ou diminuir os elementos serão modificados. Lembrando que não é preciso reescrever todas as regras do CSS, apenas reescrever aquelas que mudarão conforme a tela.

# Unidades de Medida CSS

Existem dois tipos de unidades de medida dentro do CSS, medidas absolutas e relativas. A segunda são ótimas para a questão da responsividade, uma vez que ela se adapta ao tamanho da tela que a página está.

## Medidas relativas

### Ems (em)

O `em` altera o valor da fonte do elemento filho de acordo com o tamanho da fonte do elemento pai, ou seja, se o elemento pai possui `font-size: 16px` e determinarmos que o elemento filho seja `font-size: 2em`, significa que o elemento filho terá `32px` (16px x 2).

### Porcentagem (%)

A porcentagem está relacionada com o tamanho do elemento e quanto espaço ele irá ocupar de acordo com o tamanho padrão do seu elemento e também o tamanho total da tela. É usado muito para responsividade, pois se adapta aos tamanhos da tela.

### Root em (rem)

Diferentemente do `em`, que está diretamente ligado ao elemento pai, o `rem` está relacionado com o elemento raiz do HTML. Por padrão, uma página HTML tem `font-size: 16px` então qualquer elemento dentro do nosso `<html>` que for manipulado com o valor rem estará sendo baseado nesse valor padrão, ou se mudarmos o valor da tag raiz será relacionado ao valor setado.

### Viewport Width (vw)

As medidas baseadas em viewport são novas medidas criadas para aumentar a responsividade e acessibilidade de uma página, pensada para a adaptação entre telas grandes e telas pequenas. O viewport significa a área visível da tela para o usuário.

O `vw` está relacionado ao tamanho da largura da área visível, onde 1vw = 1% da largura da área visível. E qual é a diferença entre o `vw` e o `%`? A `%` está relacionado ao tamanho do elemento em si ou de seu pai, enquanto o `vw` está relacionado a área vísivel da tela.

### Viewport Height (vh)

As medidas baseadas em viewport são novas medidas criadas para aumentar a responsividade e acessibilidade de uma página, pensada para a adaptação entre telas grandes e telas pequenas. O viewport significa a área visível da tela para o usuário.

O `vh` está relacionado ao tamanho da altura da área visível, onde 1vh = 1% da altura da área visível. E qual é a diferença entre o `vh` e o `%`? A `%` está relacionado ao tamanho do elemento em si ou de seu pai, enquanto o `vh` está relacionado a área vísivel da tela.

## Medidas absolutas

### Pixel (px)

Por padrão, o tamanho de referência de uma página é `16px` sendo modificado no `font-size`. Por ser um valor absoluto, independentemente da tela o valor é o mesmo, podendo distorcer o resultado final da página.