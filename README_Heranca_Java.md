
# 👨‍🏫 Sistema de Cadastro de Pessoas com Herança em Java

Este projeto demonstra a utilização de **POO (Programação Orientada a Objetos)** em Java, focando nos conceitos de **herança**, **construtores**, **sobrescrita de métodos** e **entrada de dados com Scanner**.

---

## 📦 Estrutura de Classes

### 🧍 Pessoa (Classe Base)

Classe com os atributos comuns a qualquer pessoa:

```java
private String nome;
private String cpf;
private String d_nasc;
```

#### 🔨 Construtores

- **Construtor sem parâmetros**: Lê os dados diretamente com `Scanner` e fecha ao final. 

```java
// Esse é o construtor padrão, usado quando ninguém passa nada. Ele mesmo cria e fecha o Scanner. Ideal para testar rápido ou usar sozinho.
// ➡️ Problema: não serve bem quando outra classe (tipo Aluno) quer reaproveitar o mesmo scanner.
public Pessoa() {
  ...
}
```

- **Construtor com parâmetro `Scanner`**: Reutiliza um `Scanner` já aberto, ideal para evitar problemas de entrada duplicada.

```java
// Esse é o construtor que recebe o Scanner de fora, ou seja, ele não cria nem fecha o scanner — só usa o que recebeu.

// ➡️ Vantagem: ideal para ser usado em herança super(scanner) e programas maiores, pois permite compartilhar o Scanner com outras classes (como Aluno ou Professor), evitando erro de input ou múltiplos fechamentos do System.in.
public Pessoa(Scanner scanner) {
  ...
}
```

#### 📄 Método

- `print()`: Exibe os dados da pessoa (nome, CPF, data de nascimento).

```java
public void print() {
  ...
}
```

---

### 🎓 Aluno (Subclasse)

```java
public class Aluno extends Pessoa {
    private String ra;
    ...
}
```

- Herda os atributos da classe `Pessoa` e adiciona o campo `RA` (Registro Acadêmico).

#### 🧱 Construtor

Recebe um `Scanner` como argumento e chama o construtor da superclasse.
```java
public Aluno(Scanner scanner) {
        super(scanner);
        System.out.print("Qual seu RA:");
        this.ra = scanner.nextLine();
    }
```

#### 📄 Método

- `print()`: Reaproveita o método da superclasse e imprime também o RA do aluno.
```java
//O @Override serve para indicar que um método está sobrescrevendo um método da superclasse.
@Override 
    public void print() {
        super.print();
        System.out.println("RA: " + ra);
    }
```

#### ▶️ Execução

```java
public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);
    Aluno aluno = new Aluno(scanner);
    aluno.print();
    scanner.close();
}
```

---

### 👨‍🏫 Professor (Subclasse)

```java
private String rd;
```

- Herda de `Pessoa` e adiciona o campo `RD` (Registro Docente).

#### 🧱 Construtor

Semelhante ao da classe `Aluno`, utiliza `Scanner` e chama a superclasse.

#### 📄 Método

- `print()`: Mostra os dados de `Pessoa` e o RD do professor.

#### ▶️ Execução

```java
public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);
    Professor professor = new Professor(scanner);
    professor.print();
    scanner.close();
}
```

---

## 📚 Conceitos Envolvidos

- **Herança** 🧬: `Aluno` e `Professor` reutilizam código da classe `Pessoa`.
- **Encapsulamento** 🔒: Atributos privados e acesso controlado.
- **Construtores** 🏗️: Inicialização dos objetos com ou sem parâmetro.
- **Sobrescrita de métodos (Override)** 🔁: Métodos redefinidos nas subclasses.
- **Entrada com `Scanner`** 🧾: Interatividade com o usuário via terminal.

---

## 🧠 Boas Práticas

- Use um único objeto `Scanner` em toda a execução.
- Evite fechar o `Scanner` dentro de classes que ainda dependem dele.
- Utilize `super()` para reaproveitar o construtor da classe pai.
- Sempre sobrescreva métodos como `print()` de forma contextual.

---

## ⚙️ Como Compilar e Rodar

1. Compile todos os arquivos `.java`:
   ```bash
   javac Pessoa.java Aluno.java Professor.java
   ```

2. Execute o programa desejado:
   - Para **Aluno**:
     ```bash
     java Aluno
     ```
   - Para **Professor**:
     ```bash
     java Professor
     ```

---

## ✅ Exemplo de Saída

```
Nome: João Silva
CPF: 123.456.789-00
Data de nascimento: 01/01/2000
Qual seu RA: 112233
------------------------------
Nome: João Silva
CPF: 123.456.789-00
Data de Nascimento: 01/01/2000
RA: 112233
```

## ☕ Código JAVA

### 🧑 Pessoa.java

```java
import java.util.Scanner;

public class Pessoa {
    private String nome;
    private String cpf;
    private String d_nasc;

    public Pessoa() {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Nome: ");
        this.nome = scanner.nextLine();
        System.out.print("CPF: ");
        this.cpf = scanner.nextLine();
        System.out.print("Data de nacimento: ");
        this.d_nasc = scanner.nextLine();

        scanner.close();
        
    }

    public Pessoa(Scanner scanner) {
        System.out.print("Nome: ");
        this.nome = scanner.nextLine();
        System.out.print("CPF: ");
        this.cpf = scanner.nextLine();
        System.out.print("Data de nascimento: ");
        this.d_nasc = scanner.nextLine();
    }

    public void print() {
        System.out.println("Nome: " + nome);
        System.out.println("CPF: " + cpf);
        System.out.println("Data de Nascimento: " + d_nasc);
    }
    
}  
```

### 📖 Aluno.java

```java
import java.util.Scanner;

public class Aluno extends Pessoa {
    private String ra;

    public Aluno(Scanner scanner) {
        super(scanner);
        System.out.print("Qual seu RA:");
        this.ra = scanner.nextLine();
    }

    @Override
    public void print() {
        super.print();
        System.out.println("RA: " + ra);
    }
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Aluno aluno = new Aluno(scanner);
        aluno.print();
        scanner.close();
    }
}
```

### 📚 Professor.java

```java
import java.util.Scanner;

public class Professor extends Pessoa {
    private String rd;

    public Professor(Scanner scanner){
        super(scanner);
        System.out.print("Qual seu RD: ");
        this.rd = scanner.nextLine();

    }

    @Override
    public void print() {
        super.print();
        System.out.println("RD: " + rd);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Professor professor = new Professor(scanner);
        professor.print();
        scanner.close();
    }
    
}
```

## 👨‍💻 Download do código está na Releases