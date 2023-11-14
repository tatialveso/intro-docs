# JavaScript

Área do Conhecimento: Tecnologia
Referência: https://developer.mozilla.org/en-US/docs/Web/JavaScript

> *Javascript é uma linguagem de programação que permite a introdução de complexidade nas páginas web, pensando na interação entre usuário e página, ou seja, ao inserirmos o Javascript transformamos nossas páginas HTML em páginas dinâmicas.*
> 

<aside>
📋 Veja o que está sendo abordado aqui:

- **Tabela de conteúdo**
</aside>

# Comentários em Javascript

É possível fazer comentários no nosso código, servindo de apoio para nos comunicarmos entre equipe e indicar partes do nosso código ou para ocultar algo do código que não queremos que seja exibido no navegador.

Existem dois tipos de maneiras de criar comentários no nosso código. O primeiro é o comentário por linha que é sinalizado por `//` antes da frase de comentário; e o segundo é por `/* */` , onde colocamos o comentário entre os sinais.

# Declarações

Existem três formas de declarar valores no nosso código:

- **Variável Global**
    
    Com a variável `var` inicializamos um valor que será possível manipular em toda a nossa aplicação, pois é global, o que significa que engloba todo o escopo do projeto.
    

- **Variável Local**
    
    Já a variável `let` conta apenas para o escopo em que se é inserido, devendo ser setado novamente quando for inserido em um novo escopo.
    

- **Constante**
    
    Com o `const` criamos um valor constante, ou seja, que não pode ser alterado ou modificado.
    

# Tipos de dados e Estrutura

Dentro do Javascript conseguimos manipular certos tipos de dados, entre eles:

| boolean | true e false |
| --- | --- |
| null | valor nulo |
| undefined | valor indefinido |
| number | número |
| string | frase ou palavra entre aspas |
| object | objetos |

O Javascript é uma linguagem dinamicamente tipada, ou seja, temos mais liberdade para manipular os dados. Dessa forma, não precisamos identificar o tipo de dado ao declarar uma variável ou constante.

```jsx
let number = 12;
number = "Doze";
```

Devido essa dinamicidade da linguagem conseguimos criar operações matemáticas entre diferentes tipos de dados.

```jsx
let number = 12;
let text = "A resposta é ";

textNumber = "A resposta é " + 12;  // A resposta é 12
```

Conseguimos também criar Arrays, que são conjunto de dados armazenados em uma variável. Dentro desse array conseguimos armazenar diferentes tipos de dados que podem ser resgatados pelo escopo do projeto.

```jsx
let ourArray = ["Maria", 23, false];
```

# Tipos de laços

Com laços conseguimos executar repetições e impressões de forma mais rápida e economizando linhas de código, tornando-as dinâmicas.

## Laço de repetição

Com os laços de repetição criamos um *loop*, ou seja, imprimimos valores de acordo com a condição e enquanto a condição for verdadeira. Existem algumas formas de criar um repetição em nosso código

- **While**
    
    Executa uma ação enquanto a condição for verdadeira.
    
    ```java
    while(condição) {
    	// faça isso;
    }
    ```
    

- **Do While**
    
    Executa uma ação até que a condição seja falsa.
    
    ```java
    do {
    	// faça isso;
    } while(condição);
    ```
    

- **For**
    
    Repete uma ação enquanto a condição for verdadeira.
    
    ```java
    for(inicio; condição; incremento) {
    	// faça isso;
    }
    ```
    

## Laço condicional

Os laços condicionais são um conjunto de ações ou cálculo que são executados caso uma condição for verdadeira e então podemos inserir uma outra ação ou cálculo se ela for falsa. Podemos criar uma condição de duas formas:

- **If Else**
    
    Executa uma ação para caso a condição for verdadeira e outra, caso ela seja falsa. Podemos criar uma outra condição dentro de uma outra condição.
    
    ```jsx
    if(condição) {
    	// faça isso
    } else {
    	// faça isso
    }
    ```
    
    Temos também a possibilidade do If Ternário, que é uma forma simplificada de criar uma condição `if else` da seguinte forma:
    
    ```jsx
    condição ? seVddFaçaIsso : seFalsaFaçaIsso
    ```
    

- **Switch**
    
    Avalia uma expressão e tenta associar o seu valor com os enunciados de cada caso para então executar a ação ou calcular o seu valor se encontrar o correspondente.
    
    ```jsx
    switch(expressao) {
    	case enunciado_1:
    		// declaração
    	case enunciado_2:
    		// declaração
    	case enunciado_3:
    		// declaração
    	default:
    		// declaração padrão
    }
    ```
    

# Como podemos unir Javascript e HTML?

Para que os eventos do Javascript seja implementado no HTML do nosso projeto devemos inserir um `<script>` no final da tag `<body>` de modo em que a última informação antes da tag de fechamento do corpo do nosso site seja a indicação do Javascript. Existem também duas formas de referenciar o código JS no HTML:

- **Javascript Interno**
    
    Criamos uma tag com abertura e fechamento `<script>` e dentro delas colocamos todo o nosso código Javascript. Dessa forma, o código inserido na página será implementado apenas nessa página e só será possível utilizar em outras se for copiado e colado nas páginas desejadas.
    
    ```html
    <script>
    	// código javascript
    </script>
    ```
    

- **Javascript Externo**
    
    Criamos um arquivo .js e referenciamos esse arquivo em uma tag `<script>`. Com o externo, podemos referenciar o arquivo .js em qualquer página HTML que quisermos, economizando linha de código e tempo da pessoa desenvolvedora.
    
    ```html
    <script src="script.js"></script>
    ```
    

<aside>
📌 Para saber mais sobre o HTML e o CSS, veja:

[HTML](https://www.notion.so/HTML-4b571e29c62f47db8a5af1be8fd61835?pvs=21)

[CSS](https://www.notion.so/CSS-e84b73253edf402ea4c064116b5681e9?pvs=21)

</aside>

# Funções em Javascript

Funções são blocos de construção que possuem um conjunto de instrução que executa uma tarefa ou calcular um valor. A estrutura básica de uma função no Javascript acontece da seguinte forma:

```jsx
function nome(parâmetros) {
	//instrução ou cálculo;

	return;
}
```

Toda função é sinalizada pela palavra reservada `function` que recebe um `nome` criado e `parâmetros` entre os parênteses (mas atenção: nem toda função possui um parâmetro). Entre as chaves colocamos então as nossas instruções ou cálculos e no final damos um `return` para retornar o resultado desejado.

Quando queremos chamar essa função em alguma parte do nosso código, precisamos invocá-la usando o seu nome e o parâmetro (caso não tenha nenhum, usar o parênteses vazio): `nome(parâmetros) ou nome()`.

## Expressões de funções

Além da declaração da função, que é a forma tradicional de criar uma função, podemos setar uma função através da expressão. Também chamada de função anônima.

```jsx
const nome = function(parâmetros) {
	// instrução ou cálculo
}

nome()
```

Dentro das expressões temos também a **arrow functions**.

```jsx
const nome = (parâmetros) => {
	// instrução ou cálculo
}
```

## Escopo

O escopo da função é o momento em que as instruções ou cálculos estão posicionados dentro de cada função.

```jsx
let numeroFora = 2;

function soma() {
	let numeroDentro = 4;
	
	return numero + numero;
}
```

Seguindo o exemplo ao lado, o `numeroFora` faz parte do escopo global do código, enquanto o `numeroDentro` faz parte do escopo da função, ou seja, do escopo local da função.

A forma como [declararemos nossas variáveis](JavaScript%207c91901c1c214989822032d83d80632c.md) irá afetar o resultado também do nosso escopo.

# Eventos em Javascript

São um conjunto de ações que um elemento HTML realiza, muitas vezes gatilhado por uma ação do usuário navegando a página. Esses eventos se transformam em atributos no nosso arquivo HTML dentro da tag de abertura do elemento que se deseja alterar durante o evento. Abaixo temos alguns eventos que conseguimos inserir no nosso projeto:

| onBlur | remove o foco do elemento |
| --- | --- |
| onChange | altera o valor do elemento |
| onClick | altera o valor quando o elemento for clicado |
| onFocus | altera o valor quando o elemento for focado |
| onKeyPress | altera o valor quando o elemento for pressionado pela tecla |
| onLoad | altera o valor quando o elemento for carregado |
| onMouseOver | define ação quando passa o mouse sobre o elemento |
| onMouseOut | define ação quando retira o mouse sobre o elemento |
| onSubmit | define a ação quando um formulário for enviado |

Outros eventos podem ser acessados [**neste link**](https://developer.mozilla.org/pt-BR/docs/Web/Events).

Existe três formas de inserir os eventos ao código:

- Fazendo o chamamento do evento dentro do elemento HTML
    
    ```html
    <button onclick="facaAlgo()">
    	Entrar
    </button>
    ```
    

- Alterando a propriedade do elemento dentro do Javascript
    
    ```jsx
    elemento.onclick = facaAlgo();
    function facaAlgo(e) {
    	// faça algo
    }
    ```
    

- Utilizando o addEventListener e chamando a função no Javascript
    
    ```jsx
    elemento.addEventListener(
    	'click',
    	facaAlgo()
    );
    ```
    

Conseguimos remover um evento com o `removeEventListener`.

# Orientação a Objeto com JavaScript

# DOM no Javascript

![https://dkrn4sk0rn31v.cloudfront.net/uploads/2021/04/arvore-dom.png](https://dkrn4sk0rn31v.cloudfront.net/uploads/2021/04/arvore-dom.png)

O DOM significa Document Object Model (Modelo de Objeto de Documento) e representa a página web dentro do Javascript. Ao alterar algo da nossa página pelo Javascript estaremos alterando o modelo do documento e não o documento em si.

A página é representada pelo DOM através desse esquema, onde a nossa janela possui três elementos: `location`, `document` e `history`. O `document` contém a nossa página HTML esquematizada.

Todas as páginas web são uma árvore e é dessa forma que ela é interpretada pelo navegador, sendo organizados a partir das tags HTML.