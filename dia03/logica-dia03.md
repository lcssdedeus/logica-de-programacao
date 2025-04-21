# Dia 3 — Curso Completo de Lógica de Programação com Português Estruturado

## Entrada e Saída de Dados: `ESCREVA` e `LEIA`

No Portugol Studio, a entrada e saída de dados é feita através das funções `escreva` e `leia`. Essas funções são fundamentais para a comunicação com o usuário: uma exibe mensagens no terminal e a outra recebe valores digitados pelo usuário.

### `escreva`

A função `escreva` exibe uma mensagem ou o valor de uma variável na tela.

```portugol
escreva("Olá, mundo!")
```

Também é possível concatenar strings com valores de variáveis:

```portugol
inteiro idade = 25
escreva("A idade digitada foi: ", idade)
```

**Importante:**  
Quem executa o comando `escreva` é o **computador**, ou seja, é ele quem escreve algo no terminal.

### `leia`

A função `leia` é usada para capturar um valor digitado pelo usuário e armazená-lo em uma variável.

```portugol
inteiro numero
escreva("Digite um número: ")
leia(numero)
```

**Importante:**  
Quem executa o comando `leia` é o **usuário**, pois é ele quem fornece os dados por meio do teclado.

---

### Uso do `\n` para Salto de Linha

O caractere especial `\n` é utilizado para realizar um **salto de linha** no terminal.

#### Exemplo 1: Usando dentro de uma string

```portugol
escreva("Primeira linha\nSegunda linha")
```

#### Exemplo 2: Concatenando com variável

```portugol
inteiro idade = 30
escreva("Idade informada:\n", idade)
```

Também é possível usar a vírgula (`,`) para **concatenar** elementos no `escreva`, sendo essa a principal forma de unir textos e valores no Portugol Studio.

---

**Nota pessoal:**  
É interessante observar que, mesmo em uma linguagem de ensino como o Portugol Studio, a distinção clara entre entrada e saída já introduz conceitos básicos de I/O (Input/Output) fundamentais para toda programação. O uso de `\n` como caractere de escape aproxima a didática de outras linguagens reais, como C e Python, e reforça a ideia de boa apresentação visual ao usuário.

---

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

## ➕ Operadores Aritméticos em Portugol Studio

Abaixo está a tabela com os operadores aritméticos básicos utilizados na linguagem Portugol Studio:

| Operador | Nome             | Exemplo       | Resultado |
|----------|------------------|---------------|-----------|
| `+`      | Soma             | `5 + 3`       | `8`       |
| `-`      | Subtração        | `10 - 7`      | `3`       |
| `*`      | Multiplicação    | `4 * 6`       | `24`      |
| `/`      | Divisão          | `8 / 2`       | `4`       |
| `%`      | Módulo (resto)   | `9 % 2`       | `1`       |

## ✏️ Expressões Aritméticas

Uma expressão aritmética pode conter variáveis e operadores que representam um cálculo. Exemplos:

- `a + b`
- `x * y - 2`
- `(n1 + n2) / 2`

## ⚠️ Precedência de Operadores (resumido)

Operadores como multiplicar `*`, dividir `/` e módulo `%` têm maior precedência que soma `+` e subtração `-`. Para alterar a ordem de execução, utilizamos **parênteses**:

```portugol
resultado = (a + b) * c
```

O uso dos parênteses garante clareza e evita resultados incorretos.

## 📚 Exemplo completo: operações básicas

Este exemplo foi baseado em um exercício dado durante a aula pelo professor Fábio (Bóson Treinamentos), que nos solicitou criar um programa para realizar todas as operações aritméticas básicas entre dois números inteiros:

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

## ⚖️ Exemplo com cálculo do Delta (Equação do Segundo Grau)

Esse exemplo foi fornecido pelo professor Fábio (Bóson Treinamentos) como introdução ao uso de expressões matemáticas mais complexas. Aqui é demonstrado como calcular o valor do **delta (▲)**:

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

        escreva("Equação: " + a + "x² + " + b + "x + " + c + " = 0")

        // Cálculo do delta:
        delta = b * b - 4 * a * c
        escreva("\nO ▲ da equação é: ", delta)
    }
}
```

> ℹ️ **Nota importante:** Um delta positivo indica que a equação possui duas raízes reais. O próximo passo natural seria calcular essas raízes utilizando **raiz quadrada**, o que exige o uso de **bibliotecas matemáticas** — assunto que será abordado em aulas futuras.

## 🔢 OPERADORES E EXPRESSÕES RELACIONAIS

Operadores relacionais — também chamados de **operadores de comparação** — são usados para estabelecer uma **relação entre dois valores**, que são chamados de **operandos**. O resultado desse tipo de operação é sempre um **valor lógico**, ou seja, **verdadeiro (VERDADEIRO)** ou **falso (FALSO)**.

Esses operadores **comparam valores do mesmo tipo**, ou seja, não é possível comparar diretamente um número com uma string, por exemplo. Eles são fundamentais em **estruturas de decisão (condicionais)** e **estruturas de repetição (loops)**, que dependem de expressões lógicas como critério de execução.

### ⚠️ Diferença entre = e ==

- O operador `=` é utilizado para **atribuição** de valor a uma variável.
  - Exemplo: `x = 5` → o valor 5 está sendo atribuído à variável `x`.
- O operador `==` é utilizado para **comparação** de igualdade entre dois valores.
  - Exemplo: `x == 5` → verifica se o valor da variável `x` é igual a 5.

---

### 📊 Tabela de Operadores Relacionais

| Operador | Descrição                          | Exemplo       | Resultado |
|----------|------------------------------------|---------------|-----------|
| `==`     | Igual a                            | `5 == 5`      | VERDADEIRO |
| `!=`     | Diferente de                       | `5 != 3`      | VERDADEIRO |
| `>`      | Maior que                          | `7 > 5`       | VERDADEIRO |
| `<`      | Menor que                          | `3 < 6`       | VERDADEIRO |
| `>=`     | Maior ou igual a                   | `5 >= 5`      | VERDADEIRO |
| `<=`     | Menor ou igual a                   | `4 <= 7`      | VERDADEIRO |

---

### 🧠 Observações Importantes

- Sempre que uma **expressão relacional** for avaliada, o retorno será um valor **lógico** (`VERDADEIRO` ou `FALSO`).
- Esses resultados são usados principalmente em:
  - **Condicionais**, como `se...entao...fimse`
  - **Laços de repetição**, como `enquanto...faca`

---

### 💻 Exemplos de Expressões Relacionais

```portugol
programa
{
    funcao inicio()
    {
        inteiro x, y
        x = 10
        y = 20

        escreva("x == y: ", x == y, "\n") // FALSO
        escreva("x != y: ", x != y, "\n") // VERDADEIRO
        escreva("x < y: ", x < y, "\n")   // VERDADEIRO
        escreva("x > y: ", x > y, "\n")   // FALSO
        escreva("x <= y: ", x <= y, "\n") // VERDADEIRO
        escreva("x >= y: ", x >= y, "\n") // FALSO
    }
}
```

## 🔐 OPERADORES LÓGICOS (E, OU, NÃO)

Os **operadores lógicos** (também chamados de **booleanos**) permitem trabalhar com **múltiplas condições relacionais** dentro de uma mesma expressão. Eles operam sobre **valores lógicos**, como `VERDADEIRO` ou `FALSO`, e retornam sempre um **resultado lógico**.

Os mais usados são:

- **E**
- **OU**
- **NÃO**

---

### 📌 Conceito de Valor Lógico

- `VERDADEIRO` (também representado por `true`)
- `FALSO` (também representado por `false`)

### 📊 Tabela Verdade – OPERADOR LÓGICO **E**

O operador **E** (representado por `&&` ou `e` no Portugol Studio) **retorna VERDADEIRO somente se ambas as condições forem verdadeiras**.

| Expressão A | Expressão B | A E B      |
|-------------|-------------|------------|
| VERDADEIRO  | VERDADEIRO  | VERDADEIRO |
| VERDADEIRO  | FALSO       | FALSO      |
| FALSO       | VERDADEIRO  | FALSO      |
| FALSO       | FALSO       | FALSO      |

---

### 📊 Tabela Verdade – OPERADOR LÓGICO **OU**

O operador **OU** (representado por `||` ou `ou` no Portugol Studio) **retorna VERDADEIRO se pelo menos uma das condições for verdadeira**.

| Expressão A | Expressão B | A OU B     |
|-------------|-------------|------------|
| VERDADEIRO  | VERDADEIRO  | VERDADEIRO |
| VERDADEIRO  | FALSO       | VERDADEIRO |
| FALSO       | VERDADEIRO  | VERDADEIRO |
| FALSO       | FALSO       | FALSO      |

---

### 📊 Tabela Verdade – OPERADOR LÓGICO **NÃO**

O operador **NÃO** (representado por `!` ou `nao` no Portugol Studio) **inverte o valor lógico**.

| Expressão   | NÃO Expressão |
|-------------|---------------|
| VERDADEIRO  | FALSO         |
| FALSO       | VERDADEIRO    |

---

### 💡 Contextualizando: Operadores Lógicos no Mundo Real

Imagine um sistema que verifica se uma pessoa pode entrar em uma sala de servidores. Para isso, ela deve:

- Ter crachá de acesso **E**
- Estar com o uniforme adequado

Usamos o **E** porque **ambas as condições precisam ser verdadeiras**.

Se fosse:

- Ter crachá de acesso **OU**
- Ter permissão temporária

A condição seria verdadeira mesmo que **apenas uma delas fosse verdadeira**, logo usamos o **OU**.

Se quisermos saber se **a pessoa não está autorizada**, usamos o **NÃO** sobre o resultado da verificação de autorização.

---

### 💻 Exemplo no Portugol Studio

```portugol
programa
{
    funcao inicio()
    {
        logico temCrachá, temUniforme, permissaoTemporaria
        temCrachá = verdadeiro
        temUniforme = falso
        permissaoTemporaria = verdadeiro

        escreva("Acesso com E: ", temCrachá e temUniforme, "\n")           // FALSO
        escreva("Acesso com OU: ", temCrachá ou permissaoTemporaria, "\n") // VERDADEIRO
        escreva("Negação do uniforme: ", nao temUniforme, "\n")             // VERDADEIRO
    }
}
```

💡 **Nota Importante:** Os exemplos apresentados aqui não são, necessariamente, os mesmos utilizados pelo professor Fábio durante a aula em vídeo. Em alguns momentos, optei por utilizar variações ou novos exemplos com o objetivo de evitar repetições e incentivar a prática ativa. A ideia é reforçar o conteúdo e estimular a autonomia na resolução de problemas, o mesmo pode se seguir em outros exemplos a seguir.

## Associatividade e Precedência dos Operadores

Na programação, a ordem em que os operadores são avaliados dentro de uma expressão é definida por dois conceitos fundamentais: **precedência** e **associatividade**.

- **Precedência** determina quais operadores são avaliados antes de outros.
- **Associatividade** determina a ordem da avaliação **quando operadores de mesma precedência aparecem juntos** em uma expressão.

> **Observação:** Parênteses `()` sempre têm **maior precedência**, e podem (e devem) ser usados para tornar expressões mais claras ou alterar a ordem natural da avaliação.

---

### 🧮 Tabela de Precedência e Associatividade dos Operadores

| Nível | Categoria                 | Operador(es)                               | Associatividade |
|-------|---------------------------|---------------------------------------------|-----------------|
| 1     | **Parênteses**            | `( )`                                       | ED              |
| 2     | **Exponenciação**         | `^`                                         | DE              |
| 3     | **Pós-fixo**              | `++`, `--`                                  | ED              |
| 4     | **Unário**                | `+`, `-`, `!`, `~`                          | DE              |
| 5     | **Multiplicação/Divisão** | `*`, `/`, `%`                               | ED              |
| 6     | **Adição/Subtração**     | `+`, `-`                                    | ED              |
| 7     | **Deslocamento**         | `<<`, `>>`                                  | ED              |
| 8     | **Relacional**           | `<`, `<=`, `>`, `>=`                        | ED              |
| 9     | **Igualdade**            | `==`, `!=`                                  | ED              |
| 10    | **AND Bitwise**          | `&`                                         | ED              |
| 11    | **XOR Bitwise**          | `^` (bit a bit)                             | ED              |
| 12    | **OR Bitwise**           | `|`                                         | ED              |
| 13    | **E LÓGICO**             | `&&` ou `E`                                 | ED              |
| 14    | **OU LÓGICO**            | `||` ou `OU`                                | ED              |
| 15    | **Condicional (Ternário)** | `? :`                                    | DE              |
| 16    | **Atribuição**           | `=`, `+=`, `-=`, `*=`, `/=`, `%=`           | DE              |

---

### 🔍 Considerações Importantes

- O uso correto dos parênteses torna expressões complexas mais compreensíveis e evita ambiguidades.
- A ordem de avaliação natural pode levar a **resultados inesperados** se a precedência e a associatividade não forem bem compreendidas.
- Operações lógicas e bitwise, apesar de semelhantes, **operam em níveis distintos**: lógicas com valores booleanos, bitwise com bits individuais.

---

### 💡 Exemplo de Código – Portugal Studio

```portugol
programa
{
  inteiro a, b, c, resultado1, resultado2, delta

  funcao inicio()
  {
    a = 4
    b = 2
    c = 1

    // Expressão sem parênteses:
    resultado1 = a + b * c - b

    // Expressão com parênteses alterando a precedência:
    resultado2 = (a + b) * (c - b)

    escreva("Resultado da expressão SEM parênteses: ", resultado1, "\n")
    escreva("Resultado da expressão COM parênteses: ", resultado2, "\n")

    // Expressão com operadores relacionais e lógicos:
    se ((a > b) E (c < a)) entao
    {
      escreva("Expressão relacional e lógica avaliada como VERDADEIRA\n")
    }
    senao
    {
      escreva("Expressão relacional e lógica avaliada como FALSA\n")
    }

    // Cálculo do delta para mostrar uso de operadores:
    escreva("Cálculo do delta da equação do 2º grau\n")
    escreva("Digite o valor de a: ")
    leia(a)
    escreva("Digite o valor de b: ")
    leia(b)
    escreva("Digite o valor de c: ")
    leia(c)

    delta = b * b - 4 * a * c

    escreva("Equação: ", a, "x² + ", b, "x + ", c, " = 0\n")
    escreva("Delta = ", delta, "\n")

    escreva("Se delta for positivo, há duas raízes reais.\n")
    escreva("Uso da raiz quadrada será estudado com a biblioteca matemática futuramente.\n")
  }
}
```

### Nota Pessoal:

A compreensão da precedência e associatividade dos operadores é essencial para desenvolver programas corretos e evitar ambiguidades lógicas. Quando uma expressão é mal interpretada, ela pode gerar falhas sutis e difíceis de detectar, prejudicando o funcionamento do código. Por isso, usar parênteses sempre que for necessário é uma boa prática. Isso garante clareza e segurança na avaliação das expressões.

Esse conhecimento é um passo importante para a construção de programas robustos, onde o comportamento do código seja previsível e confiável. Além disso, ele serve de base para o próximo nível de compreensão em programação, onde podemos aplicar conceitos mais avançados e otimizar nosso raciocínio lógico.

**Próximos Passos:**
- Continuar explorando operadores em diferentes contextos.
- Aprofundar no uso de parênteses para clareza.
- Praticar a resolução de expressões mais complexas, observando como a precedência e associatividade afetam o resultado.

No começo, pode parecer confuso, mas com prática e revisão constante, esses conceitos se tornarão naturais no seu dia a dia de programador. E lembre-se: parênteses são seus aliados! Não hesite em usá-los sempre que houver alguma dúvida sobre a ordem de execução. Isso tornará seu código mais seguro e fácil de entender para qualquer pessoa que o leia.

Cada novo conceito que você aprender agora será a base para entender aspectos mais avançados de programação no futuro, então aproveite esse momento de aprofundamento para solidificar essas ideias.
