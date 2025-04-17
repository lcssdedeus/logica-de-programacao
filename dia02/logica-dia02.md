
# Dia 2 — Curso Completo de Lógica de Programação com Português Estruturado

## Algoritmos, Fluxograma e Diagrama de Chapin

### O que são algoritmos?
Um **algoritmo** é uma sequência finita de passos bem definidos para resolver um problema ou realizar uma tarefa. Eles são fundamentais na programação, pois definem a lógica por trás do funcionamento de programas e sistemas (mesmo já citando uma conceituação, eu preferi repetir-me, mas de outra forma aqui, para manter em mente as bases).

### Representações de algoritmos:
- **Português Estruturado**: forma textual próxima da linguagem natural, com estrutura lógica.
- **Linguagem de Programação**: usa sintaxe específica (ex: Java, Python, Portugol).
- **Fluxogramas**: diagramas com símbolos para representar o fluxo de execução.
- **Diagrama de Chapin**: alternativa visual usando colunas hierárquicas para representar estruturas lógicas.

> Dica: Utilizar **post-its** ou **papel** para esboçar algoritmos é excelente em projetos iniciais ou fluxos pequenos, ajudando a visualizar melhor a lógica.

Símbolos de fluxogramas são amplamente disponíveis online e de fácil assimilação.

---

## Tipos de Dados

Tipos de dados definem que tipo de valor uma variável pode armazenar.

### Principais tipos:

- **Numéricos**:
  - **Inteiros** (`inteiro`): sem parte decimal.
  - **Reais** (`real`): com parte decimal (ponto flutuante).

- **Caractere e Cadeia**:
  - **Caractere** (`caractere`): um único símbolo (ex: 'A').
  - **Cadeia** (`cadeia`): sequência de caracteres (ex: "Olá mundo").

- **Lógico**:
  - **Lógico** (`logico`): representa valores booleanos: `verdadeiro` ou `falso`.

> **Observação:** Tipos compostos por referência serão abordados mais adiante.

### Equivalências em outras linguagens:

| Portugol     | Java           | Python        |
|--------------|----------------|---------------|
| inteiro      | int            | int           |
| real         | double/float   | float         |
| caractere    | char           | str (1 caractere) |
| cadeia       | String         | str           |
| logico       | boolean        | bool          |

---

## Declaração e Atribuição de Variáveis

Variáveis armazenam dados temporários durante a execução do programa.

### Exemplo no Portugol Studio:

```portugol
programa
{
	// Variáveis globais
	cadeia res 
	real N1, N2, N3, N4
	logico achou
	inteiro idade
	caracter simbolo
	
	funcao inicio()
	{
		real media // Variável local
		// Operador de atribuição: = 
		idade = 25
		res = "Aprovado"
		N1 = 7.5
		N2 = N1
		simbolo = 'x'
		achou = verdadeiro
	}
}
```

### Atribuição de Valores

```portugol
idade = 25
nome = "Maria"
letra = 'A'
```

> Nota: `cadeia` usa aspas duplas, `caractere` usa aspas simples.

### Diferença entre cadeia e caractere

- `cadeia`: representa uma string, sequência de caracteres.
- `caractere`: representa um único símbolo.

---

## Padrões de Nomenclatura de Objetos

Nomenclatura clara facilita a leitura e manutenção do código.

### Não confundir com convenções de codificação (que englobam nomenclatura).

### Principais estilos:

| Nome                  | Exemplo                | Observação                              |
|-----------------------|------------------------|------------------------------------------|
| camelCase             | minhaVariavel          | usado em JavaScript para variáveis       |
| PascalCase            | MinhaClasse            | também chamado UpperCamelCase            |
| snake_case            | minha_variavel         | comum em Python                          |
| SCREAMING_SNAKE_CASE  | VARIAVEL_CONSTANTE     | usado para constantes                    |
| kebab-case            | minha-variavel         | comum em URLs                            |
| Train-Case            | Minha-Variavel         | variação pouco usada                     |
| HungarianNotation     | strNome                | usado antigamente                        |

> **FlatCase** não é uma convenção recomendada.

### Convenções por linguagem:

| Linguagem     | Convenção                            | Link |
|---------------|---------------------------------------|------|
| Java          | Java Code Conventions                 | [Link](https://www.oracle.com/java/technologies/javase/codeconventions-contents.html) |
| JavaScript    | Douglas Crockford Conventions         | [Link](https://www.crockford.com/code.html) |
| Python        | PEP8                                  | [Link](https://peps.python.org/pep-0008/) |
| PHP           | PHP Standards Recommendations (PSR)   | [Link](https://www.php-fig.org/psr/) |

---

## Escopo de Variáveis

O escopo define onde uma variável pode ser acessada.

### Tipos de escopo:

- **Global**: acessível em todo o programa.
- **Local**: acessível apenas dentro do bloco onde foi declarada.

### Exemplo no Portugol Studio:

```portugol
programa
{
	real numero = 10.0 // Variável global
	funcao inicio()
	{
		real numLocal = 12.0 // Variável local
		escreva(numero + "\n")
		escreva(numLocal + "\n")
		escreva(calcula() + "\n")
	}

	funcao real calcula()
	{
		real numCalcula = 5.0 // Variável local
		retorne numCalcula * numero
	}
}
```

> Dica: Evite variáveis globais em excesso. Isso ocupa espaço e dificulta manutenção.

---

## Nota pessoal:

Ao estudar lógica de programação, percebo o quanto é importante dominar a estrutura do raciocínio lógico e das representações visuais, como fluxogramas e diagramas. O uso do Portugol Studio e a prática de exercícios com variáveis, tipos de dados e escopos têm facilitado bastante o entendimento. Além disso, a organização do código e o uso de convenções tornam o desenvolvimento muito mais claro e profissional.

---

## Referência principal:

REIS, Fábio dos. Curso de Lógica de Programação – Bóson Treinamentos. YouTube: [https://www.youtube.com/@bosontreinamentos](https://www.youtube.com/@bosontreinamentos)
