---
marp: true
theme: default
paginate: true
style: |
  /* ── Tema Moderno · Intro Computação ── */
  section { font-family: 'Segoe UI', system-ui, sans-serif; background: linear-gradient(135deg,#0c0c1d,#1a1a3e); color: #e8e8f0; }
  h1 { color: #ff6b6b; font-size: 2.2em; }
  h2 { background: linear-gradient(90deg,#e94560,#c23152); color: #fff; padding: 6px 20px; border-radius: 8px; display: inline-block; }
  strong { color: #00d4ff; } em { color: #ffd166; font-style: normal; }
  table { font-size: 0.72em; } th { background: rgba(233,69,96,0.85); color: #fff; }
  td { background: rgba(255,255,255,0.04); }
  code { background: rgba(0,212,255,0.12); color: #ff6b6b; padding: 2px 6px; border-radius: 4px; }
  pre { background: #12122a !important; border-radius: 10px; border: 1px solid rgba(233,69,96,0.3); }
  pre code { color: #e8e8f0; background: none; }
  blockquote { border-left: 4px solid #e94560; background: rgba(233,69,96,0.08); padding: 8px 16px; border-radius: 0 8px 8px 0; }
  a { color: #00d4ff; } img { border-radius: 10px; }
  section::after { color: rgba(255,255,255,0.3); font-size: 0.7em; }
---

<!-- _class: lead -->

# 🧠 Pensamento Computacional

**Introdução à Computação · ADS**

*Decompor · Reconhecer padrões · Abstrair · Algoritmizar*

![bg right:40% brightness:0.7](https://images.unsplash.com/photo-1516110833967-0b5716ca1387?w=600&h=400&fit=crop)

---

## 💡 O que é Computação?

> Ciência do **pensamento estruturado** aplicado à resolução de problemas — Aho & Ullman, 1992

- 🔬 Não é "mexer no computador"
- 📐 Estuda **algoritmos** e suas propriedades
- 🌍 Impacta **todas** as áreas do conhecimento

![bg right:35% opacity:0.15](https://images.unsplash.com/photo-1509228468518-180dd4864904?w=400&fit=crop)

---

## 🎯 Os 4 Pilares — Wing (2006)

| Pilar | O que faz | Emoji |
|-------|----------|:-----:|
| **Decomposição** | Divide o problema em partes menores | 🧩 |
| **Padrões** | Identifica regularidades | 🔍 |
| **Abstração** | Foca no essencial, ignora ruído | 🎭 |
| **Algoritmos** | Define passos para a solução | 📋 |

> Se o problema parece impossível, **você não dividiu o suficiente**.

---

## 🧩 Pilar 1 — Decomposição

Quebrar um problema grande em **subproblemas gerenciáveis**.

| Problema | Subproblemas |
|----------|-------------|
| 🛵 App de delivery | Cadastro · Cardápio · Carrinho · Pagamento |
| ✈️ Planejar viagem | Destino · Transporte · Hotel · Roteiro |

---

## 🔍 Pilar 2 — Reconhecimento de Padrões

Encontrar **regularidades** entre problemas ou dados.

- 🎵 Spotify: padrões no seu histórico → playlist
- 🏦 Banco: padrões de transações → fraude
- 🏥 Medicina: padrões de sintomas → diagnóstico

> Sem padrões → cada problema resolvido do zero.

---

## 🎭 Pilar 3 — Abstração

Focar no **essencial**, descartar o irrelevante.

| Realidade complexa | Abstração útil |
|-------------------|---------------|
| 🗺️ Mapa com relevo e rios | Mapa do metrô: estações + linhas |
| 👤 Pessoa com 200+ atributos | Cadastro: nome, CPF, e-mail |

*Boa abstração remove complexidade* **sem perder informação essencial**.

---

## 📋 Pilar 4 — Algoritmos

Sequência **finita, ordenada e não-ambígua** de passos.

✅ **Finitude** — termina em tempo finito
✅ **Definitude** — cada passo é preciso
✅ **Entrada/Saída** — recebe dados, produz resultado
✅ **Efetividade** — cada passo é realizável

---

## 🚫 Existe Limite? — Problema da Parada

**Turing (1936):** é impossível criar um programa que determine, para *qualquer* programa, se ele vai parar ou rodar para sempre.

```
           ┌──────────────┐
  P(x) ──▶│  Vai parar?   │──▶ ??? (indecidível)
           └──────────────┘
```

> Existem problemas que **nenhum algoritmo** pode resolver.

---

## 🛠️ Na Prática — ADS

| Pilar | Aplicação profissional |
|:-----:|----------------------|
| 🧩 | Quebrar requisitos em *user stories* |
| 🔍 | Reutilizar *design patterns* |
| 🎭 | Modelar APIs e interfaces |
| 📋 | Implementar lógica de negócio |

---

## 📚 Referências

- Wing, J. (2006). *Computational Thinking.* CACM
- Aho & Ullman (1992). *Foundations of Computer Science*
- Turing, A. (1936). *On Computable Numbers*

**→ Checkpoint 01** · com módulo 02
