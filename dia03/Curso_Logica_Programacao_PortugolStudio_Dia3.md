## Dia 3 — Curso Completo de Lógica de Programação com Português Estruturado

### Entrada e Saída de Dados: ESCREVA e LEIA

No Portugol Studio, a entrada e saída de dados é feita através das funções `escreva` e `leia`. Essas funções são fundamentais para a comunicação com o usuário: uma exibe mensagens no terminal e a outra recebe valores digitados pelo usuário.

#### escreva

A função `escreva` exibe uma mensagem ou o valor de uma variável na tela.

```portugol
escreva("Olá, mundo!")
```

Também é possível concatenar strings com valores de variáveis:

```portugol
inteiro idade = 25
escreva("A idade digitada foi: ", idade)
```

> 💡 Quem executa o comando `escreva` é o computador, ou seja, é ele quem escreve algo no terminal.

#### leia

A função `leia` é usada para capturar um valor digitado pelo usuário e armazená-lo em uma variável.

```portugol
inteiro numero
escreva("Digite um número: ")
leia(numero)
```

> 💡 Quem executa o comando `leia` é o usuário, pois é ele quem fornece os dados por meio do teclado.

#### Uso do `\n` para Salto de Linha

O caractere especial `\n` é utilizado para realizar um salto de linha no terminal.

```portugol
escreva("Primeira linha\nSegunda linha")
```

```portugol
inteiro idade = 30
escreva("Idade informada:\n", idade)
```

> ✅ Também é possível usar a vírgula (`,`) para concatenar elementos no `escreva`, sendo essa a principal forma de unir textos e valores no Portugol Studio.

#### Nota pessoal:

É interessante observar que, mesmo em uma linguagem de ensino como o Portugol Studio, a distinção clara entre entrada e saída já introduz conceitos básicos de I/O (Input/Output) fundamentais para toda programação. O uso de `\n` como caractere de escape aproxima a didática de outras linguagens reais, como C e Python, e reforça a ideia de boa apresentação visual ao usuário.

### Exemplo Prático em Portugol Studio

```portugol
programa
{
    inteiro idade
    real altura
    caractere nome[30]

    funcao inicio()
    {
        escreva("Digite seu nome: ")
        leia(nome)

        escreva("Digite sua idade: ")
        leia(idade)

        escreva("Digite sua altura (em metros): ")
        leia(altura)

        escreva("\n--- DADOS INFORMADOS ---\n")
        escreva("Nome: ", nome, "\n")
        escreva("Idade: ", idade, " anos\n")
        escreva("Altura: ", altura, " metros")
    }
}
```

Esse exemplo une os conceitos de entrada (`leia`) e saída (`escreva`), concatenação com vírgulas e uso do caractere especial `\n` para organização da apresentação no terminal.

---

### ➕ Operadores Aritméticos em Portugol Studio

| Operador | Nome             | Exemplo | Resultado |
|----------|------------------|---------|-----------|
| +        | Soma             | 5 + 3   | 8         |
| -        | Subtração        | 10 - 7  | 3         |
| *        | Multiplicação    | 4 * 6   | 24        |
| /        | Divisão          | 8 / 2   | 4         |
| %        | Módulo (resto)   | 9 % 2   | 1         |

#### ✏️ Expressões Aritméticas

```portugol
a + b
x * y - 2
(n1 + n2) / 2
```

#### ⚠️ Precedência de Operadores (resumido)

```portugol
resultado = (a + b) * c
```

> O uso dos parênteses garante clareza e evita resultados incorretos.

#### 📚 Exemplo completo: operações básicas

```portugol
programa
{
    inteiro x, y, som, sub, multi, div, mod

    funcao inicio()
    {
        escreva("Entre com algum valor inteiro: ")
        leia(x)

        escreva("Entre com algum outro valor inteiro: ")
        leia(y)

        som = x + y
        sub = x - y
        multi = x * y
        div = x / y
        mod = x % y

        escreva("O resultado da soma é: ", som, "\n")
        escreva("O resultado da subtração é: ", sub, "\n")
        escreva("O resultado da multiplicação é: ", multi, "\n")
        escreva("O resultado da divisão é: ", div, "\n")
        escreva("O resultado do resto da divisão é: ", mod)
    }
}
```

---

### ⚖️ Exemplo com cálculo do Delta (Equação do Segundo Grau)

```portugol
programa
{
    inteiro a, b, c, delta

    funcao inicio()
    {
        escreva("Cálculo do ▲ de uma equação do segundo grau\n")
        escreva("Digite o valor de a: ")
        leia(a)

        escreva("Digite o valor de b: ")
        leia(b)

        escreva("Digite o valor de c: ")
        leia(c)

        escreva("Equação: ", a, "x² + ", b, "x + ", c, " = 0")

        // Cálculo do delta:
        delta = b * b - 4 * a * c
        escreva("\nO ▲ da equação é: ", delta)
    }
}
```

> ℹ️ Um delta positivo indica que a equação possui duas raízes reais. O próximo passo natural seria calcular essas raízes utilizando raiz quadrada, o que exige o uso de bibliotecas matemáticas — assunto que será abordado em aulas futuras.

---

## 🔢 OPERADORES E EXPRESSÕES RELACIONAIS

Operadores relacionais — também chamados de operadores de comparação — são usados para estabelecer uma relação entre dois valores. O resultado é sempre um valor lógico: `VERDADEIRO` ou `FALSO`.

| Operador | Descrição        | Exemplo | Resultado   |
|----------|------------------|---------|-------------|
| ==       | Igual a          | 5 == 5  | VERDADEIRO  |
| !=       | Diferente de     | 5 != 3  | VERDADEIRO  |
| >        | Maior que        | 7 > 5   | VERDADEIRO  |
| <        | Menor que        | 3 < 6   | VERDADEIRO  |
| >=       | Maior ou igual a | 5 >= 5  | VERDADEIRO  |
| <=       | Menor ou igual a | 4 <= 7  | VERDADEIRO  |

```portugol
funcao inicio()
{
    inteiro x, y
    x = 10
    y = 20

    escreva("x == y: ", x == y, "\n")
    escreva("x != y: ", x != y, "\n")
    escreva("x < y: ", x < y, "\n")
    escreva("x > y: ", x > y, "\n")
    escreva("x <= y: ", x <= y, "\n")
    escreva("x >= y: ", x >= y, "\n")
}
```

---

## 🔐 OPERADORES LÓGICOS (E, OU, NÃO)

Os **operadores lógicos** permitem trabalhar com **múltiplas condições relacionais** dentro de uma mesma expressão.

### 📌 Conceito de Valor Lógico

- `VERDADEIRO` (true)
- `FALSO` (false)

### 📊 Tabela Verdade – OPERADOR LÓGICO **E**

| Expressão A | Expressão B | A E B      |
|-------------|-------------|------------|
| VERDADEIRO  | VERDADEIRO  | VERDADEIRO |
| VERDADEIRO  | FALSO       | FALSO      |
| FALSO       | VERDADEIRO  | FALSO      |
| FALSO       | FALSO       | FALSO      |

### 📊 Tabela Verdade – OPERADOR LÓGICO **OU**

| Expressão A | Expressão B | A OU B     |
|-------------|-------------|------------|
| VERDADEIRO  | VERDADEIRO  | VERDADEIRO |
| VERDADEIRO  | FALSO       | VERDADEIRO |
| FALSO       | VERDADEIRO  | VERDADEIRO |
| FALSO       | FALSO       | FALSO      |