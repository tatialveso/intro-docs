<h1 align="center">Introdução ao ExpressJS</h1>

> *O Express é um framework de aplicação web para a criação de servidores utilizando Javascript e sendo o framework mais utilizado do ecossistema do node.js.*
> 

O Express tem como objetivo criar servidores e trabalhar com requisições dentro do ecossistema do node.js de uma forma mais otimizada.

A tecnologia faz parte do **MERN Stack**, que é o conjunto de tecnologias que completa a produção full stack de uma aplicação envolvendo MongoDB, Express, React e Node.

# 🪅 Criando um servidor com `express`

Dentro da pasta do projeto escolhido, rode no terminal o seguinte comando

```bash
npm init --yes
npm install express
```

Este comando irá gerar um arquivo `package.json` e depois podemos dar o comando de instalação do `express`. Abra o arquivo e insira, antes do fechamento do objeto, a informação `“type”: “module”` para que consigamos importar e exportar informações.

Crie um arquivo chamado `app.js` e passe o seguindo código

```jsx
import express from 'express'

const app = express()
app.use(express.json())
```

Ao importar o `express` conseguimos criar requisições mais otimizadas e de forma mais simples do que se montassemos na mão. Agora sempre que formos chamar os métodos existentes da nossa dependência chamaremos diretamento o `app`.

Abaixo habilitamos para que o `app` consiga interpretar informações que chegam em `JSON`.

## Setando as rotas

No back-end ao setarmos rotas estamos dizendo ao servidor o que fazer quando receber uma requisição.

Duas informações devem ser passadas em uma requisição: a `URL`, que é o caminho que será acessada, e o `método`, que será o verbo que definirá o tipo de requisição que estaremos fazendo.

Crie uma pasta chamada `routes` e dentro dela crie um arquivo com o nome do objeto que estaremos manipulando mais `.routes.js`. Dentro de cada arquivo iremos agrupar as requisições relacionada àquele grupo, por exemplo, se estamos lidando com usuários iremos deixar todas as requisições (o CRUD) para manipular os usuários dentro do mesmo arquivo chamado `usuarios.routes.js`.

```jsx
const router = express.Router()

export default router
```

A primeira informação que passaremos neste arquivo é o chamamento do `Router` dentro de uma constante chamada `router`. Esta constante será utilizada ao longo de todas as requisições.

No arquivo `app.js` importaremos o arquivo de rotas e antes da informação do `listen` inseriremos o código ao lado para que todas as vezes que acessarmos a requisição dentro da rota indicada o que estiver no arquivo de rotas será interpretado.

```jsx
import router from './routes/items.route.js'

app.use('/items', router)
```

### Método `GET`

```jsx
router.get('/', (request, response) => {
	return response.status(200).json("return all items")
})
```

O método `GET` é utilizado quando queremos ler informações ou acessá-las, também conhecido como o READ de CRUD. Retornamos a resposta quando seu status dá `200 OK` e inserimos o que queremos retornar dentro do `json()`.

No método `GET` também é possível capturar um único item pelo seu `id`.

No caminho da requisição passamos o `:id`, que significa que estamos identificando a informação de forma dinâmica. Este `id` será um parâmetro (`params`) da nossa requisição.

O que será returnado no `json()` será o método de array `find()` onde encontraremos dentro daquela lista o item de mesmo `id` que estamos requisitando.

```jsx
router.get('/:id', (request, response) => {
	const { id } = request.params

  const findById = items.find(
	  item => item.id == id
	)

	return response.status(200).json(items)
})
```

### Método `POST`

```jsx
router.post('/create', (request, response) => {
	const create = {
	  ...request.body,
		id: uuidv4()
  }

  items.push(create)

  return response.status(201).json(items)
})
```

O método `POST` cria um novo item para a nossa lista de informação.

Passamos um caminho novo para acessarmos neste momento e dentro da callback criamos um novo objeto que conterá o corpo da requisição. Depois inserimos este objeto dentro da lista com o `push()`.

Este método retornará o objeto criado quando o status for `200 OK`.

- **Indicação de dependência para criação de `id`**
    
    O `id` funciona como um identificador único para os itens de nossa listagem, por isso é importante que eles sejam gerados de forma única e aleatória para melhorarmos a segurança de sua manipulação.
    
    Podemos instalar a dependência `uuid` que gerará de forma automática um código para identificação
    
    ```bash
    npm install uuid
    ```
    
    Depois de instalado o importaremos no arquivo de rotas e no método POST conseguimos executar a função da dependência como mostrado no código acima.
    
    ```jsx
    import { v4 as uuidv4 } from 'uuid'
    ```
    

### Método `PUT`

```jsx
router.put('/:id', (request, response) => {
	const { id } = request.params

  const update = items.find(
	  item => item.id === id
  )

  const index = items.indexOf(update)

  items[index] = {
    ...update,
    ...request.body
  }

  return response.status(200).json(items[index])
})
```

O método `PUT` atualiza informações de um item já existente dentro da lista. Ele funciona de uma forma parecida com o `POST`, porém precisamos identificar o `id` daquela item para editarmos suas informações.

O método `indexOf()` nos ajudará a identificar a posição do elemento que queremos atualizar e enviaremos a lista junto com a nova requisição. Então retornaremos quando o status for `200 OK` o objeto atualizado.

### Método `DELETE`

```jsx
router.delete('/:id', (request, response) => {
	const { id } = request.params
    
  const deleteById = items.find(
	  item => item.id === id
  )

  const index = items.indexOf(deleteById)
  items.splice(index, 1)

  return response.status(200).json(items)
})
```

O método `DELETE` exclui um item de dentro da nossa lista.

Assim como o `PUT` precisamos identificar qual é o `id` do objeto que queremos excluir e então identificar a sua posição dentro da lista. Depois disso, usamos o `splice()` para retirar o objeto de dentro da lista, passando a posição do objeto.

Retornamos no final o objeto deletado para conseguirmos um status `200 OK`.

## Executando o servidor em uma porta

No final de todo o nosso código no arquivo principal, podemos inserir o seguindo código

```jsx
app.listen(8080,
	() => console.log("server listening on port 8080"))
```

Essa linha pede para que a aplicação seja ouvida na porta `4000` e então gera uma mensagem que será impressa no terminal para que possamos ter a certeza de que temos um servidor rodando com sucesso.

Para vermos isso acontecendo, rode no terminal o comando do node

```bash
node --watch app.js
```

Abra no navegador ou em algum programa de requisição a URL [**http://localhost:4000/**](http://localhost:4000/) e observe que irá imprimir o que está sendo informado na requisição com caminho `/`.

# 🪢 Entendendo dependências importantes para o servidor

## `CORS`

CORS significa Compartilhamento de Recursos de Origem Cruzada e garante a navegação segura dos usuários dentro da aplicação.

Todos os navegadores, para criarem uma navegação segura ao usuário, possuem um mecanismo de segurança chamado Same-Origin Policy, que limita a interação entre scripts de origem diferente para bloquear possíveis ações maliciosas e criminosas. Para conseguirmos, então, criar a conexão entre o Front-end e o Back-end precisamos setar a origem de onde iremos cruzar essas informações.

### Setando o `CORS`

No terminal, instale a dependência

```bash
npm install cors
```

No arquivo principal faça a importação do `CORS` e chame a sua origem

```jsx
import cors from 'cors'

app.use(cors( { origin: 'http://localhost:3000 } ))
```

O endereço utilizado no `origin` deve ser o da aplicação usada no Front-end.

## `dotenv`

Durante a criação do servidor reunimos diversas variáveis de ambiente, que são variáveis que vão definir como iremos trabalhar ou conexões com outras aplicações.

Para concentrarmos essas variáveis de forma segura e que será individual para cada teste, utilizamos a dependência `dotenv` que seta e faz a comunicação da aplicação com as variáveis de ambiente, tornando-as dinâmicas de cada ambiente de desenvolvimento.

### Setando o `dotenv`

No terminal faça a instalação da dependência

```bash
npm install dotenv
```

Na raiz do projeto, crie um arquivo chamado `.env` e insira as variáveis de ambiente.

```jsx
PORT="8080"
FRONT_URL="http://localhost:3000"
```

No arquivo principal do servidor, importe o `dotenv` e chame a configuração da dependência.

Por fim, chame as variáveis com o comando padrão.

```jsx
import * as dotenv from 'dotenv'
dotenv.config()

app.use(cors({ origin: process.env.FRONT_URL }))

app.listen(Number(process.env.PORT), () => {
    console.log("server listening on port 3000")
})
```
