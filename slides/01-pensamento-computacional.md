---
marp: true
theme: default
paginate: true
header: '![w:90](ifpe-logo.png)'
footer: 'Introdução à Computação · IFPE'
style: |
  /* ── Tema IFPE · Fundo Branco · Verde e Vermelho ── */
  section { font-family: 'Segoe UI', system-ui, sans-serif; background: #ffffff; color: #222; }
  header { top: 16px; right: 24px; left: auto; }
  header img { margin: 0; }
  footer { color: #666; font-size: 0.6em; border-top: 2px solid #2f9e41; padding-top: 4px; }
  h1 { color: #2f9e41; font-size: 2em; border-bottom: 3px solid #cd191e; padding-bottom: 6px; }
  h2 { color: #2f9e41; font-size: 1.4em; }
  strong { color: #cd191e; }
  em { color: #2f9e41; font-style: normal; }
  table { font-size: 0.72em; border-collapse: collapse; }
  th { background: #2f9e41; color: #fff; padding: 6px 10px; }
  td { border: 1px solid #ddd; padding: 5px 10px; background: #fafafa; }
  code { background: #f0f0f0; color: #cd191e; padding: 2px 6px; border-radius: 4px; }
  pre { background: #f7f7f7 !important; border-radius: 8px; border: 1px solid #ddd; }
  pre code { color: #333; background: none; }
  blockquote { border-left: 4px solid #2f9e41; background: #f0faf0; padding: 8px 16px; border-radius: 0 8px 8px 0; color: #333; }
  a { color: #2f9e41; }
  section::after { color: #999; font-size: 0.7em; }
  /* Capa */
  section.capa { display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; }
  section.capa h1 { border: none; font-size: 1.6em; }
  section.capa h2 { margin-top: -10px; }
---

<!-- _class: capa -->
<!-- _paginate: false -->
<!-- _header: '' -->
<!-- _footer: '' -->

![w:220](ifpe-logo.png)

# Introdução à Computação

## Módulo 01 · Pensamento Computacional

**Prof. Hélio Bentzen**
IFPE · Análise e Desenvolvimento de Sistemas

---

# 🧠 Pensamento Computacional

---

## O que é Computação?

> Ciência do **pensamento estruturado** aplicado à resolução de problemas — Aho & Ullman, 1992

- Não é "mexer no computador"
- Estuda **algoritmos** e suas propriedades
- Impacta **todas** as áreas do conhecimento

![bg right:35% opacity:0.12](https://images.unsplash.com/photo-1509228468518-180dd4864904?w=400&fit=crop)

---

## Os 4 Pilares — Wing (2006)

| Pilar | O que faz |
|-------|----------|
| 🧩 **Decomposição** | Divide o problema em partes menores |
| 🔍 **Padrões** | Identifica regularidades |
| 🎭 **Abstração** | Foca no essencial, ignora ruído |
| 📋 **Algoritmos** | Define passos para a solução |

> Se o problema parece impossível, *você não dividiu o suficiente*.

---

## Pilar 1 — Decomposição

Quebrar um problema grande em **subproblemas gerenciáveis**.

| Problema | Subproblemas |
|----------|-------------|
| App de delivery | Cadastro · Cardápio · Carrinho · Pagamento |
| Planejar viagem | Destino · Transporte · Hotel · Roteiro |

---

## Pilar 2 — Reconhecimento de Padrões

Encontrar **regularidades** entre problemas ou dados.

- 🎵 Spotify — padrões no histórico → playlist
- 🏦 Banco — padrões de transações → fraude
- 🏥 Medicina — padrões de sintomas → diagnóstico

> Sem padrões → cada problema resolvido do zero.

---

## Pilar 3 — Abstração

Focar no **essencial**, descartar o irrelevante.

| Realidade complexa | Abstração útil |
|-------------------|---------------|
| Mapa com relevo e rios | Mapa do metrô: estações + linhas |
| Pessoa com 200+ atributos | Cadastro: nome, CPF, e-mail |

*Boa abstração remove complexidade* **sem perder informação essencial**.

---

## Pilar 4 — Algoritmos

Sequência **finita, ordenada e não-ambígua** de passos.

✅ **Finitude** — termina em tempo finito
✅ **Definitude** — cada passo é preciso
✅ **Entrada/Saída** — recebe dados, produz resultado
✅ **Efetividade** — cada passo é realizável

---

## Existe Limite? — Problema da Parada

**Turing (1936):** é impossível criar um programa que determine, para *qualquer* programa, se ele vai parar ou rodar para sempre.

```
           ┌──────────────┐
  P(x) ──▶│  Vai parar?   │──▶ ??? (indecidível)
           └──────────────┘
```

> Existem problemas que **nenhum algoritmo** pode resolver.

---

## Na Prática — ADS

| Pilar | Aplicação profissional |
|:-----:|----------------------|
| 🧩 | Quebrar requisitos em *user stories* |
| 🔍 | Reutilizar *design patterns* |
| 🎭 | Modelar APIs e interfaces |
| 📋 | Implementar lógica de negócio |

---

## Referências

- Wing, J. (2006). *Computational Thinking.* CACM
- Aho & Ullman (1992). *Foundations of Computer Science*
- Turing, A. (1936). *On Computable Numbers*

**→ Checkpoint 01** · com módulo 02
