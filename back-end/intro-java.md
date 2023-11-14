# Java

Área do Conhecimento: Tecnologia
Referência: https://docs.oracle.com/javase/tutorial/getStarted/index.html

> *Java é uma linguagem de programação orientada a objetos e baseada em classes, concebida para dispor da menor quantidade possível de dependências de implementação, onde as aplicações são executadas em uma Máquina Virtual Java permitindo a portabilidade para diferentes plataformas.*
> 

<aside>
📋 Veja o que está sendo abordado aqui:

- **Tabela de conteúdo**
</aside>

O JVM significa **Java Virtual Machine** (Máquina Virtual de Java) e é uma máquina virtual que permite um computador de rodar programas Java assim como programas escrito em outras linguagens que também são compiladas em bytecode Java. 

O JDK significa **Java Development Kit** (Kit de Desenvolvimento Java) e é um software para aplicações Java, que inclui a máquina virtual, o compilador, debugador e as ferramentas de performance necessárias para o desenvolvimento do projeto.

A execução do Java acontece em duas etapas, em que o compilador traduz o código que a pessoa desenvolvedora escreve (código-fonte) para bytecode, que é a linguagem binária que o computador entende. Dentro de todo projeto Java existe arquivos que não são manipulados pelas pessoas desenvolvedoras, mas são essenciais para essa compilação e tradução para que o computador entenda o código-fonte que estamos programando.

# Comentários em Java

É possível fazer comentários no nosso código, servindo de apoio para nos comunicarmos entre equipe e indicar partes do nosso código ou para ocultar algo do código que não queremos que seja exibido no navegador.

Para comentários em texto usamos a indicação `/* */` onde o compilador ignora o texto que está entre os sinais, assim como o comentário em linha indicado pelo sinal `//`, geralmente usado no final da linha de um código que queremos. Já o sinal `/** */` indica um comentário sobre documentação, onde o compilador ignora o comentário, mas a ferramenta `javadoc` usa esses comentários no momento de preparar a documentação gerada automaticamente do projeto.

# **Estrutura básica do Java**

O código em Java é composto por três componentes primários: comentários, a classe e o método.

```java
class HelloWorldApp {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

Iniciamos com a indicação `class` para dizer que estamos manipulando uma classe, que receberá um nome customizado e dentro das chaves indicamos o método e o código desejado.

O método `main` é uma indicação padrão, toda aplicação precisa desse método. 

# Declarações

Para armazenar e declarar valores usamos variáveis e constantes:

- **Variáveis**
    
    Uma variáveis tem seu valor guardado e pode ser modificado ao longo do projeto. Para declarar é preciso informar o tipo de dado que será aceito junto com o nome criado.
    
    ```java
    String myName = "Maria";
    ```
    

- **Constantes**
    
    A constante é um valor fixo e que não pode ser modificado. Ele é indicado com a palavra reservado final no início da declaração e o seu nome deve estar em letras maiúsculas.
    
    ```java
    final int NUMBER_OF_MONTHS = 12;
    ```
    

# Tipos de dado e Estrutura

Na declaração de valores devemos especificar o tipo de dados, que podem ser entre eles:

| boolean | true e false |
| --- | --- |
| String | frase ou palavra entre aspas duplas |
| char | letra ou caractere entre aspas simples |
| int | número inteiro |
| double | decimais |

Conseguimos também armazenar conjunto de valores utilizando Array. Diferentemente do Javascript, em Java apenas conseguimos reunir dentro de uma array dados do mesmo tipo, onde informamos o tipo de dados e então criamos a array.

```java
int[] ages = {19, 42, 92};
```

Conseguimos realizar a conversão de tipo de dado dentro de uma variável se especificarmos antes da variável. Por exemplo, se temos uma variável `int idade = 12;` e então queremos que ela se transforme em um número decimal declaramos `double idadeNova = (double) idade;`, dessa forma a variável `idade` está armazenada como número decimal na variável `idadeNova`.

Dentro dos mesmos tipos de dados conseguimos realizar operações matemáticas e realizar cálculos ou unir frases. Abaixo está uma lista de operadores aritméticos e operadores relacionais.

| + | adição |
| --- | --- |
| - | subtração |
| * | multiplicação |
| / | divisão |
| % | resto da divisão |
| ++ | incremento |
| - - | decremento |

| = | recebe |
| --- | --- |
| || | ou |
| && | e |
| ! | negativo |
| != | diferente |

| > | maior que |
| --- | --- |
| < | menor que |
| >= | maior ou igual que |
| <= | menor ou igual que |
| == | igual |

# Tipos de laços

Com laços conseguimos executar repetições e impressões de forma mais rápida e economizando linhas de código, tornando-as dinâmicas.

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
    

## Laço de repetição

Com os laços de repetição criamos um *loop*, ou seja, imprimimos valores de acordo com a condição e enquanto a condição for verdadeira. Existem algumas formas de criar um repetição em nosso código.

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
    

- **For each**
    
    Passa por todo o array de acordo com o que está sendo calculado ou pedido entre os colchetes.
    
    ```java
    for(item : itens) {
    	// faça isso;
    }
    ```
    

# Programação Orientada a Objeto

A Orientação a Objeto tem como objetivo simular o mundo real dentro do código-fonte. Todos os dias, nós interagimos com objetos e temos ações que não pensamos sobre como estamos realizando essas ações ou como objetos se comportam de certa forma, apenas aceitamos esse comportamento uma vez que eles façam o que pedimos. Dentro da POO, o objeto é responsável por executar a ação ou comportamento e colaboram com outros objetos para a conclusão com sucesso dessa ação.

- **Benefícios do POO**
    - Reprodução de conceitos da vida real que conhecemos
    - Facilidade na manutenção
    - Facilidade de manipulação e atualização
    - Minimização de efeitos colaterais
    - Organização

- **Potenciais desvantagens**
    - Sobrecarga de criação de código no início do projeto
    - Código mais verboso
    - Impacto na performance devido a criação de lixo (código não necessário

## Qual é a diferença entre um objeto e uma classe?

A **classe** é um template criado para novos objetos, é nela em que criamos atributos, argumentos e retornos, ou seja, as regras e comportamentos que o objeto deve ser e seguir. O **objeto** é uma classe criado no momento de execução do projeto. Cada objeto é único e criado no momento de execução a partir das informações que inserimos na classe.

```java
public class Cachorro {
	String raca;
	String nome;
	String pelagem;

	void latindo() {}
	void balancandoRabo() {}
}
```

Um objeto apresenta estados e comportamentos. O estado são atributos e propriedades desse objeto, enquanto o comportamento são métodos do objeto. Por exemplo, temos uma classe `Cachorro` que leva os atributos `raca`, `nome` e `pelagem`, junto com seus métodos `latindo()` e `balancandoRabo()`.

O objeto é criado no momento em que o programa é executado e criamos um cachorro com estados e comportamentos individuais, ou seja o nosso objeto é um cachorro chamado Spike, da raça golden retriever e com pelagem amarela.

## Métodos

Os métodos são blocos de códigos que apenas são executados quando chamados da seguinte forma `meuMetodo()`. Junto com os métodos também podemos passar argumentos que são chamados de parâmetros, que são os dados que ficam dentro do parênteses do método.

### Métodos estáticos

O `static` indicado na criação do método significa que o método não depende de um objeto, dessa forma o método estático não pode ser acessado por nenhuma classe instanciada.

### Métodos construtores

O `constructor` é um método especial que usamos para inicializar objetos, sendo ótimo para a organização dos objetos.

```java
public class Main {
  int x;

/* construtor */
  public Main() {
    x = 5;
  }
}
```

Podemos criar uma classe `constructor` na classe e setamos o valor inicial do atributo ou podemos também utilizar parâmetros dentro do construtor para inicializar os atributos da classe.

```java
public class Main {
  int x;

/* construtor */
  public Main(int y) {
    x = y;
  }
}
```

## Modificadores de acesso

Os modificadores de acesso especificam o acesso ou o escopo do método, classe ou construtor. Existe quatro tipos de acessos:

- **Privado**
    
    O `private` dá acesso apenas dentro da classe, não podendo ser acesso fora dela.
    

- **Protegido**
    
    O `protected` aceita acessar dentro do pacote.
    

- **Público**
    
    O `public` podemos acessar de qualquer lugar dentro do projeto.
    

- **Padrão**
    
    O acesso padrão é apenas dentro do pacote, ou seja `protected`.
    

## Encapsulamento

É o momento em que chamamos o objeto e modificamos o seu estado ou comportamento. Utilizando o encapsulamento evitamos que as informações sofram acessos indevidos, realizando alterações sem mudar o programa principal.

Para acessar os estados e comportamentos do objeto precisamos criar `getters` e `setters`, que são métodos para capturar e atribuir informações do objeto.

```java
public String getNome() {
	return nome;
}

public void setName (String nome) {
	this.nome = nome;
}
```

Dentro da classe criamos um `getter` e um `setter` para os estados e comportamentos quando necessário para que então conseguimos manipular a realidade de qualquer objeto referente a essa classe.

O `get` recupera a informação desejada, enquanto o `set` insere a informação no atributo desejado. Ou seja, um objeto `Cachorro`, informariamos `setNome(”Spike”)` e quando dermos `getNome()` receberiamos `Spike` no console.

## Herança

É o momento em que uma classe herda estados e comportamentos de uma classe superior. Dentro da herança, a classe pai é chamada de superclasse e a classe filho, subclasse, que herda todas as características da superclasse e também possui suas próprias características.

```java
//superclasse
public class Animais {
	String raca;
	String nome;
	String pelagem;
}
```

Podemos, por exemplo, criar uma superclasse chamada `Animais` que possuem estados e então temos uma subclasse `Cachorro` que extende os estados da superclasse e possui comportamentos particulares.

```java
//subclasse
public class Cachorro extends Animais {
	int idade;
	String tutor;

	void latindo() {}
	void balancandoRabo() {}
}
```

## Polimorfismo

A habilidade de um sistema de objeto de descobrir qual comportamento é apropriado baseado na mensagem no runtime para então que nós termos diferentes objetos qe recebem a mesma mensagem mas produz diferentes comportamentos é chamado de polimorfismo. 

This ability is called polymorphism and creates very flexible systems that are very easy to change, extend, and update without having to recompile a lot of code, for example, the main code.

### Abstração

---

A abstração acontece quando determinamos o problema central da situação para determinar as informações e comportamentos que precisamos do nosso objeto, sabendo que diferentes problemas requerem diferentes comportamentos mesmo dentro do mesmo objeto.

A abstração pode acontecer quando setamos um método para executar um outro método sem ter a interferência do usuário final o manipulando. Para isso nós setamos o método para ficar de modo privado, salvando o código de sofrer alguma alteração não desejada.

```java
public class Pedido {
	public double Total;
	private void CalcularTotal; //setando o cálculo final como privado e privamos o seu acesso externo
	
	public void AdicionarItem(Item item) {
		Items.Adicionar(item);
		CalcularTotal(); //ele é executado normalmente aqui
	}
}
```

Conseguimos manipular o acesso às classes com os modificadores de acesso, que são aplicáveis para classes, variáveis e métodos. Os modificadores de acesso também limitam o acesso dessas classes e variáveis no momento do encapsulamento.

| Modificadores de acesso | Escopo de visibilidade |
| --- | --- |
| public | Todas as classes |
| protected | Classes no mesmo package e subclasses |
| default | Classes no mesmo package |
| private | Só na mesma classe |

## Princípios da Orientação ao Objeto

---

1. Utilizamos a **Abstração** durante a fase de análise do nosso projeto para identificar os compartamentos e atributos apropriados do sistema.
2. Utilizamos a **Herança** e o **Polimorfismo** durante a criação do código para aproveitar a reutilização e criar códigos mais flexíveis.
3. Utilizamos **Encapsulamento** para minimizar dependências e efeitos colaterais na nossa lógica.

## Exceptions

---

Exceptions são momentos de situações inexperadas no nosso código. Usando-as, nós conseguimos criar momentos e mensagens de erro e aviso para o programador e usuário entender o que pode estar acontecendo no nosso programa, porque o próprio Java não sabe o que fazer.

Quando o Java não sabe o que fazer com o erro, então uma exception é criada em forma de objeto contendo informações úteis, que então vai gerar um código que invocará o método problemático. Existem diferentes tipos de objetos de exception e também há aquelas que podem ser criadas pelo programador.