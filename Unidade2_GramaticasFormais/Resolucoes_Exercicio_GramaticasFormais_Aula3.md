# Resoluções - Exercícios Práticos para Fixação (Aula 3)

**Aluno:** Edmar Yan Faria de Melo

---

## Bloco 1 (Derivação)

Gramática G1: 
S -> aS | b

**A) Gere a palavra aaab.**

Preciso de três as antes do b. Então aplico S→aS três vezes, e por último S→b para fechar.
S ⇒ aS ⇒ aaS ⇒ aaaS ⇒ aaab

Passo a passo:
S ⇒ aS (1ª aplicação de S→aS)
⇒ aaS (2ª aplicação)
⇒ aaaS (3ª aplicação)
⇒ aaab (aplico S→b, trocando o último S pelo terminal b)

**B) Explique como você sabe que a derivação terminou.**

A derivação termina quando não sobra mais nenhuma variável (não-terminal) na palavra — ou seja, quando a sentença é formada só por símbolos terminais. Nessa gramática, isso só acontece quando eu aplico a regra S→b, porque é a única regra que não deixa nenhum S "sobrando" no lado direito. Enquanto eu continuar aplicando S→aS, sempre vai sobrar um S (mais um a na frente), então a derivação segue em aberto. Assim que aplico S→b, a última variável desaparece e a palavra fica pronta — não há mais nada para reescrever.

---

## Bloco 2 (GLC)

Gramática G2: 
S -> aSb | ε

Essa regra é interessante porque ela "envolve" o S entre um a e um b ao mesmo tempo, e a única forma de encerrar é substituir S por ε (a palavra vazia). Isso faz com que a linguagem gerada seja do tipo a^n b^n, ou seja, sempre a mesma quantidade de as e de bs, com todos os as na frente e todos os bs atrás.

**A) Gere a palavra aaabbb.**

Como aaabbb tem três as e três bs, preciso aplicar S→aSb três vezes, e depois S→ε para fechar.

S ⇒ aSb ⇒ a(aSb)b ⇒ aaSbb ⇒ a(aSb)bb ⇒ aaaSbbb ⇒ aaa(ε)bbb ⇒ aaabbb

De forma mais organizada:
S ⇒ aSb (1ª aplicação — o novo S fica "no meio", entre um a e um b)
⇒ aaSbb (2ª aplicação — envolve o S de novo)
⇒ aaaSbbb (3ª aplicação)
⇒ aaabbb (aplico S→ε, ou seja, apago o S do meio, já que ε é a palavra vazia)

Repare que o S desaparece "no meio" da palavra, e é justamente por isso que sobra sempre a mesma quantidade de as (à esquerda) e bs (à direita).

**B) É possível gerar aabbb? Justifique.**

Não é possível. A palavra aabbb tem 2 símbolos a e 3 símbolos b — quantidades diferentes. Só que, pela estrutura da regra S→aSb, toda vez que adicionamos um a na frente, obrigatoriamente adicionamos também um b no final, na mesma aplicação da regra. Ou seja, é fisicamente impossível gerar mais bs do que as (ou vice-versa) usando essa gramática — os dois sempre crescem juntos, em pares. Como a linguagem gerada é L(G2) = {a^n b^n ∣ n≥0} (quantidades sempre iguais), e aabbb teria que ser a^2 b^3 (quantidades diferentes), essa palavra não pertence a L(G2) e não pode ser gerada.

---

## Bloco 3 (Classificação)

Gramática: 
S -> aA | A -> b

**Classificação: Regular.**

**Justificativa:** essa gramática é o que chamamos de gramática regular (mais especificamente, uma gramática linear à direita / right-linear). O critério para isso é que, em cada produção, o lado direito tem no máximo um terminal seguido de no máximo uma variável — e nunca uma variável seguida de outra coisa depois dela, nem duas variáveis na mesma produção.

Olhando as regras:
S → aA: um terminal (a) seguido de uma única variável (A) — respeita o formato regular.
A → b: só um terminal (b), sem nenhuma variável — também respeita o formato, encerrando a derivação.

Como todas as produções seguem esse padrão (terminal, opcionalmente seguido de uma única variável no final), a gramática é regular. Diferente do Bloco 2, onde a regra S→aSb tem a variável S no meio da produção (terminal antes E depois da variável), o que já não é permitido em uma gramática regular — esse tipo de estrutura (variável "encaixotada" entre terminais) é característico de uma gramática livre de contexto que não é regular, já que é exatamente esse formato que permite "contar" e emparelhar quantidades iguais de as e bs, coisa que uma gramática regular não consegue fazer.

Aliás, a linguagem gerada pela gramática do Bloco 3 é bem simples: só a palavra ab (fazendo S ⇒ aA ⇒ ab). Uma linguagem com uma única palavra finita como essa é sempre regular.
