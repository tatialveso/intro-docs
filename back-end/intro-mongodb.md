<h1 align="center">Introdução ao MongoDB</h1>

> *Programa de banco de dados distribuído não-relacional orientado a documentos que armaneza dados em coleções.*
> 

# Introdução ao MongoDB

![https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_157ca84354e93013a2289e0e4a8809a6.png](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_157ca84354e93013a2289e0e4a8809a6.png)

É um banco de dados não-relacional que armaneza informações em coleções. As informações coletadas são flexíveis, semelhantes a `JSON` e com campos significativos que podem variar de documento para documento. A sua forma de distribuição permite escabilidade horizontal que é fácil de manuseio.

# Instalação do MongoDB

Para instalar o MongoDB no sistema operacional Windows é preciso ir até o [**site oficial**](https://www.mongodb.com/try/download/community) da ferramenta e selecionar a versão desejada para instalação.

⚠️ **É sempre recomendado escolher a versão indicada como current pois é a mais recente estável da ferramenta.**

- Siga os passos de instalação e espere até a instalação estar finalizada. Antes de iniciar os trabalhos no Compass, siga os passos
    1. Abra o Explorador de Arquivo
    2. Entre no Disco Local (ou `C:`)
    3. Vá em Arquivos de Programas
    4. Acesse a pasta MongoDB
    5. Entre em Server
    6. Entre na pasta com o nome da versão instalada e vá até a pasta bin
    7. Copie o endereço deste caminho disponibilizado pela barra logo acima
    8. Abra as configurações do seu computador
    9. Em Sistema, abra a aba de nome Sobre
    10. Encontre a opção Configurações avançadas do sistema
    11. Selecione o botão Variáveis de Ambiente…
    12. Encontre a variável Path e clique duas vezes
    13. Na janela que surgirá, clique no botão Novo
    14. Insira o caminho copiado anteriormente
    15. Dê OK em todas as outras janelas, fechando-as
    16. Abra o Prompt de Comando e digite o comando
        
        ```bash
        mongod
        ```
        
    
    Se aparecer várias informações é porque o seu banco de dados está funcionando!
    

## Conectando o MongoDB

Abra o MongoDB Compass e para criar uma nova conexão vá em New Connection.

Clica em Save & Connect para salvar e conectar ao `localhost`.

A informação da URI irá variar dependendo da necessidade de cada projeto, mas para testar e estudar é válido aceitar o caminho padrão do MongoDB.

## Criando uma database e uma coleção

Clique em Create database e insira um nome para o banco de dados e também insira um nome para coleção que irá trabalhar.

Dentro de uma conexão é possível ter vários bancos de dados e dentro de cada banco é possível ter várias coleções.

É nas coleções que iremos insirar os objetos que se tornarão itens das nossas requisições.

Nessas coleções é possível insirar cada informação de forma individual ou importar um `JSON` de algum outro lugar.

# Operações de buscas dentro do MongoDB Compass

## Consultas básicas

Para recuperar itens a partir de uma operação é possível passar a informação do nome do campo e o valor para filtrar entre as opções.

```sql
{ fieldname: value }
```

É possível também recuperar uma informação pelo seu `id`. Para isso é importante envolver o valor em um `ObjectId`.

```sql
{ "_id": ObjectId(id) }
```

## Consultas lógicas

### $and

Usado quando queremos encontrar uma informação que obedeça todas as condições citadas na consulta.

```sql
{ $and: [ { <expression1> }, { <expression2> }, ... ] }
```

### $or

Usado quando queremos encontrar uma informação que obedeça uma ou outra condição citada na consulta.

```sql
{ $or: [ { <expression1> }, { <expression2> }, ... ] }
```

### $nor

Usado quando queremos encontrar uma informação que tem um resultado que:

- contém informações diferentes de todas as informadas na consulta
- contém informações diferentes de no mínimo uma das informadas na consulta
- não contém nenhum campo informado na consulta

```sql
{ $nor: [ { <expression1> }, { <expression2> }, ... ] }
```

## Consultas avançadas

### Projeções

O segundo campo da barra de consulta do MongoDB Compass determina projeções que permite especificar o tipo de informação que queremos retornar.

Podemos dizer quais campos queremos mostrar selecionando apenas `1` ou `0` no objeto. Todos os campos que queremos mostrar são indicados com o número `1` e todos os campos que não queremos mostrar são indicados com o `0`.


⚠️ **Por padrão o `_id` é sempre mostrado, então se não queremos retorná-lo devemos indicar com o `0`.**


Por exemplo, se queremos retornar apenas os títulos de uma lista de filmes, no campo `PROJECT` passamos a seguinte informação

```sql
{ title: 1, _id: 0 }
```

### Ordem

O terceiro campo da barra de consulta determina a ordem que as informações vão aparecer.

Ao setar a ordem como `1`, então a lista aparecerá em ordem crescente; e para setar uma ordem decrescente colocamos o campo com valor `-1`.

Por exemplo, se queremos retorna uma lista de filmes na ordem crescente de título, no campo SORT passamos a informação

```sql
{ title: 1 }
```

### Skip & Limites

No MongoDB Compass também temos a opção de colocar um número de informações que queremos pular e só mostrar informações a partir deste valor.

Por exemplo, se queremos mostrar a partir da 21ª informação, então no camp `SKIP` informamos o valor `20`.

Já o campo `LIMIT` dita o número de informações que vão aparecer no total.

Dessa forma, se quisermos ver apenas `5` informações passamos este número no campo indicado.

## Consultas de comparação

### $ne

Usado quando queremos encontrar uma informação que tem um resultado diferente do informado na consulta. Na resposta também é incluso informações que não possuem o campo informado na consulta.

```sql
{ field: { $ne: value } }
```

### $eq

Usado quando queremos encontrar uma informação que tem um resultado igual ao informado na consulta.

```sql
{ field: { $eq: value } }
```

### $gt

Usado quando queremos encontrar uma informação que tem um resultado maior do que o informado na consulta.

```sql
{ field: { $gt: value } }
```

### $gte

Usado quando queremos encontrar uma informação que tem um resultado maior ou igual do que o informado na consulta.

```sql
{ field: { $gte: value } }
```

### $lt

Usado quando queremos encontrar uma informação que tem um resultado menor do que o informado na consulta.

```sql
{ field: { $lt: value } }
```

### $lte

Usado quando queremos encontrar uma informação que tem um resultado menor ou igual do que o informado na consulta.

```sql
{ field: { $lte: value } }
```

## Consultas de array

### $in

Usado quando queremos encontrar informações dentro de um array que possam conter um ou outro valor indicado na consulta.

```sql
{ field: { $in: [ value1, value2, ... ] } }
```

### $nin

Usado quando queremos encontrar informações dentro de um array que não possuem nenhuma informação indicada na consulta.

```sql
{ field: { $nin: [ value1, value2, ... ] } }
```

### $all

Usado quando queremos encontrar informações dentro de um array que contém todos os valores indicados na consulta.

```sql
{ field: { $all: [ value1, value2, ... ] } }
```

### $elemMatch

Usado quando queremos encontrar informações dentro de um array que contém um campo com, no mínimo, uma informação indicada na consulta.

```sql
{ field: { $elemMatch: { <query1>, <query2>, ... } } }
```

## Consultas de elementos

### $exists

Usado para retornar informações que contém ou não o campo informado durante a consulta. Quando o valor for `true` será retornado todos os itens que contém tal informação até eles que o valor é `null`; quando o valor for `false` será retornado aquelas informações que não contém aquele campo.

```sql
{ field: { $exists: <boolean> } }
```

### $type

Usado para retornar informações onde o valor daquele campo seja o indicado durante a consulta.

```sql
{ field: { $type: <BSON type> } }
```
