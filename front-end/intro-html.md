<h1 align="center">Introdução ao HTML</h1>

> *HTML significa **HyperText Markup Language**, que quer dizer Linguagem de Marcação de Hipertexto. Se refere à estrutura de uma página web, ou seja, o HTML é o esqueleto de uma página composta por elementos e informações que serão mostradas em um navegador ao ser acessado.*
> 

# 🩻 Estrutura básica do HTML
A estrutura básica do HTML é composta pela seguinte sequência de códigos:
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset=”utf-8”>
		<title>Meu site</title>
	</head>
	<body>
		Olá, Mundo!
	</body>
</html>
```

- A declaração `DOCTYPE` que é uma declaração para o navegador informando qual versão do HTML estamos usando nesta página;
- A tag `<head>` reune todas as informações da minha página. Ela não será exibida no navegador, mas é de extrema importante para a página ser mostrada no mesmo;
    - Dentro desta tag temos a linha `<meta charset=”utf-8”>` que informa a codificação de caracteres que estamos usando na nossa página;
- A tag `<body>` reune toda a parte visível da nossa página, ou seja, tudo o que o navegador mostrará estará disposto dentro dessa tag;

A estrutura de uma tag pode ser escrita da seguinte forma:

```html
<tag atributo="valor"> ... </tag> 
```

A maioria das tags possuem uma abertura e um fechamento, porém existem algumas que não possuem fechamento, como a tag `<img>` . Podemos também setar atributos dentro das nossas tags, que sempre estarão na tag de abertura, que possuem objetivos diferentes.

# ✍️ Comentários no HTML

É possível fazer comentários no nosso código, servindo de apoio para nos comunicarmos entre equipe e indicar partes do nosso código ou para ocultar algo do código que não queremos que seja exibido no navegador.

O comentário é feito pela indicação `<!--  -->` , sendo o comentário escrito entre os sinais.

# *️⃣ Elementos HTML
Um elemento HTML é composto por tags, seus atributos e informações.

As tags são palavras-chaves que informa a formatação ou o propósito daquela informação dentro da página. Toda informação de um site está posicionada dentro de uma tag, que só é visível quando pegamos o código-fonte da nossa página.

Temos a seguir alguns elementos essenciais para montar uma página web.

## Cabeçalhos de texto

Os cabeçalhos formatam títulos e subtítulos de uma página que vão de `<h1>` a `<h6>`, sendo da maior para a menor.

Por boas práticas, usamos a tag de título `<h1>` apenas uma única vez por página e podemos repetir as demais quantas vezes necessário, porém é importante respeitar a sua hierarquia.

## Links e ancoragem

A tag `<a>` é usada para informar um link, onde possui um atributo `href` que é passado o link ou o caminho para a informação desejada.

Além de links e páginas, a tag também liga outros tipos de informação como e-mail e número de telefone.

Existem duas formas de passar um endereço para uma nova página:

- **Caminho absoluto** que utiliza um link externo como, por exemplo, `<a href=”https://google.com”>Google</a>`.
- **Caminho relativo** que utiliza um caminho interno para chegar até a página como, por exemplo, `<a href=”./contato.html”>Contato</a>`.

## Lista ordenada

Existem duas formas de criarmos listas, uma delas é a lista ordenada.

Com a tag `<ol>` criamos uma lista de itens enumerados, que são indicados pela tag `<li>` .

## Lista não-ordenada

A segunda forma de criar uma lista é com a `<ul>`, que indica uma lista não-ordenada.

Esse tipo de lista indica informações que não possuem uma ordem específica, sendo usado marcadores de bullet por exemplo. Os itens também são indicados pela tag `<li>`.

## Tabela

Uma tabela é formada por um conjunto de tags que determinam suas colunas e linhas.

A tabela deve ser iniciada pela tag `<table>`, cada linha da tabela fica reunida dentro da tag `<tr>`, enquanto o cabeçalho da tabela é identificado por `<th>` e os dados da tabela é formado pela tag `<td>`. 

```html
<table>
	<tr>
		<th>Primeiro nome</th>
		<th>Sobrenome</th>
	</tr>
	<tr>
		<td>John</td>
		<td>Doe</td>
	</tr>
</table>
```

## Paragráfos e textos

Podemos englobar um texto dentro de uma tag `<p>`, que indica um paragráfo. Por padrão, a sua configuração é em bloco.

A tag `<span>` usamos para englobar textos, mas a sua formatação se apresentará de forma inline (em linha).

## Imagens

A tag `<img>` invoca uma imagem para ser usada dentro da página web.

Ela possui dois atributos: o `src`, que possui o caminho ou link para a imagem, e o `alt`, que usamos para descrever a imagem, utilizado para acessibilidade e para o caso de uma imagem inexistente.

## Formulário

Criado pela tag `<form>`, o formulário possui um conjunto de elementos que o forma.

O elemento `<label>` mostra a legenda do propósito do input, e o `<input>` é uma tag sem fechamento que mostrará no navegador o campo de escrita do formulário. O `<button>` finaliza o formulário, que corresponde ao botão de envio.

Um formulário pode ter também um `<textarea>`, que mostra um grande campo para ser enviado mensagens maiores com mais de uma linha.

```html
<form>
	<label>Nome</label>
	<input type="text" placeholde="Insira seu nome">
	
	<label>Mensagem</label>
	<textarea rows=5 cols=20></textarea>
	
	<button>Enviar</button>
</form>
```

# 🔮 HTML Semântico

A semântica no HTML significa implementar elementos que significam algo para o navegador e para a pessoa desenvolvedora. Por exemplo, um elemento `<p>` está claro que determina um paragráfo, sendo um elemento semântico, enquanto a `<div>` ou o `<span>` não são um elemento semântico.

<div align="center"><img src="https://i.stack.imgur.com/fzLpL.png"/></div>

Com o HTML semântico, a página não fica apenas mais legível para o navegador ou ajuda na organização da equipe desenvolvedora, ele também ajuda na leitura de dispositivos de acessibilidade como leitores de telas para pessoas com deficiência visual. Outra vantagem desse HTML é a classificação do site em buscadores de pesquisa, como o Google, onde o algoritmo identifica as informações relevantes daquele site de acordo com os elementos que possuem um significado importante.

O DOM com a semântica fica mais clara, onde conseguimos determinar o cabeçalho `<header>`, o menu de navegação `<nav>`, o rodapé `<footer>` e o conteúdo principal `<main>`, e inserimos outros elementos semânticos de menor valor dentro desses elementos maiores.

Outros elementos HTML com ou sem semântica pode ser acessado [**neste link**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element).

## A diferença entre `<section>` e `<article>`?

O `<article>` representa uma parte independente da página web, ou seja, fora do contexto da página, o conteúdo dentro desta tag ainda faz sentido. Por exemplo, uma notícia ou uma postagem de blog estaria dentro do elemento `<article>` onde dentro dele estaria cabeçalhos de texto e poderia conter outras tags e uma `<section>`.
A `<section>` é uma seção genérica semântica da nossa página. Ele pode ser um capítulo ou uma informação de contato da página. Ele também pode estar contida dentro de uma tag `<article>` ou pode conter esta tag dentro dele. A forma não-semântica desta tag é a `<div>`.
