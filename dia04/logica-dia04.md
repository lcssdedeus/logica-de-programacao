# Dia 04 — Curso Completo de Lógica de Programação com Português Estruturado

No quarto dia de estudos, aprofundamos o conceito de **decisão condicional**, trabalhando com estruturas de **condicional simples**, **condicional composta** e **condicional encadeada** (também chamada de desvio condicional aninhado), fundamentais para permitir que o algoritmo tome decisões baseadas em diferentes cenários. Em seguida, exploramos o comando **ESCOLHA...CASO**, uma alternativa prática para múltiplas verificações de valores, facilitando a leitura e organização das decisões dentro do código.

Prosseguimos aprendendo como utilizar **bibliotecas e funções** no Portugol Studio para expandir as funcionalidades dos algoritmos, como, por exemplo, gerar **números aleatórios**. Finalizamos o dia estudando os **laços de repetição**, abordando o **ENQUANTO** e o **PARA**, estruturas essenciais para executar ações repetitivas com eficiência, além do **encadeamento de laços** (ou **repetições aninhadas**), ampliando ainda mais nossa capacidade de construir algoritmos mais dinâmicos e elaborados.

## 🧭 Decisão Condicional Simples

A **decisão condicional simples** é utilizada quando se deseja executar um bloco de instruções **somente se uma condição for verdadeira**. Se a condição for falsa, **nada acontece**.

Essa estrutura é muito útil para verificar situações específicas em que uma ação só deve ocorrer mediante um determinado critério lógico.

---

### 🔤 Sintaxe no Portugol Studio

```portugol
se (condição) entao
{
    // Instruções a serem executadas se a condição for verdadeira
}
```

---

### 💡 Explicação

- `se`: inicia a estrutura de decisão.
- `(condição)`: expressão lógica que será avaliada.
- `entao`: indica o início do bloco que será executado caso a condição seja verdadeira.
- `fimse`: encerra a estrutura condicional.

---

### 📘 Exemplo Simples

```portugol
programa
{
    real nota

    funcao inicio()
    {
        escreva("Digite sua nota final: ")
        leia(nota)

        se (nota >= 7) {
            escreva("Parabéns! Você foi aprovado.")
        }
    }
}
```

---

### 🧠 Observações

- Nesse exemplo, a mensagem **só será exibida se a nota for maior ou igual a 7**.
- Caso o usuário digite uma nota menor que 7, **nada acontecerá** (nenhuma mensagem será exibida).
- Esse tipo de estrutura é ideal para **testes simples**, como verificar se uma pessoa atingiu a média mínima ou se um número é positivo.

---

## 🧭 Decisão Condicional Composta

A **decisão condicional composta** é utilizada quando se deseja executar **um bloco de instruções se a condição for verdadeira** e **outro bloco de instruções caso a condição seja falsa**.

Essa estrutura amplia a condicional simples, permitindo ações alternativas quando o critério lógico não é satisfeito.

---

### 🔤 Sintaxe no Portugol Studio

```portugol
se (condição) entao
{
    // Instruções a serem executadas se a condição for verdadeira
}
senao
{
    // Instruções a serem executadas se a condição for falsa
}
```

---

### 💡 Explicação

- `se`: inicia a estrutura de decisão.
- `(condição)`: expressão lógica a ser avaliada.
- `entao`: início do bloco para condição verdadeira.
- `senao`: início do bloco para condição falsa.
- `fimse`: encerra a estrutura condicional.

---

### 📘 Exemplo Continuando o Raciocínio da Condicional Simples

```portugol
programa
{
    real nota

    funcao inicio()
    {
        escreva("Digite sua nota final: ")
        leia(nota)

        se (nota >= 7) 
        {
            escreva("Parabéns! Você foi aprovado.")
        }
        senao
        {
            escreva("Infelizmente, você foi reprovado.")
        }
    }
}
```

---

### 🧠 Observações

- Agora, **sempre haverá uma resposta**, independente do valor da nota.
- Se a nota for **7 ou maior**, a mensagem de aprovação será exibida.
- Se a nota for **menor que 7**, o aluno verá a mensagem de reprovação.
- Essa estrutura é essencial quando queremos **cobrir todos os casos possíveis** (verdadeiro e falso) de uma condição.

---

## 🧭 Desvio Condicional Encadeado (ou Aninhado)

O **desvio condicional encadeado** (também chamado de **desvio aninhado**) é utilizado quando é necessário realizar **vários testes sequenciais**, um dentro do outro. Ele permite criar decisões mais complexas, analisando múltiplas condições em sequência.

---

### 🔤 Sintaxe no Portugol Studio

```portugol
se (condição1) entao
{
    // Instruções se condição1 for verdadeira
}
senao
{
    se (condição2) entao
    {
        // Instruções se condição2 for verdadeira
    }
    senao
    {
        // Instruções se nenhuma condição for verdadeira
    }
    fimse
}
```

---

### 💡 Explicação

- O segundo `se` é **inserido** dentro do bloco do `senao`.
- Permite **testar uma nova condição** caso a primeira tenha sido falsa.
- Esse processo pode ser **repetido diversas vezes**, criando uma cadeia (ou "aninhamento") de testes.

---

### 📘 Exemplo Simples com Base no Anterior

```portugol
programa
{
    real nota

    funcao inicio()
    {
        escreva("Digite sua nota final: ")
        leia(nota)

        se (nota >= 7)
        {
            escreva("Parabéns! Você foi aprovado.")
        }
        senao
        {
            escreva("Você foi reprovado.")
        }
    }
}
```

---

### 📘 Exemplo Mais Completo: Média e Faltas

```portugol
programa
{
    real nota
    inteiro faltas

    funcao inicio()
    {
        escreva("Digite sua nota final: ")
        leia(nota)

        escreva("Digite o número de faltas: ")
        leia(faltas)

        se (faltas >= 10)
        {
            escreva("Reprovado por faltas.")
        }
        senao
        {
            se (nota >= 7)
            {
                escreva("Aprovado!")
            }
            senao
            {
                se (nota >= 5)
                {
                    escreva("Em recuperação.")
                }
                senao
                {
                    escreva("Reprovado por nota.")
                }
            }
        }
    }
}
```

---

### 🧠 Observações

- Se o número de faltas for **10 ou mais**, o aluno é reprovado automaticamente.
- Caso contrário, a média é verificada:
  - **Nota ≥ 7**: Aprovado.
  - **Nota ≥ 5 e < 7**: Recuperação.
  - **Nota < 5**: Reprovado.
- A estrutura aninhada evita a necessidade de múltiplas instruções separadas e permite maior **organização e clareza** no processo de decisão.

---

## 🧭 Desvio Condicional: Comando `ESCOLHA...CASO`

O comando **ESCOLHA CASO** é utilizado quando se deseja selecionar **uma opção dentre várias possíveis**, eliminando a necessidade de escrever múltiplos testes `SE...ENTAO`. É uma forma **mais organizada** e **mais eficiente** de lidar com diversas alternativas de decisão.

> ⚡ As palavras **ESCOLHA** e **CASO** são comandos no Portugol Studio, portanto, devem ser destacadas como tais.

---

### 🔤 Sintaxe no Portugol Studio

```portugol
escolha (expressao)
{
    caso valor1:
        // Instruções para o valor1
        pare

    caso valor2:
        // Instruções para o valor2
        pare

    ...

    caso valorN:
        // Instruções para o valorN
        pare

    caso contrario:
        // Instruções caso nenhum valor seja correspondente
}
```

---

### 💡 Explicação

- `escolha`: Inicia a estrutura de múltipla escolha, avalia uma expressão.
- `caso`: Cada valor possível é testado.
- `pare`: Finaliza o bloco do `caso` para que não continue testando os demais.
- `caso contrario`: Executado se **nenhum dos valores anteriores** for correspondente.

---

### 📘 Exemplo no Portugol Studio

```portugol
programa
{
    inteiro opcao

    funcao inicio()
    {
        escreva("Menu de opções:\n")
        escreva("1 - Cadastrar produto\n")
        escreva("2 - Excluir produto\n")
        escreva("3 - Atualizar produto\n")
        escreva("4 - Sair\n")
        escreva("Escolha uma opção: ")
        leia(opcao)

        escolha (opcao)
        {
            caso 1:
                escreva("Produto cadastrado com sucesso!")
                pare

            caso 2:
                escreva("Produto excluído com sucesso!")
                pare

            caso 3:
                escreva("Produto atualizado com sucesso!")
                pare

            caso 4:
                escreva("Saindo do sistema...")
                pare

            caso contrario:
                escreva("Opção inválida. Tente novamente.")
        }
    }
}
```

---

### 🧠 Observações

- **Cada `caso` deve ser encerrado com `pare`** para evitar a execução dos próximos casos.
- O uso de `caso contrario` é opcional, mas **recomendado** para tratamento de entradas inválidas.
- A estrutura do comando **ESCOLHA...CASO** deixa o código **mais limpo e organizado** do que múltiplos `se...entao`.

---

## 📚 Como Usar Bibliotecas e Suas Funções no Portugol Studio

As **bibliotecas** no Portugol Studio são conjuntos de funções prontas que ampliam as capacidades dos programas, permitindo realizar operações mais complexas de forma prática e rápida.

---

### 💡 O que são Bibliotecas?

- Conjunto de códigos e funções reutilizáveis.
- Evitam a necessidade de escrever o mesmo código repetidamente.
- Facilitam tarefas comuns como cálculos matemáticos, manipulação de textos, geração de números aleatórios, entre outras.

---

### 🧩 Por que Usar Funções de Bibliotecas?

- **Economia de tempo**: funções prontas para tarefas comuns.
- **Organização**: separação de funcionalidades específicas.
- **Segurança**: funções testadas e mais confiáveis.

---

### 🛠️ Como Incluir Bibliotecas no Portugol Studio

Para usar uma biblioteca, é necessário **importá-la** no início do programa utilizando o comando `inclua biblioteca`.

### 🔤 Sintaxe

```portugol
inclua biblioteca nome_da_biblioteca
```

Se desejar **usar um apelido (alias)** para facilitar a escrita, a sintaxe correta é:

```portugol
inclua biblioteca nome_da_biblioteca --> apelido
```

> 🔹 O operador usado para apelido é `-->` (dois traços e o símbolo de maior).

---

### 📘 Exemplo Sem Apelido

```portugol
programa
{
    inclua biblioteca Matematica

    funcao inicio()
    {
        escreva("Raiz quadrada de 25 é: ", Matematica.raiz(25, 2))
    }
}
```

---

### 📘 Exemplo Com Apelido

```portugol
programa
{
    inclua biblioteca Matematica --> mat

    funcao inicio()
    {
        escreva("Raiz quadrada de 25 é: ", mat.raiz(25, 2))
    }
}
```

> 🔹 Observe que com o apelido `mat`, o código fica mais enxuto e limpo.

---

### 🗂️ Principais Bibliotecas do Portugol Studio

| Biblioteca | Descrição                     | Exemplos de Funções                                 |
|------------|---------------------------------|-----------------------------------------------------|
| Matematica | Funções matemáticas avançadas  | `raiz(radicando, indice)`, `potencia(base, expoente)`, `logaritmo(numero, base)`, `seno(angulo)` |
| Texto      | Manipulação de strings         | `numero_caracteres(cadeia)`, `extrair_subtexto(cad,posicao_inicial, posicao_final)` |
| Util       | Utilitários diversos           | `sorteia(minimo, maximo)`, `aguarde(intervalo)`, `numero_elementos(*&vetor[])` |

---

### 📚 Exemplo Usando Várias Bibliotecas

```portugol
programa
{
    inclua biblioteca Matematica --> mat
    inclua biblioteca Texto --> txt
    inclua biblioteca Util --> utl

    funcao inicio()
    {
        real resultado
        cadeia palavra
        inteiro numero

 	      //funcao* *real* raiz(*real* radicando, *real* indice)
        resultado = mat.raiz(64, 2)
        escreva("Raiz quadrada de 64 é: ", resultado, "\n")

	      //funcao* *inteiro* numero_caracteres(*cadeia* cadeia)
        palavra = "Portugol Studio"
        escreva("Tamanho da palavra: ", txt.numero_caracteres(palavra), "\n") 

	      //funcao* *inteiro* sorteia(*inteiro* minimo, *inteiro* maximo)
        numero = utl.sorteia(1, 100)
        escreva("Número aleatório entre 1 e 100: ", numero)
    }
}
```

---

### 🧠 Observações

- O uso de **apelidos** (`alias`) é **opcional**, mas **fortemente recomendado** para tornar o código mais legível.
- No Portugol Studio, o separador entre biblioteca e função é o **ponto** (`.`) — não dois pontos.
- Sempre consulte a documentação oficial do Portugol Studio para explorar a lista completa de bibliotecas e funções disponíveis.

---

## 🎲 Como Gerar Números Aleatórios no Portugol Studio

O Portugol Studio permite a geração de **números aleatórios** utilizando funções da **biblioteca Util**. Essa funcionalidade é extremamente útil para criar programas mais dinâmicos, como jogos, sorteios e simulações.

---

### 📚 Onde Encontrar a Função

No próprio Portugol Studio, você pode acessar a função responsável pela geração de números aleatórios através do menu:

> **Ajuda → Bibliotecas → Util → Função `sorteia`**

- A função `sorteia` é utilizada para **gerar um número inteiro aleatório dentro de um intervalo especificado**.

---

### 🔤 Sintaxe Básica

```portugol
Util.sorteia(minimo, maximo)
```

- `minimo`: valor mínimo que pode ser sorteado.
- `maximo`: valor máximo que pode ser sorteado.

---

### 🖋️ Utilizando Apelido (Alias)

Para facilitar a escrita no código, é possível utilizar um apelido para a biblioteca `Util`:

```portugol
inclua biblioteca Util --> utl
```

Assim, basta escrever `utl.sorteia()` para chamar a função.

---

### 📘 Exemplo 1: Número Aleatório Simples

```portugol
programa
{
    inclua biblioteca Util --> utl

    funcao inicio()
    {
        inteiro numero

        numero = utl.sorteia(1, 10)

        escreva("Número sorteado entre 1 e 10: ", numero)
    }
}
```

---

### 📘 Exemplo 2: Sorteando Vários Números

```portugol
programa
{
    inclua biblioteca Util --> utl

    funcao inicio()
    {
        inteiro i

        escreva("Sorteando 5 números entre 1 e 100:\n")

        para (i = 1; i <= 5; i++)
        {
            escreva("Número ", i, ": ", utl.sorteia(1, 100), "\n")
        }
    }
}
```

---

### 🧠 Observações

- O intervalo passado para a função `sorteia` é **inclusivo**, ou seja, o número sorteado pode ser **igual ao valor de minimo ou maximo**.
- A biblioteca se chama **Util** no Portugol Studio, e não "Útil" (sem acento).
- A geração de números aleatórios é essencial em aplicações que envolvem incerteza, sorteios, ou escolha aleatória.

---

## 🔁 Laço de Repetição ENQUANTO

O **laço de repetição ENQUANTO** é utilizado para executar um bloco de código **enquanto uma condição lógica for verdadeira**. 

Em termos de desenvolvimento, ele é conhecido como um **loop** ou **laço de repetição** — termos comuns entre programadores para indicar que um trecho de código será repetido várias vezes, até que a condição deixe de ser satisfeita.

Essa estrutura é muito útil para automatizar repetições sem a necessidade de escrever o mesmo código múltiplas vezes.

---

### 🔤 Sintaxe no Portugol Studio

```portugol
enquanto (condição)
{
    // Bloco de código a ser repetido
}
```

---

### 💡 Explicação

- `enquanto`: comando que inicia a repetição.
- `(condição)`: expressão lógica que será avaliada a cada iteração.
- O bloco de código dentro das chaves `{}` será repetido **enquanto** a condição for verdadeira.

Assim que a condição for falsa, o laço é encerrado e o programa continua sua execução normal.

---

### 📘 Exemplo 1: Contando de 1 até 10

```portugol
programa
{
	cadeia nome
	
	funcao inicio()
	{
		escreva("Digite seu nome, ou x para parar:")
		leia(nome)

		enquanto (nome != "x") {
			escreva("Bem-vindo, " + nome, "\n")
			escreva("Digite seu nome, ou x para parar:")
			leia(nome)
		}
		escreva("Até logo!")
	}
}
```

---

### 📘 Exemplo 2: Exibindo apenas números pares de 2 a 20

```portugol
programa
{
	cadeia nome
	
	funcao inicio()
	{

		enquanto (verdadeiro) {
			escreva("Digite seu nome, ou x para parar:")
			leia(nome)
			se (nome == "x") {
				pare
			}
			escreva("Bem-vindo, " + nome, "\n")
		}
		escreva("Até logo!")
	}
}
```

---

### 🧠 Observações

- **Sempre tenha cuidado** para atualizar a variável de controle (`contador`, `numero`, etc.) dentro do laço. Caso contrário, o programa pode entrar em um **loop infinito**.
- O `ENQUANTO` avalia a condição **antes** de executar o bloco de código pela primeira vez. Se a condição já for falsa no início, o bloco **não será executado nenhuma vez**.
- Estruturas de repetição são fundamentais para otimizar a escrita de programas, reduzir erros manuais e tornar o código mais eficiente.

---

## 🔁 Laço de Repetição PARA

O **laço de repetição PARA** é utilizado para repetir um bloco de instruções **um número conhecido de vezes**. 

Diferente do `ENQUANTO`, que depende de uma condição lógica ser verdadeira, o `PARA` é geralmente utilizado **quando já se sabe antecipadamente** quantas vezes o loop deve ser executado.

---

### 🔤 Sintaxe no Portugol Studio

```portugol
para (inicialização; condição; incremento)
{
    // Bloco de código a ser repetido
}
```

- **inicialização**: definição inicial da variável de controle.
- **condição**: critério para manter o laço em execução.
- **incremento**: modificação da variável de controle a cada iteração.

---

### 💡 Explicação

- `para`: comando que inicia o laço de repetição.
- Os três parâmetros ficam **dentro do parênteses**, separados por ponto e vírgula `;`.
- Permite controlar a repetição de forma compacta e organizada.
- Se a condição for falsa logo na primeira verificação, o laço **não é executado**.

---

### 📘 Exemplo 1: Contando de 1 até 10

```portugol
programa
{
    funcao inicio()
    {
        para (inteiro i = 1; i <= 10; i = i + 1)
        {
            escreva(i, "\n")
        }
    }
}
```

---

### 📘 Exemplo 2: Gerando 5 números aleatórios únicos entre 1 e 50 (estilo loteria)

```portugol
programa
{
    inclua biblioteca Util --> utl

    inteiro numeros[5]
    inteiro i, j, sorteado
    logico repetido

    funcao inicio()
    {
        para (i = 0; i < 5; i++)
        {
            // Loop para gerar um número não repetido
            faca
            {
                sorteado = utl.sorteia(1, 50)
                repetido = falso

                // Verificar se o número já foi sorteado
                para (j = 0; j < i; j++)
                {
                    se (numeros[j] == sorteado)
                    {
                        repetido = verdadeiro
                    }
                }
            } enquanto (repetido == verdadeiro)

            numeros[i] = sorteado
        }

        // Exibir números sorteados na mesma linha
        para (i = 0; i < 5; i++)
        {
            escreva(numeros[i], " ")
        }
    }
}
```

---

### 🧠 Observações

- O comando `PARA` é ideal para quando a quantidade de repetições é **previsível**.
- No segundo exemplo, usamos a função `sorteia` da **biblioteca Util** para gerar os números aleatórios.
- A estrutura `FACA...ENQUANTO` foi usada para garantir que **não haja números repetidos** no vetor.
- Todos os números sorteados foram impressos **em uma única linha**, separados apenas por um espaço.

---

## 🔄 Encadeamento de Laços de Repetição

O **encadeamento de laços de repetição** (também chamado de **laços aninhados**) ocorre quando inserimos **um laço dentro de outro laço**.  
Essa técnica permite a criação de programas mais complexos, como a varredura de tabelas, matrizes, ou múltiplas combinações de valores.

---

### 🔤 Possibilidades de Encadeamento

No Portugol Studio, podemos combinar diferentes laços entre si:

- `ENQUANTO` **dentro de** `ENQUANTO`
- `ENQUANTO` **dentro de** `PARA`
- `PARA` **dentro de** `ENQUANTO`
- `PARA` **dentro de** `PARA`

Esses laços aninhados são úteis, por exemplo, para:

- Percorrer **linhas e colunas** de uma matriz.
- Criar **estruturas de repetição múltiplas** para combinações ou contagens mais elaboradas.
- Construir sistemas de **menu e submenu**.

---

### 💡 Conceito de Funcionamento

- O **laço externo** (o primeiro) **controla o número de repetições principais**.
- A **cada repetição do laço externo**, o **laço interno** **será executado completamente**.
- O **laço interno** **reinicia a cada nova execução** do laço externo.

Essa organização exige cuidado para que **as condições de parada** de cada laço sejam bem definidas e **não entrem em laço infinito**.

---

### 📘 Exemplo 1: PARA dentro de PARA

```portugol
programa
{
    funcao inicio()
    {
        inteiro linha, coluna

        para (linha = 1; linha <= 3; linha++)
        {
            para (coluna = 1; coluna <= 2; coluna++)
            {
                escreva("Linha: ", linha, " | Coluna: ", coluna, "\n")
            }
        }
    }
}
```

### 💡 Explicação

- O laço externo (linha) controla de 1 a 3 (três linhas).
- O laço interno (coluna) percorre de 1 a 2 (duas colunas) para cada linha.
- A cada nova linha, o contador de colunas recomeça de 1.

#### 📘 Exemplo 2: PARA dentro de ENQUANTO

```Portugol
programa
{
    inteiro i, j

    funcao inicio()
    {
        i = 10  // Começamos de 10

        enquanto (i > 0) faca
        {
            escreva("Contagem: ", i, "\n")

            // Para loop dentro do enquanto, fazendo uma contagem interna de 1 a 3
            para (j = 1; j <= 3; j++) faca
            {
                escreva("    Contagem interna de j: ", j, "\n")
            }

            i = i - 2  // Diminuímos 2 de cada vez para uma contagem mais rápida
        }

        escreva("Contagem finalizada!\n")
    }
}
```

### 💡 Explicação

**Variáveis:**
- `cont`: Controla o número de repetições no laço `para`.
- `quant`: Quantidade de números aleatórios a serem gerados.

**Fluxo do Programa:**
- O programa solicita ao usuário quantos números aleatórios deseja gerar.
- Se o usuário digitar `0`, o programa será encerrado (`pare`).
- Caso contrário, o programa gera `quant` números aleatórios entre 1 e 100.

**Estruturas de Repetição:**
- `enquanto (verdadeiro)`: Laço infinito que continua até o usuário digitar `0`.
- `para (cont = 1; cont <= quant; cont++)`: Gera os números aleatórios conforme a quantidade informada.

**Função `aleatorio(1, 100)`:** Gera um número aleatório entre 1 e 100 e o imprime.

**OBS.:** Expliquei aqui com maior quantidade de detalhes, por perceber que o assunto está cada vez mais ficando complexo, portanto, siga sempre uma frase que vivo repetindo - É DIFÍCIL, MAS É SIMPLES, É SÓ REPETIR, REPETIR E REPETIR - Repetições levam ao aprendizado nesta área 

### 🧠 Observações Importantes
O uso de laços aninhados é essencial para trabalhar com estruturas bidimensionais (como tabelas, matrizes) e resolver problemas de combinação.

Cuidado com a quantidade de repetições: laços muito profundos ou mal controlados podem tornar o programa lento.

---

## Nota pessoal:
Hoje, tivemos um bom mergulho nos conceitos que realmente fazem a programação acontecer de forma eficiente. Começamos entendendo as estruturas condicionais, que são fundamentais para qualquer programa, pois é nelas que o código decide para onde ir dependendo de algumas condições. O conceito de desvio condicional encadeado e o uso do comando "escolha caso" abriram a porta para criar decisões mais complexas dentro dos programas, algo que se torna cada vez mais necessário à medida que o código cresce.

Além disso, foi interessante ver como as bibliotecas, como a `Util`, facilitam a vida com funções prontas para uso, como a geração de números aleatórios. Esses pequenos detalhes são o que tornam o trabalho de programar mais eficiente. E os laços de repetição, como `enquanto` e `para`, trouxeram a dinâmica que todo programa precisa ter, repetindo tarefas sem precisar escrever tudo de novo. 

Tudo isso, no fim das contas, é o que dá a base sólida para dar os próximos passos na programação. Sem esses fundamentos, seria impossível avançar para desafios mais complexos. E, mesmo que a caminhada seja longa, a confiança em saber que a estrutura básica está bem construída é o que nos permite crescer e seguir em frente. Enfim, este dia foi extremamente extenso comparado aos demais, e aqui também é o que separa os "meninos" dos "homens" ou as "meninas" das "mulheres" (para ser justo), muita informação e vários conceitos técnicos, mas sigamos em frente, não só por uma carreira de sucesso e bem consolidada, mas também é porque eu amo o que tenho feito todos os dias.

## Referência principal:

REIS, Fábio dos. Curso de Lógica de Programação – Bóson Treinamentos. YouTube: [https://www.youtube.com/@bosontreinamentos](https://www.youtube.com/@bosontreinamentos)
