# Máquina de Turing (29/09) 1,0 ponto - Prazo 30/09

**Disciplina:** Teoria da Computação / Linguagens Formais e Autômatos  
**Referência:** Akitando #86 — O Computador de Turing e Von Neumann: Por que calculadoras não são computadores?  
**Documento da Atividade:** [Documento.pdf](./Documento.pdf)

---

## 1. Objetivos da atividade
Ao final da atividade, o estudante deverá ser capaz de:
- Compreender o conceito de Máquina de Turing.
- Identificar os principais componentes de uma Máquina de Turing.
- Compreender a importância das Máquinas de Turing para a computação.
- Construir e simular uma Máquina de Turing simples.
- Reconhecer que existem problemas que não podem ser resolvidos por algoritmos, compreendendo os limites da computação.

## 2. Conteúdo
- Conceito de Máquina de Turing.
- Fita, cabeça de leitura/escrita e estados.
- Alfabeto e regras de transição.
- Funcionamento de uma Máquina de Turing.
- Simulação computacional.
- Computabilidade e limites computacionais.

---

## 3. Desenvolvimento da atividade

### Etapa 1 — Introdução

**1. O que é uma Máquina de Turing?**  
É um modelo matemático abstrato criado por Alan Turing em 1936 para definir o conceito de computação. Funciona como um mecanismo que opera sobre uma fita de memória potencialmente infinita, lendo, gravando e apagando símbolos de acordo com um conjunto finito de estados e regras, definindo o que pode ser processado mecanicamente.

**2. Quais são os principais componentes de uma Máquina de Turing?**  
Composta por: uma fita infinita dividida em células (memória de trabalho); uma cabeça de leitura/escrita que se move para a esquerda ou direita; um conjunto de estados finitos (incluindo estado inicial e de parada); e uma tabela de transições que dita a ação a ser executada com base no símbolo lido e no estado atual.

**3. Qual é a importância das Máquinas de Turing para a computação?**  
Estabeleceu a fronteira definitiva entre meras calculadoras (de função fixa ou cabeadas) e computadores reais. Com a Máquina de Turing Universal, provou que um único equipamento pode ler regras da fita como dados e executar qualquer programa, servindo de base para a arquitetura Von Neumann e delimitando o que qualquer computador presente ou futuro é capaz de processar.

**4. Qual é a relação entre Máquina de Turing e algoritmo?**  
Um algoritmo é a descrição passo a passo, mecânica e finita para processar uma entrada e gerar uma saída. Pela Tese de Church-Turing, qualquer coisa que seja humanamente ou mecanicamente calculável por um algoritmo pode ser calculada por uma Máquina de Turing. Se uma tarefa não pode ser descrita e concluída por regras de transição em uma Máquina de Turing, não existe algoritmo no universo capaz de resolvê-la.

---

### Etapa 2 — Simulação

**Desafio proposto:**  
Criar uma máquina capaz de reconhecer palavras da forma $0^n 1^n$. A máquina deverá verificar se existe a mesma quantidade de símbolos 0 e 1, seguindo a lógica de funcionamento de uma Máquina de Turing.

**Descrição da Máquina de Turing criada:**  
Opera por emparelhamento: lê o primeiro 0, marca com X e avança buscando o primeiro 1 para marcá-lo com Y. Em seguida, retorna até o marcador X e repete o ciclo. Concluídos os pares, verifica se restaram apenas Ys até o espaço em branco final (`_`), atingindo halt-accept. Se houver símbolos desbalanceados ou fora de ordem, a máquina para por ausência de regra, caracterizando rejeição.

#### Código da Máquina (Simulador Anthony Morphett):
```text
; Estado 0 (inicial): le o primeiro 0, marca com X e vai para 1
0 0 X r 1
0 Y Y r 3

; Estado 1: pula 0s e Ys ate achar o primeiro 1
1 0 0 r 1
1 Y Y r 1
1 1 Y l 2

; Estado 2: volta para a esquerda ate achar a marca X
2 Y Y l 2
2 0 0 l 2
2 X X r 0

; Estado 3: verifica se só restam marcas Y ate o fim da fita
3 Y Y r 3
3 _ _ r halt-accept
```

---

### Etapa 3 — Registro da simulação

#### Tabela de Testes

| Teste | Entrada | Resultado esperado | Resultado obtido | Estados percorridos |
| :---: | :---: | :---: | :---: | :--- |
| 1 | `01` | ACEITA | ACEITA | `0 -> 1 -> 2 -> 0 -> 3 -> halt-accept` |
| 2 | `0011` | ACEITA | ACEITA | `0 -> 1 -> 1 -> 2 -> 2 -> 0 -> 1 -> 1 -> 2 -> 2 -> 0 -> 3 -> 3 -> halt-accept` |
| 3 | `001` | REJEITA | REJEITA | `0 -> 1 -> 1 -> 2 -> 2 -> 0 -> 1 -> 1 -> halt` |

#### Evidências da Execução (Capturas de Tela)

**Teste 1 — Entrada 01 (Aceita - 5 passos):**  
![Teste 1 — Entrada 01](./teste1_01.png)

**Teste 2 — Entrada 0011 (Aceita - 13 passos):**  
![Teste 2 — Entrada 0011](./teste2_0011.png)

**Teste 3 — Entrada 001 (Rejeitada - 8 passos):**  
![Teste 3 — Entrada 001](./teste3_001.png)

---

### Etapa 4 — Reflexão sobre os limites computacionais

**Uma Máquina de Turing consegue resolver qualquer problema? Explique com suas palavras por que existem problemas que não podem ser resolvidos por algoritmos.**  
A Máquina de Turing não resolve qualquer problema. Turing provou a existência de problemas indecidíveis, como o Problema da Parada, demonstrando ser logicamente impossível criar um algoritmo geral que determine se qualquer programa arbitrário irá parar ou entrar em loop infinito. Além disso, há a limitação física: enquanto a máquina teórica assume uma fita infinita, os computadores reais operam com memória finita e estão sujeitos a estouro de memória (out of memory).

---

## 6. Questão final — Problema para reflexão

**Problema para reflexão:**  
Imagine que você recebeu um problema computacional muito complexo. Como saber se ele é apenas difícil de resolver ou se, na verdade, não existe nenhum algoritmo capaz de resolvê-lo para todos os casos? Explique utilizando os conceitos estudados sobre Máquinas de Turing, computabilidade e limites computacionais.

**Resposta:**  
A distinção baseia-se em Complexidade versus Computabilidade. Um problema "apenas difícil" é decidível: existe algoritmo que o resolve para todas as entradas em tempo finito, mas o custo computacional cresce exponencialmente (ex.: problemas NP-difíceis), sendo contornável via heurísticas. Já um problema "impossível" é indecidível: prova-se por redução (mostrando equivalência ao Problema da Parada) que nenhum algoritmo determinístico geral pode existir para solucioná-lo em todos os casos.
