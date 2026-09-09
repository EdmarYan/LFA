# Relatório de Validação e Resoluções - Expressões Regulares

## 1.a) Exercício Guiado

### Questão 1: Termina em 00
* **Linguagem:** Conjunto de palavras sobre o alfabeto {0,1} que terminam obrigatoriamente com o sufixo "00".
* **Regex:** `^[01]*00$`
* **Link de Validação:** [https://www.phpliveregex.com/p/Pqr](https://www.phpliveregex.com/p/Pqr)

| Entrada de Teste | Status Real | Justificativa |
| :--- | :--- | :--- |
| `00` | **Aceito** | Condição mínima atendida. |
| `100` | **Aceito** | Termina em 00, precedido por 1. |
| `110100` | **Aceito** | Termina em 00, precedido por combinação válida. |
| `010` | **Rejeitado** | Não termina em 00. |
| `111` | **Rejeitado** | Não contém 00 no final. |
| `0` | **Rejeitado** | String incompleta (falta um 0). |

<br>

### 1.b) Exatamente dois 'a'
* **Linguagem:** Conjunto de palavras sobre o alfabeto {a,b} que contêm o caractere 'a' exatamente duas vezes.
* **Regex:** `^b*ab*ab*$`
* **Link de Validação:** [https://www.phpliveregex.com/p/Pqs](https://www.phpliveregex.com/p/Pqs)

| Entrada de Teste | Status Real | Justificativa |
| :--- | :--- | :--- |
| `aa` | **Aceito** | Exatamente dois 'a', sem nenhum 'b'. |
| `baa` | **Aceito** | Exatamente dois 'a', com 'b' no início. |
| `aba` | **Aceito** | Exatamente dois 'a', com 'b' no meio. |
| `bbabbab` | **Aceito** | Exatamente dois 'a', cercados por vários 'b's. |
| `a` | **Rejeitado** | Falta um 'a'. |
| `aaa` | **Rejeitado** | Possui três 'a' (excede o limite de 2). |
| `b` | **Rejeitado** | Não possui nenhum 'a'. |

<br>

### 1.c) Identificador
* **Linguagem:** Conjunto de strings que começam estritamente com duas letras maiúsculas, seguidas por três algarismos, e terminam com uma letra minúscula opcional.
* **Regex:** `^[A-Z]{2}[0-9]{3}[a-z]?$`

| Entrada de Teste | Status Real | Justificativa |
| :--- | :--- | :--- |
| `AB123` | **Aceito** | 2 maiúsculas, 3 números, sem a minúscula opcional (válido). |
| `XY999z` | **Aceito** | 2 maiúsculas, 3 números, com a minúscula no final. |
| `BR007a` | **Aceito** | 2 maiúsculas, 3 números, com a minúscula no final. |
| `aB123` | **Rejeitado** | Inicia com letra minúscula. |
| `ABC123` | **Rejeitado** | Possui 3 letras maiúsculas (excede o limite de 2). |
| `AB12` | **Rejeitado** | Possui apenas 2 números (faltou um). |
| `AB123ab` | **Rejeitado** | Possui 2 minúsculas no final (excede o limite de 1). |

---

## 2. Desafio: Matrícula Acadêmica

* **Linguagem:** Strings que representam matrículas universitárias com curso específico (CCO, ESW ou SIS), ano entre 2024 e 2029, exatamente quatro algarismos e turno válido (M, T ou N), separados por hífen.
* **Dados Aplicados:** Ciência da Computação (CCO), Ano 2026, Número 4767, Turno Noturno (N).
* **Regex:** `^(CCO|ESW|SIS)-202[4-9]-[0-9]{4}-[MTN]$`
* **Link de Validação:** [https://www.phpliveregex.com/p/Pqt](https://www.phpliveregex.com/p/Pqt)

| Entrada de Teste | Status Real | Justificativa |
| :--- | :--- | :--- |
| `CCO-2026-4767-N` | **Aceito** | Cumpre todos os requisitos (Matrícula real). |
| `ESW-2029-0000-M` | **Aceito** | Limite superior do ano (2029) e turno válido. |
| `CCO-2023-4767-N` | **Rejeitado** | *Caso de fronteira:* O ano 2023 é anterior ao limite (2024). |
| `ESW-2029-123-M` | **Rejeitado** | *Caso de fronteira:* Faltam dígitos no número (tem 3, exige 4). |
| `SIS-2026-4767-X` | **Rejeitado** | Turno inválido ('X' não pertence a M, T ou N). |
| `cco-2026-4767-N` | **Rejeitado** | *Quase correta:* Falha por ter o curso em letras minúsculas. |

---

## 3. Questões para Reflexão Teórica (Discursivas)

**1. Toda expressão regular formal representa uma linguagem regular?**
Sim. Pelo Teorema de Kleene, as expressões regulares clássicas (aquelas construídas estritamente com operações de união, concatenação e Fecho de Kleene) descrevem, por definição, a classe exata das linguagens regulares. 

**2. Toda linguagem regular possui uma expressão regular?**
Sim. A equivalência demonstrada pelo Teorema de Kleene é bidirecional. Se uma linguagem é regular (podendo ser reconhecida por um Autômato Finito), existe um algoritmo sistemático para convertê-la em uma expressão regular correspondente e vice-versa.

**3. Como uma Regex se relaciona com DFA e NFA?**
Eles são três modelos matemáticos distintos, mas que possuem o **mesmo poder expressivo**. Eles se relacionam através de algoritmos de conversão:
* Uma Regex pode ser convertida em um NFA (por exemplo, via Construção de Thompson).
* Um NFA pode ser convertido em um DFA equivalente (via Algoritmo da Construção de Subconjuntos).
* Um DFA pode ser convertido de volta para uma Regex (utilizando Eliminação de Estados ou o Lema de Arden).

**4. Quais extensões de motores não pertencem à definição clássica?**
Os motores modernos de expressões regulares em linguagens de programação (como PCRE, Java, Python, PHP) suportam funcionalidades que ultrapassam a regularidade matemática formal. A principal delas é a **Retroreferência** (*Backreferences*, como `\1` ou `\2`), que confere "memória" ao motor para lembrar de capturas anteriores, algo impossível em um autômato finito. Outras extensões incluem *Lookaheads*, *Lookbehinds* e suporte à recursão.

**5. Por que a linguagem $L = \{a^nb^n \mid n \ge 0\}$ não pode ser reconhecida por um DFA?**
Para reconhecer essa linguagem (que exige que o número de ocorrências de 'a' seja exatamente igual ao de 'b'), a máquina precisaria de uma forma de contar ou memorizar quantos 'a's foram lidos, já que $n$ pode tender ao infinito. Um DFA (Autômato Finito Determinístico) possui um número finito e fixo de estados, o que significa que sua memória é estritamente limitada. Ele não consegue realizar contagens ilimitadas, provando que essa linguagem não é regular (trata-se de uma Linguagem Livre de Contexto).
