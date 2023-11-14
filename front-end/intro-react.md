# ReactJS

Área do Conhecimento: Tecnologia
Referência: https://pt-br.reactjs.org/

> *ReactJS é uma biblioteca Javascript de código aberto para a construção de interfaces de usuário. O React é considerado uma SPA ao possibilitar o carregamento rápido das páginas utilizando componentes em sua estrutura.*
> 

<aside>
📋 Veja o que está sendo abordado aqui:

- **Tabela de conteúdo**
</aside>

<aside>
📌 Para saber mais sobre o Javascript, veja:

[JavaScript](https://www.notion.so/JavaScript-7c91901c1c214989822032d83d80632c?pvs=21)

</aside>

# Single-Page Application

São aplicações concentradas em uma visualização de uma única página.

Esse tipo de aplicação dá a sensação de estarmos navegando em uma aplicação desktop utilizando apenas uma única página e componentes, criando interações mais fluidas entre o usuário e a página.

Ao criar uma aplicação React estaremos sempre criando a noção de uma página única, onde montaremos componentes de acordo a nossa navegação.

# Iniciando um projeto React

No terminal devemos dar o comando de criação de um projeto, que criará uma pasta com os arquivos padrões dentro, ou seja, não é necessário criar uma pasta para inserir o projeto, pois o comando já fará isso:

```bash
npx create-react-app nome-do-projeto
```

Com esse comando estamos falando para criar um projeto de nome `nome-do-projeto` e que tenha um template de Typescript, que é um linguagem criado em cima do Javascript.

Para rodar o projeto é preciso entrar na pasta do projeto e rodar o comando:

```bash
npm start 
	// ou
yarn start
```

Por padrão, todos os projetos React atendem na porta :3000.

# O que é JSX e TSX?

Como definido, o React é uma biblioteca de Javascript, dessa forma o conceito de JSX e TSX vem para unir essa linguagem de programação com a linguagem de marcação HTML. Então podemos entender que o JSX e o TSX é uma extensão de sintaxe para o Javascript e o Typescript, respectivamente.

```jsx
const elemento = <h1>Olá, mundo!</h1>;
```

O React usa essa extensão para facilitar a organização do projeto que, ao invés de separarmos tecnologias em arquivos diferentes, conseguimos criar componentes e utilizar as tecnologias de uma forma que faz mais sentido para o momento de renderização do código. Não é obrigatório o uso do JSX ou TSX em um projeto React, porém ele é muito utilizado pela sua organização.

<aside>
📌 Para saber mais sobre o HTML, veja:

[HTML](https://www.notion.so/HTML-4b571e29c62f47db8a5af1be8fd61835?pvs=21)

</aside>

# Estrutura de pastas do React

Ao ser criado, o projeto React acompanha algumas pastas e arquivos organizados e prontos para usarmos. Alguns podemos excluir dependendo do nosso objetivo e outros são fundamentais para o funcionamento da nossa aplicação.

![https://miro.medium.com/max/800/1*eXN1LlNnuZmosJ7n7EsJ-Q.png](https://miro.medium.com/max/800/1*eXN1LlNnuZmosJ7n7EsJ-Q.png)

O arquivo `package.json` possui uma estrutura que declara as dependências usadas no nosso projeto e quais delas deverá ser instalada ao baixarmos o projeto em outra máquina. Essas dependências ficarão guardadas na pasta `node-modules/`, que não será manipulada mas é essencial pra o funcionamento. Em contrapartida, o arquivo `.gitignore` reune nomes de diretórios e arquivos que não subirão para o servidor pelo git.

A pasta `public/` reune informações essenciais da nossa página, como se fosse o `<head>` da nossa aplicação. Dentro dele temos informações de ícone e o `index.html` da nossa aplicação.

Dentro da pasta `src/`, o arquivo `index.tsx` executa o método que renderiza os códigos. O arquivo `App.tsx` é um exemplo de componente, que podemos criar diversos ao longo da necessidade do nosso projeto, e é dentro desse componente que organizamos o restante dos nossos componentes, criando a página única de modelo.

O `README.md` é um arquivo de documentação, que será muito útil para detalhar sobre o projeto no GitHub.

# Componentes

Os componentes trabalham como funções Javascript que aceitam entradas e retornam o que deve ser exibido no navegador. Ao criarmos componentes conseguimos separar as partes do nosso projeto para manipularmos cada parte independentemente e assim criar na prática o conceito de [**SPA**](ReactJS%20a5b35b74b7394b0497d1f29c97b68cdd.md).

Por padrão, os arquivos de componentes devem ser nomeados com a primeira letra maiúscula, por exemplo `Home.tsx`.

```jsx
function Home() {
  return (
    <div>Home</div>
  );
}

export default Home;
```

O método `return` retorna o elemento que queremos exibir em tela, caso queremos mostrar mais de um elemento é preciso colocar os elementos dentro de uma caixa (uma `<div>`, por exemplo, ou uma tag vazio `<> Home </>`).

Para que esse componente seja visualizado no navegador temos que exportá-lo através do `export default` e então adicioná-lo no arquivo `App.tsx` como `< Home />` e fazer sua importação.

A organização do nosso projeto fica a critério nosso e da equipe em que estamos trabalhando. No entanto é recomendado que todos os componentes fiquem reunidos em uma pasta chamada `components` e que dentro desta página os arquivos de código e de estilo fiquem reunidos dentro de uma outra pasta especificando qual componente é esse.

# Rotas

Para a criação de rotas no nosso projeto podemos utilizar a depedência react-router-dom através dos comandos:

```bash
npm install react-router-dom
	//ou
yarn add react-router-dom
```

E então inserir o comando a seguir no console também para instalar a utilização do router-dom:

```bash
yarn add @types/react-router-dom
```

# Model

A pasta de Model armazena os modelos do nosso banco de dados. Os arquivos contidos nele são os modelos, os objetos que vão conter os campos que farão a conexão com o banco de dados.

# O que acontece na Service?

A Service é a camada de serviço, onde acontece a regra de negócio do nosso projeto, como por exemplo a nossa API.

# Introdução a Hooks

**Hooks** são funções que nos permitem ligar aos *state* e ciclo de vida do React a partir de componentes funcionais. O estado (ou *state*) é uma propriedade do componente que possui valores e quando esses valores sofrem algum tipo de alteração, o componente é atualizado em tela, ou seja, ele é renderizado novamente.

## useState

Responsável por fazer o controle do estado de um componente. É um hook que nos permite adicionar um estado a um componente funcional, para então conseguirmos manipular os valores de estado de um componente.

O `useState` retorna dois valores: o valor do estado atual e uma função que permite atualizá-lo.

```jsx
const [count, setCount] = useState(0);
```

A forma declarada é chamada de desestruturação, onde montamos um array com os valores que são declarados para a variável. Nos permite atribuir diferentes nomes para as variáveis do estado que não fazem parte da API do `useState`.

## useEffect

Adiciona a funcionalidade de executar efeitos colaterais através de um componente funcional.

Ao chamarmos o `useEffect` estamos falando para o React executar sua função de efeito após liberar as mudanças para o DOM. Os efeitos são declarados dentro do componente, para que eles tenham acesso as suas *props* e *state*.

# Utilizando o Redux no seu projeto

É uma biblioteca independente do React, sendo possível utilizá-lo com outras ferramentas sem ser o React.

Seu objetivo é fazer um controle centralizado das mudanças de estado da aplicação, onde todos esses estados serão compartilhados em todos os componentes que quiserem fazer uso dele.

Para a sua instalação é necessário rodar o comando:

```bash
npm install redux react-redux
```

O Redux é composto pelas partes:

- O `reducer` que administra o estado e retorna um estado atualizado;
- A `action` que são uma parte da função do `reducer` e possui um `type`, que tem um identificador único, e um `payload`, que possui os dados;
- O `dispatch` que é criado todas as vezes que queremos enviar um dado de um evento, então sempre que um evento acontece nós enviamos este dado ao Redux.

## Criando um store.js

O `store` é um objeto do estado global, onde controla todos os estados da nossa aplicação.

É aqui que guardamos todas as informações que podem ser utilizadas por mais de um componente e a única forma de alterar o estado dentro dele é chamando o `dispatch` e a `action`.

```jsx
import { createStore } from 'redux';

const store = createStore(reducer);

export default store;
```

O `store` é guardado dentro de um arquivo chamado `store.js` também dentro de uma pasta `store/` na `src/` do projeto React.

É setado uma função `createStore` do próprio Redux que recebe como parâmetro o `reducer`, que por sua vez receberá outras partes do projeto.

No `index.js` é preciso importar o `Provider` para habilitar a utilização do `store` em toda a nossa aplicação.

```jsx
ReactDOM.render(
  <BrowserRouter>
    <Provider store={ store }>
      <App />
    </Provider>
  </BrowserRouter>,
  document.getElementById('root'),
);
```

## Entendendo o `reducer`

O `reducer` é uma função que aceita uma acumulação e um valor e retorna um novo acumulado. É usado para reduzir um coleção de valores para um único valor.

```jsx
const reducer = (state = { object }, action) => {
	return state;
}

export default reducer;
```

Como boa prática, criamos uma pasta chamada `reducers/` e criamos o nosso arquivo que guardará a função, podendo ser chamada de `index.js`.

O `reducer` recebe como parâmetros: um estado (`state`) que é um objeto, representando o estado inicial, e uma `action`, que será executado pela `store`; e retorna o estado.

useSelector() é um custom hook que permite extrair o dado da store usando uma função de seleção, é equivalente ao mapStateToProps argumentando com o connect.

The selector will be called with the entire Redux store state as its only argument. The selector will be run whenever the function component renders (unless its reference hasn't changed since a previous render of the component so that a cached result can be returned by the hook without re-running the selector). `useSelector()`
 will also subscribe to the Redux store, and run your selector whenever an action is dispatched.

## Entendendo o `dispatch`

Utilizando o useDisptach custom hook do react-redux criamos o dispatch que cuidará dos dados enviados.

```jsx
import { useDispatch } from 'react-redux';

const dispatch = useDispatch();
dispatch(action);
```

# Estilizando o nosso projeto em React

Ao se tratar de estilização podemos utilizar diversas ferramentas para nos auxiliar. Temos bibliotecas que vão nos ajudar na gestão do tempo como o Bootstrap e o Material UI, e outras ferramentas que dinamizam a disposição do CSS como o styled-components. Mais uma vez, a ferramenta certa para o projeto fica à critério da equipe ou das nossas necessidades.

<aside>
📌 Para saber mais sobre o CSS e suas bibliotecas, veja:

[CSS](https://www.notion.so/CSS-e84b73253edf402ea4c064116b5681e9?pvs=21)

[**Material UI**](https://mui.com/getting-started/installation/)

**[Bootstrap](https://getbootstrap.com/docs/5.1/getting-started/introduction/)**

**[styled-components](https://styled-components.com/docs)**

</aside>

[Links](ReactJS%20a5b35b74b7394b0497d1f29c97b68cdd/Links%20343e0dc6d6174395b37a5f0365775b8b.md)