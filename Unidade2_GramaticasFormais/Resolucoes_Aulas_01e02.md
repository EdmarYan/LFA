# Resoluções - Exercícios Comentados (Aulas 01 e 02)

**Aluno:** Edmar Yan Faria de Melo

---

## 1. Alfabeto

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

## 2. Palavras sobre um alfabeto

Lembrando: uma palavra é válida sobre Σ={0,1} se todos os símbolos que a compõem pertencem a Σ.

1. 0101 → Válida. Todos os símbolos (0 e 1) pertencem a Σ.
2. 00110 → Válida. Mesma justificativa: só usa 0 e 1.
3. 012 → Não válida. O símbolo 2 não pertence a Σ={0,1}.
4. 111 → Válida. Usa apenas o símbolo 1, que pertence a Σ.
5. 10a → Não válida. O símbolo a não pertence a Σ={0,1}.

---

## 3. Pertinência de símbolos e palavras

Aqui é importante ter cuidado com uma distinção importante: Σ é o conjunto de símbolos (letras individuais), enquanto Σ* é o conjunto de todas as palavras possíveis formadas com esses símbolos (incluindo a palavra vazia ε).

1. 0∈Σ → Verdadeiro. 0 é um dos símbolos do alfabeto.
2. 1∈Σ → Verdadeiro. 1 é um dos símbolos do alfabeto.
3. 01∈Σ → Falso. 01 é uma palavra (sequência de dois símbolos), não um único símbolo. Σ contém apenas símbolos isolados, então 01 não pode pertencer a Σ.
4. 01∈Σ* → Verdadeiro. Σ* é o conjunto de todas as palavras formadas com os símbolos de Σ, e 01 é uma sequência válida formada só por 0 e 1.
5. 2∈Σ → Falso. O símbolo 2 não faz parte do alfabeto {0,1}.
6. 101∈Σ* → Verdadeiro. 101 é formada só por símbolos de Σ, logo é uma palavra válida pertencente a Σ*.

---

## 4. Compreendendo o conjunto linguagem

Aqui L={0,01,011,0111} é uma linguagem definida explicitamente, ou seja, por enumeração das palavras que a compõem. Uma palavra pertence a L se, e somente se, ela estiver literalmente listada dentro do conjunto.

1. 0∈L → Verdadeiro. 0 está listado em L.
2. 01∈L → Verdadeiro. 01 está listado em L.
3. 0111∈L → Verdadeiro. 0111 está listado em L.
4. 10∈L → Falso. 10 não aparece em L (repare que a ordem dos símbolos importa: 10 é diferente de 01).
5. 111∈L → Falso. 111 não está entre as palavras listadas em L.
6. 011∈L → Verdadeiro. 011 está listado em L.

---

## 5. Descrevendo uma linguagem por padrão

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

## 6. Linguagem vazia e palavra vazia

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

## 7. Componentes de uma gramática

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

## 8. Derivação em uma gramática

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

## 9. Derivação completa de uma palavra

Gramática:
S→aS ∣ b
Queremos gerar aaab.

S ⇒ aS ⇒ aaS ⇒ aaaS ⇒ aaab

Contamos quantas vezes usamos cada regra: usamos S→aS três vezes (uma para cada a) e S→b uma vez, no final. Isso bate exatamente com a estrutura da palavra aaab.

---

## 10. Verificando palavras em uma gramática

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

## Desafio final

Gramática:
S→aS ∣ b

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
