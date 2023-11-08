<h1 align="center">Introdução ao nodeJS</h1>

> *O nodeJS é um ambiente open-source que lida com o lado do servidor (server side) e roda em diferentes sistemas operacionais, possibilitando a utilização de Javascript no back-end.*
> 

# Instalação do `node`

Ao entrar no [**site oficial**](https://nodejs.org/en/) é possível escolher a opção LTS, que é uma versão mais estável e recomendada pelos desenvolvedores do programa, para ser instalada no seu sistema operacional.

```bash
node --version
```

Após a sua instalação podemos abrir o terminal e rodar o comando ao lado para termos a confirmação de que o `node` foi instalado e qual é a sua versão disponível para trabalharmos.

## Hello world em `node`

Crie um projeto e o abra no Visual Studio Code. Em seguida, crie um arquivo chamada `app.js` e digite o seguinte código

```jsx
console.log("Hello World!")
```

Abra o terminal dentro do VS Code e rode o comando abaixo

```bash
node --watch app.js
```

O `node` é o comando que digitamos para que o Javascript seja interpretado fora do navegador, através de linha de comando. O `--watch` permite com que a cada atualização do nosso código o servidor seja reiniciado automaticamente. Em seguida passamos o nome do arquivo que queremos rodar.

# Introdução a internet e seus conceitos teóricos

## O que é a internet?

A internet é uma rede global de computadores que tem como objetivo a comunicação e transferência de informações.

![https://madooei.github.io/cs421_sp20_homepage/assets/client-server-1.png](https://madooei.github.io/cs421_sp20_homepage/assets/client-server-1.png)

Na internet a comunicação acontece entre cliente e servidor, onde o servidor possui informações e o cliente faz um pedido sobre quais informações ele precisa, o servidor então analisa o pedido e retorna a informação para o cliente.

O pedido do cliente é chamado de requisição (`request`) e o envio de informação pelo servidor é chamado de resposta (`response`). Basicamente toda a internet são várias requisições e respostas.

## Protocolo HTTP

Como qualquer forma de comunicação existe um conjunto de regras a ser seguido, o que também chamamos de protocolo. O protocolo mais conhecido é o HTTP, abreviação de Protocolo de Transferência de Hipertexto.

O HTTP é o protocolo utilizado para a transferência de diferentes arquivos na Web como, por exemplo, HTML, scripts, multimídias, etc.

### Protocolo HTTPS

O HTTPS é uma versão segura do HTTP, o que significa que ele é criptografado para aumentar a segurança entre a transferência de dados. Quando estamos tratando de dados sensíveis como informações de login, dados bancários, informações pessoais, etc. é de extrema importância que as aplicações estejam utilizando HTTPS para dar mais segurança para o usuário e portador dessas informações.

# Criando um servidor do zero

Dentro de uma pasta rode o comando

```bash
npm init --yes
```

Este comando será responsável por gerar o arquivo `package.json`. Abra o arquivo e no final do objeto, antes do fechamento da chave, insira a linha de informação

`"type": "module"`

No arquivo `app.js`, insira o seguinte código

```jsx
import { createServer } from "http"

const server = createServer()
server.listen(4000)
```

O `node` possui um módulo `http` embutido que importaremos para criar o nosso servidor. A constante `server` fará esse comando e então chamamos o método `listen()` com o número da porta que usaremos para rodar o servidor.

⚠️ **Cuidado para não rodar o servidor na mesma porta do front-end!**

Para que a comunicação esteja completa precisamos criar uma requisição e uma resposta. Para isso, atualize o código da seguinte forma

```jsx
const server = createServer((request, response) => {
	console.log("Hello World")
	response.end("server working with success")
})
```

Passamos `request` e `response` como parâmetros para que quando a requisição for feita, o que estiver dentro do escopo será executado. O `response.end()` é um método que fala ao servidor quando a requisição foi bem sucedida e pode enviar uma resposta também.

Ao rodar o comando no terminal para rodar o servidor é possível ver as informações sendo executadas.
