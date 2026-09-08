# Aula 02: Sumário, objetivos, conteúdo, exemplos, exercícios e revisão para prova.

# 📚 Aula 1 — Linguagens Formais e Gramáticas

> Introdução aos principais conceitos de **Linguagens Formais, Alfabetos, Cadeias, Linguagens e Gramáticas**.

---

## 📑 Sumário

* [🎯 Objetivos da Aula](#-objetivos-da-aula)
* [1. Operadores Lógicos](#1-operadores-lógicos)
* [2. Palavra Vazia — ε](#2-palavra-vazia--)
* [3. Prefixos e Sufixos](#3-prefixos-e-sufixos)
* [4. Alfabeto — Σ](#4-alfabeto--)
* [5. Σ* — Todas as Cadeias Possíveis](#5---todas-as-cadeias-possíveis)
* [6. Linguagem Formal — L](#6-linguagem-formal--l)
* [7. Gramática Formal](#7-gramática-formal)
* [8. Regras de Produção](#8-regras-de-produção)
* [9. Como Ler →](#9-como-ler-)
* [10. Derivação de Palavras](#10-derivação-de-palavras)
* [11. Linguagem Gerada](#11-linguagem-gerada)
* [12. Atividades Práticas](#12-atividades-práticas)
* [13. Resumo para Prova](#13-resumo-para-prova)
* [14. Mapa Mental](#14-mapa-mental)

---

# 🎯 Objetivos da Aula

Ao final desta aula, devemos ser capazes de:

* Entender o conceito de **alfabeto**;
* Identificar **cadeias/palavras**;
* Compreender a **palavra vazia `ε`**;
* Identificar **prefixos e sufixos**;
* Entender o conceito de **linguagem formal**;
* Interpretar a notação **`L ⊆ Σ*`**;
* Compreender o funcionamento de uma **gramática formal**;
* Interpretar **regras de produção**;
* Gerar palavras a partir de uma gramática.

---

# 1. Operadores Lógicos

Os principais operadores estudados são:

| Símbolo | Nome       | Leitura               |
| :-----: | ---------- | --------------------- |
|   `¬`   | Negação    | não                   |
|   `∧`   | E          | e                     |
|   `∨`   | OU         | ou                    |
|   `→`   | Implicação | implica / se... então |

### Exemplo

Considere:

```text
p = "Está chovendo."
q = "Eu levo um guarda-chuva."
```

### Negação — `¬`

```text
¬p
```

Lê-se:

> Não está chovendo.

---

### E — `∧`

```text
p ∧ q
```

Lê-se:

> Está chovendo **e** eu levo um guarda-chuva.

---

### OU — `∨`

```text
p ∨ q
```

Lê-se:

> Está chovendo **ou** eu levo um guarda-chuva.

---

### Implicação — `→`

```text
p → q
```

Lê-se:

> Se está chovendo, então eu levo um guarda-chuva.

> **⚠️ Atenção:** o símbolo `→` possui significados diferentes dependendo do contexto. Em lógica, significa **implicação**. Em gramáticas, normalmente significa **produção/geração**.

---

# 2. Palavra Vazia — `ε`

A palavra vazia é representada por:

```text
ε
```

Lê-se:

> **Épsilon**

Ela representa uma cadeia que **não possui nenhum símbolo**.

Seu tamanho é:

```text
|ε| = 0
```

Ou seja:

> O comprimento da cadeia vazia é zero.

### Exemplo

A cadeia:

```text
abc
```

possui 3 símbolos:

```text
|abc| = 3
```

Já:

```text
ε
```

possui 0 símbolos:

```text
|ε| = 0
```

### ⚠️ Importante

`ε` **não é um espaço em branco**.

`ε` significa:

> **Não existe nenhum símbolo na cadeia.**

---

# 3. Prefixos e Sufixos

Considere a palavra:

```text
ab
```

## Prefixos

Um prefixo é uma parte da palavra que começa **no início**.

Podemos obter:

```text
ε
a
ab
```

Portanto:

```text
Prefixos(ab) = {ε, a, ab}
```

### 🧠 Dica

> **Prefixo → começa no começo.**

---

## Sufixos

Um sufixo é uma parte da palavra que termina **no final**.

Podemos obter:

```text
ε
b
ab
```

Portanto:

```text
Sufixos(ab) = {ε, b, ab}
```

### 🧠 Dica

> **Sufixo → termina no final.**

---

## Resumo

| Palavra | Prefixos       | Sufixos        |
| ------- | -------------- | -------------- |
| `ab`    | `ε`, `a`, `ab` | `ε`, `b`, `ab` |

O `ε` é considerado tanto **prefixo** quanto **sufixo**.

---

# 4. Alfabeto — `Σ`

Um **alfabeto** é um conjunto finito de símbolos.

Ele é representado por:

```text
Σ
```

Lê-se:

> **Sigma**

### Exemplo

```text
Σ = {a, b}
```

Nosso alfabeto possui dois símbolos:

```text
a
b
```

A partir deles podemos criar palavras:

```text
a
b
aa
ab
ba
bb
aaa
aab
aba
...
```

---

# 5. `Σ*` — Todas as Cadeias Possíveis

A notação:

```text
Σ*
```

representa o conjunto de **todas as cadeias finitas que podem ser formadas utilizando os símbolos de `Σ`**, incluindo `ε`.

Se:

```text
Σ = {a, b}
```

então:

```text
Σ* = {ε, a, b, aa, ab, ba, bb, aaa, ...}
```

## Existe um limite?

**Não existe limite máximo para o tamanho das palavras.**

Podemos formar:

```text
ε
a
aa
aaa
aaaa
aaaaa
...
```

A quantidade de palavras cresce conforme o tamanho aumenta.

Para um alfabeto com 2 símbolos:

```text
Quantidade de cadeias de tamanho n = 2ⁿ
```

| Tamanho | Quantidade |
| :-----: | :--------: |
|    0    |      1     |
|    1    |      2     |
|    2    |      4     |
|    3    |      8     |
|    4    |     16     |
|    5    |     32     |
|   ...   |     ...    |

### 📌 Conclusão

> `Σ*` é infinito, mas cada cadeia individual possui tamanho finito.

---

# 6. Linguagem Formal — `L`

Uma **linguagem formal** é um conjunto de palavras construídas a partir de um alfabeto.

Sua definição é:

```text
L ⊆ Σ*
```

Lê-se:

> **L é um subconjunto de Sigma estrela.**

### Entendendo cada elemento

```text
Σ
```

É o alfabeto.

```text
Σ*
```

É o conjunto de todas as palavras possíveis.

```text
L
```

É um conjunto de palavras escolhidas de `Σ*`.

---

## Exemplo

Considere:

```text
Σ = {a, b}
```

Podemos definir:

```text
L = {a, ab, abb, abbb}
```

Como todas essas palavras podem ser formadas usando `a` e `b`:

```text
L ⊆ Σ*
```

---

## Linguagem finita

```text
L = {ε, a, ab}
```

Possui uma quantidade limitada de palavras.

---

## Linguagem infinita

```text
L = {a, aa, aaa, aaaa, ...}
```

Possui infinitas palavras.

---

# 7. Gramática Formal

Uma gramática formal fornece **regras para gerar palavras**.

Considere:

```text
G = ({S}, {a}, {S → aS | ε}, S)
```

Uma gramática normalmente pode ser representada como:

```text
G = (N, Σ, P, S)
```

Onde:

| Elemento | Significado     |
| -------- | --------------- |
| `N`      | Não terminais   |
| `Σ`      | Terminais       |
| `P`      | Produções       |
| `S`      | Símbolo inicial |

No nosso exemplo:

```text
G = ({S}, {a}, {S → aS | ε}, S)
```

Temos:

### Não terminal

```text
{S}
```

### Terminal

```text
{a}
```

### Produções

```text
S → aS | ε
```

### Símbolo inicial

```text
S
```

---

# 8. Regras de Produção

A regra:

```text
S → aS | ε
```

possui duas possibilidades:

```text
S → aS
```

**OU**

```text
S → ε
```

O símbolo:

```text
|
```

significa:

> **OU**

Portanto:

> `S` pode produzir `aS` ou `ε`.

---

# 9. Como Ler `→`

O símbolo:

```text
→
```

pode ser lido de maneiras diferentes.

## Em gramáticas

Pode significar:

* produz;
* gera;
* deriva em.

Exemplo:

```text
S → aS
```

Lê-se:

> **S produz aS.**

---

## Em lógica

Pode significar:

* implica;
* se... então.

Exemplo:

```text
p → q
```

Lê-se:

> **Se p, então q.**

ou:

> **p implica q.**

---

# 10. Derivação de Palavras

Considere:

```text
G = ({S}, {a}, {S → aS | ε}, S)
```

Começamos sempre pelo símbolo inicial:

```text
S
```

---

## Gerando `ε`

Escolhemos:

```text
S → ε
```

Resultado:

```text
ε
```

---

## Gerando `a`

Primeiro:

```text
S → aS
```

Depois:

```text
S → ε
```

Logo:

```text
S → aS → aε → a
```

Resultado:

```text
a
```

---

## Gerando `aa`

Aplicamos `S → aS` duas vezes:

```text
S → aS
  → aaS
  → aaε
  → aa
```

Resultado:

```text
aa
```

---

## Gerando `aaa`

Aplicamos `S → aS` três vezes:

```text
S → aS
  → aaS
  → aaaS
  → aaaε
  → aaa
```

Resultado:

```text
aaa
```

---

# 11. Linguagem Gerada

A gramática:

```text
G = ({S}, {a}, {S → aS | ε}, S)
```

gera:

```text
ε
a
aa
aaa
aaaa
aaaaa
...
```

Logo:

```text
L(G) = {ε, a, aa, aaa, aaaa, ...}
```

Também podemos representar como:

```text
L(G) = {aⁿ | n ≥ 0}
```

Isso significa:

> A linguagem contém qualquer quantidade de `a`, incluindo **zero `a`**.

O caso de zero `a` é:

```text
ε
```

---

# 12. Atividades Práticas

## 📝 Atividade 1 — Prefixos e Sufixos

Considere a palavra:

```text
ab
```

### Pergunta

Liste os prefixos e sufixos.

### Gabarito

**Prefixos:**

```text
{ε, a, ab}
```

**Sufixos:**

```text
{ε, b, ab}
```

---

## 📝 Atividade 2 — Gramática

Considere:

```text
G = ({S}, {a}, {S → aS | ε}, S)
```

### Pergunta

Liste 3 palavras geradas.

### Gabarito

Uma resposta possível:

```text
ε
a
aa
```

Outras possibilidades:

```text
aaa
aaaa
aaaaa
...
```

---

# 13. Resumo para Prova

### 🔹 Alfabeto

```text
Σ = conjunto de símbolos
```

Exemplo:

```text
Σ = {a, b}
```

---

### 🔹 Cadeia

Uma sequência de símbolos pertencentes ao alfabeto.

Exemplo:

```text
ab
```

---

### 🔹 Palavra vazia

```text
ε
```

Possui zero símbolos:

```text
|ε| = 0
```

---

### 🔹 `Σ*`

Todas as cadeias finitas possíveis sobre `Σ`, incluindo `ε`.

```text
Σ* = {ε, a, b, aa, ab, ba, bb, ...}
```

---

### 🔹 Linguagem

Um conjunto de cadeias:

```text
L ⊆ Σ*
```

---

### 🔹 Prefixo

Começa no início da palavra.

Para `ab`:

```text
{ε, a, ab}
```

---

### 🔹 Sufixo

Termina no final da palavra.

Para `ab`:

```text
{ε, b, ab}
```

---

### 🔹 Gramática

Define regras para gerar palavras.

Exemplo:

```text
S → aS | ε
```

---

### 🔹 `→`

Em gramáticas:

> **produz / gera**

Em lógica:

> **implica / se... então**

---

### 🔹 `|`

Nas regras de produção:

> **OU**

Exemplo:

```text
S → aS | ε
```

Significa:

> S produz `aS` **ou** `ε`.

---

# 14. 🧠 Mapa Mental

```text
                    LINGUAGENS FORMAIS
                           │
          ┌────────────────┼────────────────┐
          │                │                │
          ▼                ▼                ▼
      ALFABETO           CADEIA          LINGUAGEM
          │                │                │
          │                │                └── L ⊆ Σ*
          │                │
          │                └── ε = cadeia vazia
          │
          └── Σ
               │
               └── Σ* = todas as cadeias
                           │
                           ▼
                       GRAMÁTICA
                           │
                           ▼
                    Regras de produção
                           │
                           ▼
                      S → aS | ε
                           │
                           ▼
                ε, a, aa, aaa, ...
```

---

# 📌 Checklist da Aula 1

Antes de avançar para a próxima aula, verifique se você consegue explicar:

* [x] O que é um **alfabeto `Σ`**;

    > Um alfabeto é um conjunto finito e não vazio de símbolos. Esses símbolos são as "peças básicas" que vamos usar para montar palavras. Por exemplo, Σ={a,b,c} ou Σ={0,1}. É importante notar: o alfabeto contém apenas símbolos individuais, nunca sequências de símbolos.

* [x] O que é uma **cadeia**;

    > Uma cadeia (também chamada de palavra ou sentença) é uma sequência finita de símbolos retirados de um alfabeto. Por exemplo, se Σ={0,1}, então 0101 é uma cadeia formada por símbolos de Σ. A ordem dos símbolos importa, e os símbolos podem se repetir.

* [x] O que significa **`ε`**;

    > ε representa a palavra vazia — ou seja, a cadeia que não possui símbolo algum. Ela não é um símbolo do alfabeto; é um conceito especial que representa "a ausência total de símbolos" formando uma palavra válida.

* [x] Por que **`|ε| = 0`**;

    > A notação |w| representa o comprimento de uma palavra w, ou seja, quantos símbolos ela tem. Como ε é a palavra sem nenhum símbolo, seu comprimento é zero: |ε|=0. Compare, por exemplo, com |abc|=3, porque abc tem três símbolos.

* [x] O que é um **prefixo**;

    > Um prefixo de uma palavra w é qualquer sequência inicial contígua de símbolos de w, começando do início dela. Por exemplo, para a palavra abc, os prefixos são: ε, a, ab, abc. Repare que a própria palavra e a palavra vazia também contam como prefixos (às vezes chamados de prefixo impróprio e prefixo trivial).

* [x] O que é um **sufixo**;

    > De forma parecida, um sufixo de uma palavra w é qualquer sequência final contígua de símbolos de w, terminando no fim dela. Para abc, os sufixos são: ε, c, bc, abc.

* [x] O que significa **`Σ*`**;

    > Σ* (lê-se "estrela de Sigma" ou "fecho de Kleene de Sigma") representa **o conjunto de todas as palavras possíveis** que podem ser formadas usando símbolos do alfabeto Σ — incluindo a palavra vazia ε. Ou seja, Σ* engloba desde a palavra vazia até palavras arbitrariamente longas, com qualquer combinação e repetição de símbolos de Σ.

* [x] Se `Σ*` possui limite de tamanho;

    > Não. Σ* é um conjunto infinito, mesmo que o alfabeto Σ seja finito. Isso acontece porque não existe limite para o comprimento de uma palavra — sempre é possível formar uma palavra mais longa adicionando mais símbolos. Por exemplo, com Σ={a}, já temos infinitas palavras possíveis: ε, a, aa, aaa, aaaa, … e assim por diante, sem fim.

* [x] O que é uma **linguagem formal `L`**;

    > Uma linguagem formal L é simplesmente um conjunto de palavras formadas a partir de um alfabeto — ou seja, um subconjunto de Σ*. Uma linguagem pode ser definida de duas formas: por enumeração (listando explicitamente as palavras, como L={0,01,011}) ou por compreensão/padrão (descrevendo uma regra que as palavras devem satisfazer, como L={a^n ∣ n≥1}).

* [x] O que significa **`L ⊆ Σ*`**;

    > Essa notação diz que L é um subconjunto de Σ*, ou seja, toda palavra que pertence a L obrigatoriamente também pertence a Σ* (foi formada com símbolos válidos do alfabeto). Isso faz sentido: uma linguagem nunca pode conter uma "palavra" com símbolos que não existem no alfabeto — ela é sempre um recorte, uma seleção, dentro do conjunto de todas as palavras possíveis Σ*.

* [x] O que é uma **gramática formal**;

    > Uma gramática formal é um mecanismo com regras que permite gerar (produzir) as palavras de uma linguagem. Formalmente, é definida como uma tupla G=(V,Σ,P,S), onde:
    > * V = conjunto de variáveis (não-terminais)
    > * Σ = conjunto de terminais
    > * P = conjunto de regras de produção
    > * S = símbolo inicial (de onde toda derivação começa)
    > 
    > A ideia central é: começando do símbolo inicial S, aplicamos as regras de P repetidamente, substituindo variáveis, até sobrar só símbolos terminais — e aí temos uma palavra da linguagem.

* [x] O que são **terminais e não terminais**;

    > * **Terminais:** são os símbolos que fazem parte do alfabeto Σ — eles aparecem na palavra final e não podem mais ser substituídos. São o "produto acabado".
    > * **Não-terminais** (ou variáveis, conjunto V): são símbolos auxiliares (geralmente representados por letras maiúsculas, como S, A, B) que ainda podem ser reescritos por outras sequências de símbolos, seguindo as regras de produção. Eles não aparecem na palavra final — servem só como "andaimes" durante a construção da palavra.

* [x] O que é uma **regra de produção**;

    > Uma regra de produção é uma instrução no formato α→β, que diz: "onde eu encontrar α, posso substituir por β". Na prática, na maioria dos casos que vimos, o lado esquerdo é uma única variável (como S), e o lado direito é uma sequência de terminais e/ou variáveis (como aS ou b). É através dessas regras que a gramática "constrói" as palavras da linguagem, passo a passo.

* [x] Como ler **`S → aS | ε`**;

    > Essa notação é uma forma compacta de escrever duas regras de produção separadas, usando a barra | (que significa "ou"). Ela equivale a escrever:
    > * S → aS
    > * S → ε
    > 
    > Lendo em português: "S pode ser substituído por aS, ou S pode ser substituído pela palavra vazia". Isso significa que, a cada passo da derivação, eu posso escolher qual das duas regras aplicar. Como S→ε é a única forma de encerrar a derivação (fazendo o S "sumir"), e S→aS adiciona um a cada vez que é aplicada, essa gramática gera a linguagem L={a^n ∣ n≥0} — ou seja, qualquer quantidade de as, incluindo zero (que resultaria na própria palavra vazia).

* [x] Como gerar palavras usando uma gramática.

    > O processo se chama derivação. Ele funciona assim:
    > 1. Começamos sempre pelo símbolo inicial S.
    > 2. A cada passo, escolhemos uma variável presente na sentença atual e aplicamos alguma regra de produção que tenha essa variável do lado esquerdo, substituindo-a pelo lado direito da regra.
    > 3. Repetimos esse processo quantas vezes forem necessárias.
    > 4. A derivação termina quando a sentença não contém mais nenhuma variável — só símbolos terminais. Nesse momento, temos uma palavra da linguagem gerada pela gramática.
    > 
    > Usamos o símbolo ⇒ para indicar "deriva em um passo", e ⇒* para indicar "deriva em zero ou mais passos". Por exemplo:
    > S ⇒ aS ⇒ aaS ⇒ aab


---

## 🚀 Conceito-chave

> **Um alfabeto fornece os símbolos.
> As cadeias são formadas com esses símbolos.
> `Σ*` reúne todas as cadeias possíveis.
> Uma linguagem seleciona algumas dessas cadeias.
> Uma gramática define regras para gerar as cadeias da linguagem.**

---

### 📚 Aula 1 concluída

**Próximo passo:** praticar a identificação de alfabetos, cadeias, prefixos, sufixos e a derivação de palavras por meio de gramáticas formais.

