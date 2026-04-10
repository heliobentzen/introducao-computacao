---
marp: true
theme: default
paginate: true
header: '![w:90](ifpe-logo.png)'
footer: 'Introdução à Computação · IFPE'
style: |
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

## Módulo 07 · Inteligência Artificial

**Prof. Hélio Bentzen**
IFPE · Análise e Desenvolvimento de Sistemas

---

# 🤖 Inteligência Artificial

---

## O Que É IA?

> Sistema que percebe o ambiente e age para maximizar desempenho. — Russell & Norvig, 2021

| | Como humanos | Racionalmente |
|:-:|:---:|:---:|
| 🧠 **Pensando** | Ciência cognitiva | Lógica formal |
| 🏃 **Agindo** | Teste de Turing | **Agente racional** ← dominante |

---

## Cronologia Essencial

| Ano | Marco |
|:---:|-------|
| 1950 | Turing — "Máquinas podem pensar?" |
| 1956 | Dartmouth — termo "AI" cunhado |
| 1997 | Deep Blue vence Kasparov |
| 2012 | AlexNet — Deep Learning domina visão |
| 2017 | Transformer — *Attention Is All You Need* |
| 2020+ | GPT-3 → ChatGPT → GPT-4 → Gemini |

> *Invernos da IA:* 1974–80 e 1987–93 (euforia → decepção → corte de verba)

---

## Paradigmas de IA

| Paradigma | Como funciona | Exemplo |
|-----------|-------------|---------|
| **Simbólica** | Regras IF-THEN | Sistemas especialistas |
| **Machine Learning** | Aprende dos dados | Detecção de spam |
| **Deep Learning** | Redes neurais profundas | Reconhecimento de imagem |

---

## Tipos de Aprendizado

| Tipo | Dados | Exemplo |
|------|:-----:|---------|
| **Supervisionado** | Rotulados | Spam / não-spam |
| **Não supervisionado** | Sem rótulos | Segmentação de clientes |
| **Por reforço** | Recompensas | AlphaGo, robótica |

```
Dados → Pré-proc. → Treino → Modelo → Inferência
  ↑                                        │
  └──── Monitoramento + Retreino ←─────────┘
```

---

## Arquiteturas Deep Learning

| Arquitetura | Uso principal |
|:-----------:|-------------|
| **MLP** | Dados tabulares |
| **CNN** | Imagens, visão |
| **RNN / LSTM** | Séries temporais |
| **Transformer** | NLP, visão, multimodal — domina tudo |

> **Backpropagation:** erro na saída é propagado de volta, ajustando pesos camada a camada.

---

## IA no Desenvolvimento

| Aplicação | Ferramenta |
|-----------|-----------|
| Code completion | Copilot, Codeium |
| Code review | CodeQL, SonarQube |
| Testes auto | Diffblue Cover |
| Chatbots | Dialogflow, Lex |
| AIOps | Datadog AI, New Relic |

---

## Limitações

| Limitação | Exemplo |
|-----------|--------|
| Dependência de dados | Dados enviesados → resultado enviesado |
| Correlação ≠ causa | Sorvete ↔ afogamentos |
| Caixa preta | Difícil explicar *por que* decidiu |
| Alucinação | LLMs inventam com cara confiável |
| Custo | GPT-4 ≈ US$ 100M para treinar |

---

## Viés Algorítmico

- Reconhecimento facial: **erro 34.7% maior** para mulheres de pele escura — Buolamwini & Gebru, 2018
- Amazon: algoritmo de recrutamento penalizava termos femininos

Mitigação: auditoria de dados · métricas de fairness · diversidade na equipe

---

## EU AI Act (2024)

| Risco | Exemplo | Requisito |
|:-----:|---------|----------|
| 🚫 Inaceitável | Scoring social | Proibido |
| 🔴 Alto | Diagnóstico médico | Transparência, auditoria |
| 🟡 Limitado | Chatbots | Informar que é IA |
| 🟢 Mínimo | Filtros de spam | Sem requisitos |

> Primeira legislação abrangente do mundo sobre IA.

---

## Referências

- Russell & Norvig (2021). *AI: A Modern Approach*, 4ª ed.
- Goodfellow et al. (2016). *Deep Learning*
- Buolamwini & Gebru (2018). *Gender Shades*
- Vaswani et al. (2017). *Attention Is All You Need*

**→ Checkpoint 04** · com módulo 08
