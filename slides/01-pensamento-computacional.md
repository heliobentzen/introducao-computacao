---
marp: true
theme: default
paginate: true
backgroundColor: #1a1a2e
color: #eaeaea
style: |
  section {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }
  h1 {
    color: #e94560;
  }
  h2 {
    color: #0f3460;
    background: #e94560;
    padding: 4px 16px;
    border-radius: 4px;
    color: #fff;
  }
  table {
    font-size: 0.8em;
  }
  code {
    background: #16213e;
    color: #e94560;
  }
  a {
    color: #00d2ff;
  }
  blockquote {
    border-left: 4px solid #e94560;
    color: #ccc;
  }
---

# 01 — Pensamento Computacional

**Introdução à Computação — ADS**
Decompor. Reconhecer padrões. Abstrair. Algoritmizar.

---

## O que é Computação?

> "Ciência da Computação é o estudo de **algoritmos**, incluindo suas propriedades formais e matemáticas, seu hardware, seu software e suas aplicações." — Aho & Ullman (1992)

- Não é "mexer no computador"
- É uma **ciência do pensamento estruturado**
- Impacta todas as áreas do conhecimento

---

## Pensamento Computacional

Conceito formalizado por **Jeannette Wing (2006)**:

> Processo de formulação de problemas e suas soluções de forma que possam ser representadas como sequências de passos computacionais.

**4 Pilares:**

1. Decomposição
2. Reconhecimento de padrões
3. Abstração
4. Algoritmos

---

## Pilar 1 — Decomposição

Quebrar um problema complexo em partes menores e gerenciáveis.

| Problema | Subproblemas |
|----------|-------------|
| Construir um app de delivery | Cadastro, cardápio, carrinho, pagamento, rastreamento, avaliação |
| Organizar uma viagem | Destino, transporte, hospedagem, roteiro, orçamento |

**Princípio:** se o problema parece impossível, você não dividiu o suficiente.

---

## Pilar 2 — Reconhecimento de Padrões

Identificar **regularidades** e **similaridades** entre problemas ou dados.

- Playlists do Spotify: padrões no seu histórico
- Detecção de fraude bancária: padrões de transações
- Diagnóstico médico: padrões de sintomas

**Sem padrões** → cada problema seria resolvido do zero.

---

## Pilar 3 — Abstração

Focar no que é **essencial**, ignorar o que é **irrelevante**.

| Realidade | Abstração |
|-----------|----------|
| Mapa com relevo, rios, vegetação | Mapa de metrô: apenas estações e conexões |
| Pessoa com 200+ atributos | Cadastro: nome, CPF, e-mail |

**Regra:** boa abstração remove complexidade sem perder informação essencial.

---

## Pilar 4 — Algoritmos

Sequência **finita, ordenada e não-ambígua** de passos para resolver um problema.

**Qualidades de um bom algoritmo:**

- **Finitude** — termina em tempo finito
- **Definitude** — cada passo é preciso
- **Entrada/saída** — recebe dados, produz resultado
- **Efetividade** — cada passo é realizável

---

## Computabilidade — Existe Limite?

**Problema da Parada (Turing, 1936):**

> É impossível criar um programa que determine, para qualquer programa e entrada, se ele vai parar ou rodar para sempre.

Implicação: existem problemas que **nenhum algoritmo** pode resolver.

---

## Aplicação em ADS

| Pilar | Na prática profissional |
|-------|----------------------|
| Decomposição | Quebrar requisitos em user stories |
| Padrões | Reutilizar design patterns |
| Abstração | Modelar APIs e interfaces |
| Algoritmos | Implementar lógica de negócio |

---

## Referências-chave

- Wing, J. (2006). Computational Thinking. *CACM*
- Aho, A. & Ullman, J. (1992). *Foundations of Computer Science*
- Turing, A. (1936). On Computable Numbers
- Denning, P. (2009). Beyond Computational Thinking. *CACM*

---

## Checkpoint

**→ Checkpoint 01** (com módulo 02)
Farmácia + controle de medicamentos: decomposição, pseudocódigo, fluxograma.
