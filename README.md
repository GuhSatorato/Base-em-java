## ☕ Guia Intuitivo de Java com Emojis

## 🚀 Começando com Java

- **Java** ☕: Java é uma linguagem de programação que roda em qualquer sistema operacional por conta da JVM 
- **start** ▶️: Para começar a utilizar a linguagem JAVA, você precisa instalar o **JDK**.

## 📦 JDK, JRE, JVM e Executáveis

- **JDK (Java Development Kit)** 🛠️: Kit de Desenvolvimento JAVA, como dito anteriormente é necessário para utilizar o JAVA, pois inclui tudo para programar em JAVA (compilador, ferramentas, JRE).
- **JRE (Java Runtime Environment)** 🔁: Ambiente para rodar programas Java (inclui JVM).
- **JVM (Java Virtual Machine)** ⚙️: A máquina virtual que executa o Java.
- **java.exe** 📥: Executa programas compilados (.class).
- **javac.exe** 🛠️: Compila arquivos `.java` para `.class`.
- **.class** 📄: Arquivo gerado após a compilação de um `.java`. Contém o código que será interpretado pela JVM.

## 🧱 Classe, Objeto, Atributo e Método

- **Classe** 🧩forma: A classe é um molde para criar um objeto\
  Exemplo: Como se você fosse fazer um bolo, primeiro você reserva a forma e depois faz o bolo, no caso a forma seria a **Classe** **e o bolo seria o Objeto**.

- **Objeto** 🎂: Instância de uma classe. Ele é criado a partir da classe e pode usar seus atributos e métodos.\
  Exemplo: após você reservar a forma (**Classe)** vc faz o bolo (**Objeto)**, porem você pode fazer vários sabores de bolo, então você pode ter vários (**Objeto)**.

- **Atributo e Método**🧮

  - **Atributo**: característica ou informação do objeto (ex: tamanho e sabor).
  - **Método**: Método é a ação que o objeto pode realizar. (ex: assar o bolo, rechear o bolo)

- **Resumo 📖**

  - **Classe** = a forma de fazer bolo (molde para o objeto)
  - **Objeto** = o bolo feito
  - **Atributos** = sabor, tamanho
  - **Método** = assar()

## ⚙️ Tipos de Dados
  - **int** 🖥: Números inteiros. **ex:** 12.
  - **string** 📝: Texto. **ex:** "Chocolate".
  - **float** 📊: Números de ponto flutuante. **ex:** 12.5.
  - **boolean** 📄: Verdadeiro ou falso.

## ↪ Desvio de Fluxo
- **if** 📜: Se.
` ...
if (numero > 5) {
            System.out.println("O número é maior que 5.");
        }
...
` 
- **else** 📜: Senão.
` ...
else {
            System.out.println("O número é 5 ou menor.");
        }
...
` 
- **for** 📜: Para.
` ...
for (int i = 1; i <= 5; i++) {
            System.out.println("Contando: " + i);
        }
...
` 
- **while** 📜: Enquanto.
` ...
while (i <= 5) {
            System.out.println("Contando: " + i);
            i++;
        }
...
`

## 🔒 Encapsulamento

- **Encapsulamento** 📦: Protege os dados internos de uma classe, impedindo de serem alterados externamente.
    Exemplo: Como guardar uma coisa dentro de uma "caixa", e deixar visível somente o que for necessário.
- **private** 🔐: Só pode ser acessado dentro da propria classe.
    Exemplo: Igual guardar seu dinheiro na gaveta (**classe**), mais ninguem pode acessar (**private**).
- **public** 🌐: Pode ser acessado de qualquer lugar.
    Exemplo: Um botão de elevador, que pode ser acessado por qualquer pessoa (**public**).

## 🛠️ Métodos Especiais

- **Get/Set** ↕️:

  - `getNome()` 🧐 → retorna um valor.
  - `setNome("João")` ✍️ → define um valor.

- **This** 👈: Referência ao próprio objeto (útil quando há ambiguidade).
    Exemplo: No método `setNome`, `this.nome` é uma referência ao atributo `nome` do objeto atual.
    ```java	
    public void setNome(String nome) {
            this.nome = nome;
        }
    ```

- **static** 📜: Static é algo que pertence a classe e não a um objeto, util para metodos que são iguais para todos os objetos da classe
- **final** 📜: Não pode ser alterado depois de definido, algo imutavel.

## 🧬 Construtor, Sobrecarga e Subscrita

- **Método Construtor** 🏗️: Um metodo que quando um objeto é criado, é executado automaticamente.
    Exemplo
    ```java
        class Pessoa {
        String nome;

        // Construtor
        Pessoa(String n) {
            nome = n;
        }
    }

    Pessoa pessoa1 = new Pessoa("Gustavo"); // Chama o construtor
    Pessoa pessoa2 = new Pessoa("Henrique"); // Chama o construtor
    ```
- **Sobrecarga (Overload)** ➕: Vários métodos com o mesmo nome, mas diferentes parâmetros, serve para usar o metodo mais de uma maneira diferente.
    Exemplo
    ```java
    class Soma {
        int somar(int a, int b) {
            return a + b;
        }

        double somar(double a, double b) {
            return a + b;
        }
    }
    ```
- **Subscrita (Override)** 🔁: É quando uma subclasse reescreve um método da superclasse, serve para mudar o metodo da classe pai.
    Exemplo
    ```java
    class Animal {
        void fazerSom() {
            System.out.println("Miado");
        }
    }

    class Cachorro extends Animal {
        @Override
        void fazerSom() {
            System.out.println("Latido");
        }
    }
    ```

## 🔢 Parâmetros

- **Parâmetros** 📏: Atributos que vão entre parrenteses dentro do metodo, eles recebem valores quando o metodo é chamado.
    - Resumindo são caixas que recebem valores.
- Exemplo
    ```java
    class Matematica {
        // Método com dois parâmetros: a e b
        int soma(int a, int b) {
            return a + b;
        }
    }
    ```
    ```java
    public class TestaMatematica {
        public static void main(String[] args) {
            Matematica m = new Matematica();
            int resultado = m.soma(5, 3); // Aqui 5 e 3 são passados como valores pros parâmetros
            System.out.println("Resultado: " + resultado); // Mostra 8
        }
    }
    ```

---

## 📂 Exemplo Comentado com Classe, Objeto, Construtor e Getters

### `Bolo.java`

```java
class Bolo {
    // Atributos (características do bolo)
    String sabor;
    String tamanho;

    // Método (ação que o bolo pode realizar)
    void assar() {
        System.out.println("O bolo de " + sabor + " de tamanho " + tamanho + " está assando.");
    }

    void rechear() {
        System.out.println("O bolo de " + sabor + " está sendo recheado.");
    }
}
```

---

### `TestaBolo.java`

```java
public class TestaBolo {
    public static void main(String[] args) {
        // Criando objetos (bolos)
        Bolo bolo1 = new Bolo();
        bolo1.sabor = "chocolate";
        bolo1.tamanho = "grande";
        
        Bolo bolo2 = new Bolo();
        bolo2.sabor = "morango";
        bolo2.tamanho = "pequeno";

        // Chamando os métodos (ações)
        bolo1.assar();
        bolo1.rechear();

        bolo2.assar();
        bolo2.rechear();
    }
}
```

---

## 🧾 Software Real: Cadastro de Produtos

### `Produto.java`

```java
// Classe Produto representa um item com nome, preço e quantidade
public class Produto {
    private String nome; // Atributo para armazenar o nome do produto
    private double preco; // Atributo para armazenar o preço do produto
    private int quantidade; // Atributo para armazenar a quantidade em estoque

    // Construtor que inicializa os atributos com os valores recebidos
    public Produto(String nome, double preco, int quantidade) {
        this.nome = nome; // Atribui o nome ao atributo da classe
        this.preco = preco; // Atribui o preço ao atributo da classe
        this.quantidade = quantidade; // Atribui a quantidade ao atributo da classe
    }

    // Métodos getters retornam os valores dos atributos
    public String getNome() {
        return nome;
    }

    public double getPreco() {
        return preco;
    }

    public int getQuantidade() {
        return quantidade;
    }

    // Método setter atualiza o valor da quantidade
    public void setQuantidade(int quantidade) {
        this.quantidade = quantidade;
    }

    // Método que calcula o valor total do estoque (preço x quantidade)
    public double calcularTotal() {
        return preco * quantidade;
    }
}
```

### `Loja.java`

```java
// Importa a classe Scanner para leitura de dados pelo teclado
import java.util.Scanner;

// Classe principal Loja
public class Loja {
    public static void main(String[] args) {
        // Cria um objeto Scanner para capturar entrada do usuário
        Scanner sc = new Scanner(System.in);

        // Solicita o nome do produto
        System.out.print("Nome do produto: ");
        String nome = sc.nextLine(); // Lê o nome digitado

        // Solicita o preço do produto
        System.out.print("Preço do produto: ");
        double preco = sc.nextDouble(); // Lê o preço digitado

        // Solicita a quantidade em estoque
        System.out.print("Quantidade em estoque: ");
        int quantidade = sc.nextInt(); // Lê a quantidade digitada

        // Cria um objeto Produto com os dados informados
        Produto produto = new Produto(nome, preco, quantidade);

        // Exibe os dados do produto no console
        System.out.println("\nProduto cadastrado com sucesso!");
        System.out.println("Nome: " + produto.getNome());
        System.out.println("Preço: R$" + produto.getPreco());
        System.out.println("Estoque: " + produto.getQuantidade());
        System.out.println("Valor total em estoque: R$" + produto.calcularTotal());
    }
}
```
