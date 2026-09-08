# Exercícios Comentados — Aulas 01 e 02

## Linguagens Formais, Alfabeto, Linguagens e Gramáticas

**Disciplina:** Linguagens Formais e Autômatos
**Objetivo:** revisar os conceitos fundamentais de **alfabeto, palavras, linguagens e gramáticas**, desenvolvendo também a capacidade de interpretar e ler a notação matemática.

> **Orientação ao estudante:** primeiro leia e compreenda o exercício comentado. Em seguida, tente resolver o exercício proposto sem consultar o gabarito. Ao final do material, confira suas respostas.

---

# 1. Alfabeto

## Exercício comentado

Considere o conjunto:

$$
\Sigma = {0,1}
$$

**Pergunta:** o que significa esse conjunto?

### Resolução passo a passo

O símbolo $\Sigma$ é utilizado para representar um **alfabeto**.

Um alfabeto é um conjunto finito de símbolos que podem ser utilizados para construir palavras.

Neste caso:

$$
\Sigma = {0,1}
$$

O alfabeto possui dois símbolos:

```text
0
1
```

### Como se lê?

Podemos ler:

> **"Sigma é o conjunto formado pelos símbolos zero e um."**

Ou:

> **"O alfabeto Sigma é formado pelos símbolos 0 e 1."**

### Atenção

Os elementos `0` e `1` são **símbolos individuais**.

Não devemos confundir:

```text
0
```

com:

```text
01
```

O primeiro é um símbolo.

O segundo é uma sequência de símbolos, ou seja, uma **palavra**.

---

## Exercício para o estudante

Considere:

$$
\Sigma = {a,b,c}
$$

Responda:

1. Quantos símbolos existem no alfabeto?
2. Quais são os símbolos?
3. O símbolo `a` pertence ao alfabeto?
4. O símbolo `d` pertence ao alfabeto?
5. Escreva uma palavra formada por símbolos desse alfabeto.

<br>

### 📝 Minha Resolução:

1. Quantos símbolos existem no alfabeto?
Existem 3 símbolos.

2. Quais são os símbolos?
Os símbolos são: a, b, c.

3. O símbolo a pertence ao alfabeto?
Sim. Como Σ={a,b,c}, e a está listado dentro desse conjunto, então a∈Σ.

4. O símbolo d pertence ao alfabeto?
Não. O símbolo d não aparece no conjunto Σ={a,b,c}, então d∉Σ.

5. Escreva uma palavra formada por símbolos desse alfabeto.
Por exemplo: abac. Toda palavra é simplesmente uma sequência (finita) de símbolos retirados do alfabeto, podendo repetir símbolos e podendo ter qualquer tamanho.


---

# 2. Palavras sobre um alfabeto

## Exercício comentado

Considere:

$$
\Sigma = {a,b}
$$

Verifique quais das sequências abaixo são palavras construídas sobre esse alfabeto:

```text
abba
abc
baab
d
```

### Resolução

Uma **palavra** é uma sequência finita de símbolos pertencentes ao alfabeto.

Nosso alfabeto é:

$$
\Sigma = {a,b}
$$

### Palavra `abba`

Observe:

```text
a b b a
```

Todos os símbolos pertencem ao alfabeto.

Portanto:

$$
abba \in \Sigma^*
$$

### Como se lê?

> **"abba pertence ao conjunto de todas as palavras construídas sobre Sigma."**

### Palavra `abc`

Observe:

```text
a b c
```

O símbolo `c` pertence ao alfabeto?

Não.

Temos:

$$
c \notin \Sigma
$$

Portanto:

$$
abc \notin \Sigma^*
$$

### Palavra `baab`

Observe:

```text
b a a b
```

Todos os símbolos pertencem a:

$$
\Sigma = {a,b}
$$

Logo:

$$
baab \in \Sigma^*
$$

### Palavra `d`

O símbolo `d` não pertence ao alfabeto.

Portanto:

$$
d \notin \Sigma^*
$$

---

## Exercício para o estudante

Considere:

$$
\Sigma = {0,1}
$$

Classifique cada sequência como **palavra válida** ou **não válida**:

| Sequência | Válida? | Justificativa |
| --------- | ------- | ------------- |
| `0101`    |         |               |
| `00110`   |         |               |
| `012`     |         |               |
| `111`     |         |               |
| `10a`     |         |               |

<br>

### 📝 Minha Resolução:

Lembrando: uma palavra é válida sobre Σ={0,1} se todos os símbolos que a compõem pertencem a Σ.

1. 0101 → Válida. Todos os símbolos (0 e 1) pertencem a Σ.
2. 00110 → Válida. Mesma justificativa: só usa 0 e 1.
3. 012 → Não válida. O símbolo 2 não pertence a Σ={0,1}.
4. 111 → Válida. Usa apenas o símbolo 1, que pertence a Σ.
5. 10a → Não válida. O símbolo a não pertence a Σ={0,1}.


---

# 3. Pertinência de símbolos e palavras

## Exercício comentado

Considere:

$$
\Sigma = {a,b,c}
$$

Determine se:

$$
a \in \Sigma
$$

e se:

$$
ab \in \Sigma
$$

### Resolução

Primeiro analisamos:

$$
a \in \Sigma
$$

O símbolo `a` está dentro do conjunto?

Sim.

Portanto:

$$
\boxed{a \in \Sigma}
$$

Agora observe:

```text
ab
```

`ab` possui dois símbolos:

```text
a b
```

Portanto, `ab` é uma **palavra**, e não um símbolo individual do alfabeto.

Assim:

$$
ab \notin \Sigma
$$

Porém:

$$
ab \in \Sigma^*
$$

### Como se lê?

$$
a \in \Sigma
$$

Lemos:

> **"a pertence a Sigma."**

Já:

$$
ab \in \Sigma^*
$$

Lemos:

> **"ab pertence ao conjunto de todas as palavras sobre Sigma."**

### Conceito importante

Não confunda:

$$
a \in \Sigma
$$

com:

$$
ab \in \Sigma
$$

O primeiro representa um **símbolo**.

O segundo representa uma **palavra**.

---

## Exercício para o estudante

Considere:

$$
\Sigma = {0,1}
$$

Determine se as afirmações são **verdadeiras ou falsas**:

1. $0 \in \Sigma$
2. $1 \in \Sigma$
3. $01 \in \Sigma$
4. $01 \in \Sigma^*$
5. $2 \in \Sigma$
6. $101 \in \Sigma^*$

Justifique cada resposta.

<br>

### 📝 Minha Resolução:

Aqui é importante ter cuidado com uma distinção importante: Σ é o conjunto de símbolos (letras individuais), enquanto Σ* é o conjunto de todas as palavras possíveis formadas com esses símbolos (incluindo a palavra vazia ε).

1. 0∈Σ → Verdadeiro. 0 é um dos símbolos do alfabeto.
2. 1∈Σ → Verdadeiro. 1 é um dos símbolos do alfabeto.
3. 01∈Σ → Falso. 01 é uma palavra (sequência de dois símbolos), não um único símbolo. Σ contém apenas símbolos isolados, então 01 não pode pertencer a Σ.
4. 01∈Σ* → Verdadeiro. Σ* é o conjunto de todas as palavras formadas com os símbolos de Σ, e 01 é uma sequência válida formada só por 0 e 1.
5. 2∈Σ → Falso. O símbolo 2 não faz parte do alfabeto {0,1}.
6. 101∈Σ* → Verdadeiro. 101 é formada só por símbolos de Σ, logo é uma palavra válida pertencente a Σ*.


---

# 4. Linguagem

## Exercício comentado

Considere:

$$
\Sigma = {a,b}
$$

e a linguagem:

$$
L = {a,ab,abb}
$$

### O que é $L$?

Uma **linguagem** é um conjunto de palavras.

Neste exemplo:

```text
a
ab
abb
```

são as palavras que pertencem à linguagem.

### Verificando `ab`

Queremos saber:

$$
ab \in L?
$$

Observe a linguagem:

$$
L = {a,ab,abb}
$$

A palavra `ab` aparece no conjunto.

Portanto:

$$
\boxed{ab \in L}
$$

### Verificando `ba`

Agora:

$$
ba \in L?
$$

A palavra `ba` não aparece no conjunto.

Portanto:

$$
\boxed{ba \notin L}
$$

### Como se lê?

$$
ab \in L
$$

Lemos:

> **"ab pertence à linguagem L."**

Já:

$$
ba \notin L
$$

Lemos:

> **"ba não pertence à linguagem L."**

---

## Exercício para o estudante

Considere:

$$
L = {0,01,011,0111}
$$

Determine se cada palavra pertence à linguagem:

1. $0 \in L$
2. $01 \in L$
3. $0111 \in L$
4. $10 \in L$
5. $111 \in L$
6. $011 \in L$

<br>

### 📝 Minha Resolução:

Aqui L={0,01,011,0111} é uma linguagem definida explicitamente, ou seja, por enumeração das palavras que a compõem. Uma palavra pertence a L se, e somente se, ela estiver literalmente listada dentro do conjunto.

1. 0∈L → Verdadeiro. 0 está listado em L.
2. 01∈L → Verdadeiro. 01 está listado em L.
3. 0111∈L → Verdadeiro. 0111 está listado em L.
4. 10∈L → Falso. 10 não aparece em L (repare que a ordem dos símbolos importa: 10 é diferente de 01).
5. 111∈L → Falso. 111 não está entre as palavras listadas em L.
6. 011∈L → Verdadeiro. 011 está listado em L.


---

# 5. Descrevendo uma linguagem por padrão

## Exercício comentado

Considere:

$$
L = {a,aa,aaa,aaaa,\ldots}
$$

Qual é o padrão dessa linguagem?

### Resolução

Observe as palavras:

```text
a
aa
aaa
aaaa
aaaaa
...
```

Todas possuem apenas o símbolo `a`.

A quantidade de `a` pode aumentar indefinidamente.

Podemos representar essa linguagem por:

$$
L = {a^n \mid n \geq 1}
$$

### Como se lê?

A expressão:

$$
a^n
$$

pode ser lida:

> **"a elevado a n"**

Nesse contexto, significa:

> **"n ocorrências do símbolo a."**

Por exemplo:

$$
a^1 = a
$$

$$
a^2 = aa
$$

$$
a^3 = aaa
$$

$$
a^4 = aaaa
$$

O símbolo:

$$
\mid
$$

pode ser lido como:

> **"tal que"**

Assim:

$$
{a^n \mid n \geq 1}
$$

pode ser lido:

> **"O conjunto das palavras formadas por n ocorrências de a, tal que n é maior ou igual a 1."**

---

## Exercício para o estudante

Considere:

$$
L = {b^n \mid n \geq 1}
$$

1. Escreva as cinco primeiras palavras.
2. Explique o significado de $b^n$.
3. A palavra `bbbbbb` pertence à linguagem?
4. A palavra vazia ($\varepsilon$) pertence à linguagem?

<br>

### 📝 Minha Resolução:

Aqui L={b^n ∣ n≥1} é uma linguagem definida por compreensão, isto é, por uma regra/padrão em vez de uma lista.

1. Escreva as cinco primeiras palavras.
Como n≥1, começamos em n=1:
n=1: b
n=2: bb
n=3: bbb
n=4: bbbb
n=5: bbbbb

2. Explique o significado de b^n.
b^n significa o símbolo b repetido n vezes seguidas. Por exemplo, b^3 = bbb (três bs em sequência). Então a notação b^n é só uma forma compacta de descrever uma palavra formada por várias repetições do mesmo símbolo.

3. A palavra bbbbbb pertence à linguagem?
Sim. bbbbbb tem 6 símbolos b, ou seja, é b^6. Como 6≥1, essa palavra satisfaz a condição da linguagem, então bbbbbb ∈ L.

4. A palavra vazia (ε) pertence à linguagem?
Não. A palavra vazia corresponde a n=0 (zero repetições de b), mas a definição exige n≥1. Como 0 não satisfaz n≥1, temos ε∉L.


---

# 6. Linguagem vazia e palavra vazia

## Exercício comentado

Explique a diferença entre:

$$
\emptyset
$$

e:

$$
\varepsilon
$$

### Resolução

Esses dois símbolos possuem significados diferentes.

## Conjunto vazio

$$
\emptyset
$$

representa um conjunto que **não possui elementos**.

Uma linguagem vazia pode ser representada por:

$$
L = \emptyset
$$

Isso significa:

> **A linguagem não possui nenhuma palavra.**

## Palavra vazia

$$
\varepsilon
$$

representa uma palavra que possui **zero símbolos**.

Uma linguagem que contém somente a palavra vazia é:

$$
L = {\varepsilon}
$$

Essa linguagem possui **uma palavra**.

Essa palavra possui comprimento zero.

Portanto:

$$
\emptyset \neq {\varepsilon}
$$

### Como se lê?

$$
\emptyset
$$

Lemos:

> **"Conjunto vazio."**

$$
\varepsilon
$$

Lemos:

> **"Épsilon"** ou **"palavra vazia"**.

---

## Exercício para o estudante

Explique, com suas próprias palavras, a diferença entre:

### A

$$
L=\emptyset
$$

### B

$$
L={\varepsilon}
$$

Depois responda:

1. Qual delas possui uma palavra?
2. Qual delas não possui nenhuma palavra?
3. Qual é o comprimento da palavra $\varepsilon$?

<br>

### 📝 Minha Resolução:

A) L=∅ — Essa é a linguagem vazia. Ela é um conjunto que não contém absolutamente nenhuma palavra, nem mesmo a palavra vazia. É como uma caixa completamente vazia: não tem nada dentro, nem um único elemento.

B) L={ε} — Essa é uma linguagem que contém exatamente uma palavra, e essa palavra é a palavra vazia (ε). É como uma caixa que não está vazia — ela tem um elemento dentro —, mas esse elemento é a "palavra sem símbolos".

A diferença central: ∅ não tem elemento nenhum (nem ε), enquanto {ε} tem um elemento, que por acaso é a palavra vazia.

1. Qual delas possui uma palavra?
L={ε}, pois contém a palavra ε como elemento.

2. Qual delas não possui nenhuma palavra?
L=∅, pois é o conjunto vazio, sem nenhum elemento.

3. Qual é o comprimento da palavra ε?
O comprimento de ε é 0 (zero símbolos). Por definição, ε é a palavra sem nenhum símbolo.


---

# 7. Estrutura de uma gramática

## Exercício comentado

Considere:

$$
G=(V,T,P,S)
$$

com:

$$
V={S}
$$

$$
T={a,b}
$$

e:

$$
P={S\rightarrow aS,\ S\rightarrow b}
$$

### O que significa cada componente?

Uma gramática formal é representada por:

$$
G=(V,T,P,S)
$$

### $V$ — Variáveis ou não terminais

Temos:

$$
V={S}
$$

O símbolo `S` será utilizado durante a derivação.

### $T$ — Terminais

Temos:

$$
T={a,b}
$$

Os terminais são os símbolos que podem aparecer na palavra final.

### $P$ — Produções

Temos:

$$
P={S\rightarrow aS,\ S\rightarrow b}
$$

São as regras utilizadas para transformar ou substituir os não terminais.

### $S$ — Símbolo inicial

O símbolo inicial é:

$$
S
$$

É por ele que a derivação começa.

### Como se lê?

$$
G=(V,T,P,S)
$$

Pode ser lido:

> **"G é uma gramática formada pelo conjunto de variáveis V, conjunto de terminais T, conjunto de produções P e símbolo inicial S."**

---

## Exercício para o estudante

Considere:

$$
G= ({S,A},{0,1},P,S)
$$

com:

$$
P={S\rightarrow0A,\ A\rightarrow1}
$$

Identifique:

1. O conjunto de variáveis.
2. O conjunto de terminais.
3. O conjunto de produções.
4. O símbolo inicial.
5. Qual palavra pode ser gerada por essa gramática?

<br>

### 📝 Minha Resolução:

Aqui temos G=({S,A},{0,1},P,S) com P={S→0A, A→1}.

1. O conjunto de variáveis.
V={S,A}. São os símbolos "auxiliares" que ainda podem ser reescritos/substituídos durante a derivação.

2. O conjunto de terminais.
Σ={0,1}. São os símbolos que efetivamente aparecem na palavra final — não podem mais ser substituídos.

3. O conjunto de produções.
P={S→0A, A→1}. São as regras que dizem como cada variável pode ser reescrita.

4. O símbolo inicial.
S. É de onde toda derivação começa.

5. Qual palavra pode ser gerada por essa gramática?
Vamos derivar passo a passo:
S ⇒ 0A ⇒ 01
A palavra gerada é 01.


---

# 8. Como ler e aplicar uma produção

## Exercício comentado

Considere a produção:

$$
S\rightarrow aS
$$

### Como se lê?

Podemos ler:

> **"S produz aS."**

Também podemos dizer:

> **"S pode ser substituído por aS."**

O símbolo:

$$
\rightarrow
$$

pode ser lido como:

> **"produz"**

ou:

> **"é substituído por"**.

### Aplicando a regra

Começamos com:

$$
S
$$

Aplicamos a produção:

$$
S\Rightarrow aS
$$

Podemos aplicar novamente:

$$
aS\Rightarrow aaS
$$

E novamente:

$$
aaS\Rightarrow aaaS
$$

Portanto:

$$
S\Rightarrow aS\Rightarrow aaS\Rightarrow aaaS
$$

### Atenção

A derivação ainda **não terminou**.

Por quê?

Porque ainda existe um não terminal:

$$
S
$$

Uma derivação termina quando não existem mais não terminais.

---

## Exercício para o estudante

Considere:

$$
S\rightarrow0S
$$

Começando com $S$:

1. Aplique a regra uma vez.
2. Aplique a regra duas vezes.
3. Aplique a regra três vezes.
4. Escreva a sequência completa de derivação.

<br>

### 📝 Minha Resolução:

Regra: S→0S.

1. Aplique a regra uma vez.
S ⇒ 0S

2. Aplique a regra duas vezes.
S ⇒ 0S ⇒ 00S

3. Aplique a regra três vezes.
S ⇒ 0S ⇒ 00S ⇒ 000S

4. Escreva a sequência completa de derivação.
S ⇒ 0S ⇒ 00S ⇒ 000S ⇒ …
Repare que, como só existe a regra S→0S, essa gramática ficaria gerando 0s indefinidamente. Para gerar uma palavra terminada, precisaríamos de outra regra, como S→ε ou S→0, para "fechar" a derivação.


---

# 9. Derivação completa de uma palavra

## Exercício comentado

Considere a gramática:

$$
G:
\begin{cases}
S\rightarrow aS\
S\rightarrow b
\end{cases}
$$

Queremos gerar:

```text
aab
```

### Passo 1 — Começar pelo símbolo inicial

$$
S
$$

### Passo 2 — Produzir o primeiro `a`

Utilizamos:

$$
S\rightarrow aS
$$

Então:

$$
S\Rightarrow aS
$$

### Passo 3 — Produzir o segundo `a`

Ainda temos:

$$
S
$$

Aplicamos novamente:

$$
S\rightarrow aS
$$

Logo:

$$
aS\Rightarrow aaS
$$

### Passo 4 — Produzir `b`

Agora temos:

```text
aaS
```

Queremos terminar com `b`.

Utilizamos:

$$
S\rightarrow b
$$

Então:

$$
aaS\Rightarrow aab
$$

### Derivação completa

$$
\boxed{S\Rightarrow aS\Rightarrow aaS\Rightarrow aab}
$$

### Como se lê?

Podemos ler:

> **"S deriva aS."**

> **"aS deriva aaS."**

> **"aaS deriva aab."**

O símbolo:

$$
\Rightarrow
$$

representa uma **derivação**, ou seja, uma aplicação de uma regra de produção.

### Quando termina?

A palavra final é:

```text
aab
```

Não existe mais `S`.

Portanto, a derivação terminou.

---

## Exercício para o estudante

Utilizando:

$$
G:
\begin{cases}
S\rightarrow aS\
S\rightarrow b
\end{cases}
$$

gere:

$$
aaab
$$

**Escreva todos os passos da derivação.**

<br>

### 📝 Minha Resolução:

Gramática:
S→aS ∣ b
Queremos gerar aaab.

S ⇒ aS ⇒ aaS ⇒ aaaS ⇒ aaab

Contamos quantas vezes usamos cada regra: usamos S→aS três vezes (uma para cada a) e S→b uma vez, no final. Isso bate exatamente com a estrutura da palavra aaab.


---

# 10. Identificando palavras geradas por uma gramática

## Exercício comentado

Considere:

$$
G:
\begin{cases}
S\rightarrow0S\
S\rightarrow1
\end{cases}
$$

Pergunta:

> A palavra `001` pode ser gerada pela gramática?

### Passo 1 — Começamos

$$
S
$$

Queremos gerar:

```text
001
```

O primeiro símbolo é `0`.

Utilizamos:

$$
S\rightarrow0S
$$

Portanto:

$$
S\Rightarrow0S
$$

### Passo 2

Ainda precisamos produzir:

```text
01
```

Aplicamos novamente:

$$
S\rightarrow0S
$$

Então:

$$
0S\Rightarrow00S
$$

### Passo 3

Agora queremos produzir `1`.

Utilizamos:

$$
S\rightarrow1
$$

Logo:

$$
00S\Rightarrow001
$$

### Derivação completa

$$
\boxed{S\Rightarrow0S\Rightarrow00S\Rightarrow001}
$$

Portanto:

$$
\boxed{001\in L(G)}
$$

### Como se lê?

$$
001\in L(G)
$$

Lemos:

> **"001 pertence à linguagem gerada pela gramática G."**

### E a palavra `101`?

Observe a gramática:

$$
S\rightarrow0S
$$

ou:

$$
S\rightarrow1
$$

A regra que produz `1` encerra a derivação.

Portanto, não conseguimos gerar:

```text
101
```

porque depois de produzir `1` não podemos voltar a produzir `0`.

Logo:

$$
\boxed{101\notin L(G)}
$$

---

## Exercício para o estudante

Considere novamente:

$$
G:
\begin{cases}
S\rightarrow0S\
S\rightarrow1
\end{cases}
$$

Determine se cada palavra pode ser gerada:

1. `1`
2. `01`
3. `001`
4. `0001`
5. `101`
6. `1001`

Para as palavras que podem ser geradas, apresente a derivação completa.

<br>

### 📝 Minha Resolução:

Gramática:
S→0S ∣ 1

1. 1
Pode ser gerada.
S ⇒ 1

2. 01
Pode ser gerada. Um 0 seguido de 1.
S ⇒ 0S ⇒ 01

3. 001
Pode ser gerada. Dois 0s seguidos de 1.
S ⇒ 0S ⇒ 00S ⇒ 001

4. 0001
Pode ser gerada. Três 0s seguidos de 1.
S ⇒ 0S ⇒ 00S ⇒ 000S ⇒ 0001

5. 101
Não pode ser gerada. O único jeito de introduzir um 1 é através da regra S→1, e essa regra sempre encerra a derivação.

6. 1001
Não pode ser gerada, pelo mesmo motivo do item anterior.


---

# Gabarito Comentado

## Exercício 1

Considere:

$$
\Sigma={a,b,c}
$$

### Respostas

1. O alfabeto possui **3 símbolos**.
2. Os símbolos são:

$$
a,\ b,\ c
$$

3. Sim:

$$
a\in\Sigma
$$

4. Não:

$$
d\notin\Sigma
$$

5. Exemplos de palavras válidas:

```text
a
ab
abc
bca
cab
```

### Comentário

Uma palavra pode possuir um ou vários símbolos, desde que todos pertençam ao alfabeto.

---

# Exercício 2

Para:

$$
\Sigma={0,1}
$$

| Sequência | Resposta   | Justificativa                           |
| --------- | ---------- | --------------------------------------- |
| `0101`    | Válida     | Todos os símbolos são `0` ou `1`        |
| `00110`   | Válida     | Todos os símbolos são `0` ou `1`        |
| `012`     | Não válida | `2` não pertence ao alfabeto            |
| `111`     | Válida     | Todos os símbolos pertencem ao alfabeto |
| `10a`     | Não válida | `a` não pertence ao alfabeto            |

---

# Exercício 3

Para:

$$
\Sigma={0,1}
$$

### 1.

$$
0\in\Sigma
$$

**Verdadeiro.**

### 2.

$$
1\in\Sigma
$$

**Verdadeiro.**

### 3.

$$
01\in\Sigma
$$

**Falso.**

`01` é uma palavra, não um símbolo individual.

### 4.

$$
01\in\Sigma^*
$$

**Verdadeiro.**

### 5.

$$
2\in\Sigma
$$

**Falso.**

### 6.

$$
101\in\Sigma^*
$$

**Verdadeiro.**

Todos os símbolos de `101` pertencem ao alfabeto.

---

# Exercício 4

Para:

$$
L={0,01,011,0111}
$$

| Palavra | Pertence a $L$? |
| ------- | --------------- |
| `0`     | Sim             |
| `01`    | Sim             |
| `0111`  | Sim             |
| `10`    | Não             |
| `111`   | Não             |
| `011`   | Sim             |

### Comentário

Uma palavra pertence à linguagem quando ela é um dos elementos definidos no conjunto.

---

# Exercício 5

$$
L={b^n\mid n\geq1}
$$

As cinco primeiras palavras são:

```text
b
bb
bbb
bbbb
bbbbb
```

O símbolo:

$$
b^n
$$

representa `n` ocorrências de `b`.

A palavra:

```text
bbbbbb
```

possui seis `b`.

Logo:

$$
bbbbbb=b^6
$$

e:

$$
bbbbbb\in L
$$

Já:

$$
\varepsilon\notin L
$$

porque a condição determina:

$$
n\geq1
$$

---

# Exercício 6

### A

$$
L=\emptyset
$$

Não possui nenhuma palavra.

### B

$$
L={\varepsilon}
$$

Possui exatamente uma palavra:

$$
\varepsilon
$$

Essa palavra possui comprimento:

$$
|\varepsilon|=0
$$

### Resposta

$$
\boxed{\emptyset\neq{\varepsilon}}
$$

---

# Exercício 7

Considere:

$$
G=({S,A},{0,1},P,S)
$$

com:

$$
P={S\rightarrow0A,\ A\rightarrow1}
$$

### Respostas

**Variáveis:**

$$
V={S,A}
$$

**Terminais:**

$$
T={0,1}
$$

**Produções:**

$$
P={S\rightarrow0A,\ A\rightarrow1}
$$

**Símbolo inicial:**

$$
S
$$

### Palavra gerada

Começamos:

$$
S
$$

Aplicamos:

$$
S\rightarrow0A
$$

Então:

$$
S\Rightarrow0A
$$

Agora:

$$
A\rightarrow1
$$

Logo:

$$
0A\Rightarrow01
$$

Portanto:

$$
\boxed{01}
$$

---

# Exercício 8

Aplicando:

$$
S\rightarrow0S
$$

três vezes:

$$
S
\Rightarrow0S
\Rightarrow00S
\Rightarrow000S
$$

### Resposta

$$
\boxed{000S}
$$

### Atenção

A derivação ainda não terminou porque existe o não terminal:

$$
S
$$

---

# Exercício 9

Para gerar:

```text
aaab
```

temos:

$$
S
\Rightarrow aS
\Rightarrow aaS
\Rightarrow aaaS
\Rightarrow aaab
$$

Portanto:

$$
\boxed{aaab\in L(G)}
$$

### Como pensar?

Cada aplicação:

$$
S\rightarrow aS
$$

adiciona um `a`.

Quando já temos a quantidade necessária de `a`, utilizamos:

$$
S\rightarrow b
$$

para finalizar.

---

# Exercício 10

Gramática:

$$
G:
\begin{cases}
S\rightarrow0S\
S\rightarrow1
\end{cases}
$$

### 1. `1`

Sim:

$$
S\Rightarrow1
$$

### 2. `01`

Sim:

$$
S\Rightarrow0S\Rightarrow01
$$

### 3. `001`

Sim:

$$
S\Rightarrow0S\Rightarrow00S\Rightarrow001
$$

### 4. `0001`

Sim:

$$
S\Rightarrow0S
\Rightarrow00S
\Rightarrow000S
\Rightarrow0001
$$

### 5. `101`

Não.

Depois que utilizamos:

$$
S\rightarrow1
$$

a derivação termina.

Não é possível produzir outro `0` ou `1`.

### 6. `1001`

Não.

A gramática permite:

```text
zero ou mais 0
+
um 1 final
```

Portanto, palavras válidas possuem o formato:

```text
000...001
```

A palavra `1001` começa com `1` e depois possui outros símbolos, o que não é permitido.

---

# Resumo dos conceitos

| Conceito           | Significado                                                           |
| ------------------ | --------------------------------------------------------------------- |
| $\Sigma$           | Alfabeto                                                              |
| `a`, `b`, `0`, `1` | Símbolos                                                              |
| $w$                | Palavra                                                               |
| $L$                | Linguagem                                                             |
| $\Sigma^*$         | Conjunto de todas as palavras sobre $\Sigma$, incluindo $\varepsilon$ |
| $\varepsilon$      | Palavra vazia                                                         |
| $\emptyset$        | Conjunto vazio                                                        |
| $w\in L$           | A palavra $w$ pertence à linguagem                                    |
| $w\notin L$        | A palavra $w$ não pertence à linguagem                                |
| $G$                | Gramática                                                             |
| $V$                | Variáveis/não terminais                                               |
| $T$                | Terminais                                                             |
| $P$                | Produções                                                             |
| $S$                | Símbolo inicial                                                       |
| $\rightarrow$      | Produção/regra                                                        |
| $\Rightarrow$      | Derivação                                                             |

---

# Checklist de estudo

Antes de avançar para os próximos conteúdos, verifique se você consegue:

* [✔️] Explicar o que é um alfabeto.
* [✔️] Identificar os símbolos de um alfabeto.
* [✔️] Diferenciar símbolo de palavra.
* [✔️] Explicar o que é uma linguagem.
* [✔️] Verificar se uma palavra pertence a uma linguagem.
* [✔️] Interpretar $\Sigma^*$.
* [✔️] Diferenciar $\emptyset$ de $\varepsilon$.
* [✔️] Interpretar $w\in L$.
* [✔️] Identificar os componentes de uma gramática.
* [✔️] Ler uma regra como $S\rightarrow aS$.
* [✔️] Realizar uma derivação passo a passo.
* [✔️] Identificar quando uma derivação termina.
* [✔️] Determinar se uma palavra pode ser gerada por uma gramática.

---

# Desafio final

Considere:

$$
G:
\begin{cases}
S\rightarrow aS\
S\rightarrow b
\end{cases}
$$

Responda sem consultar o gabarito:

### 1.

A palavra `b` pode ser gerada?

### 2.

A palavra `ab` pode ser gerada?

### 3.

A palavra `aab` pode ser gerada?

### 4.

A palavra `aaab` pode ser gerada?

### 5.

A palavra `aba` pode ser gerada?

### 6.

Escreva a derivação completa de `aaaab`.

### 7.

Descreva, com suas palavras, o padrão das palavras geradas por essa gramática.

> **Dica:** observe o que acontece quando aplicamos várias vezes $S\rightarrow aS$ e, finalmente, utilizamos $S\rightarrow b$.

<br>

### 📝 Minha Resolução:

1. A palavra b pode ser gerada?
Sim. Basta aplicar a regra S→b diretamente, sem usar S→aS nenhuma vez.
S ⇒ b

2. A palavra ab pode ser gerada?
Sim. Aplico S→aS uma vez, e depois S→b para encerrar.
S ⇒ aS ⇒ ab

3. A palavra aab pode ser gerada?
Sim. Preciso de dois as antes do b, então aplico S→aS duas vezes, e depois S→b.
S ⇒ aS ⇒ aaS ⇒ aab

4. A palavra aaab pode ser gerada?
Sim. Preciso de três as antes do b, então aplico S→aS três vezes, e depois S→b.
S ⇒ aS ⇒ aaS ⇒ aaaS ⇒ aaab

5. A palavra aba pode ser gerada?
Não. O motivo é que a única forma de "encerrar" a derivação é aplicando S→b, e essa regra troca o S por b sem deixar mais nenhum S para continuar a produção. Uma vez que o b aparece, ele tem que ser o último símbolo da palavra. Em aba, o b aparece no meio da palavra, e depois dele ainda tem um a. Não existe regra que permita continuar produzindo depois do b. Então aba não pertence à linguagem.

6. Escreva a derivação completa de aaaab.
A palavra aaaab tem quatro as seguidos de um b. Então preciso aplicar S→aS quatro vezes, e no final aplicar S→b:
S ⇒ aS ⇒ aaS ⇒ aaaS ⇒ aaaaS ⇒ aaaab

Passo a passo:
S ⇒ aS (1ª aplicação de S→aS)
⇒ aaS (2ª aplicação)
⇒ aaaS (3ª aplicação)
⇒ aaaaS (4ª aplicação)
⇒ aaaab (aplicação de S→b)

7. Descreva, com suas palavras, o padrão das palavras geradas por essa gramática.
Essa gramática gera palavras formadas por zero ou mais as seguidos de exatamente um b no final. O b sempre aparece uma única vez, e sempre na última posição da palavra; antes dele só podem existir as (podendo até não ter nenhum a).
Isso acontece porque a regra S→aS "cresce" a palavra adicionando as na frente, enquanto a regra S→b "termina" a derivação, colocando o b como último símbolo.

Em notação mais formal, a linguagem gerada é:
L(G) = {a^n b ∣ n≥0}

