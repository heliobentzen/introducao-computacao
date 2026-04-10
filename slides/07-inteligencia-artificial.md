---
marp: true
theme: default
paginate: true
style: |
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

# 🤖 Inteligência Artificial

**Introdução à Computação · ADS**

*O que IA pode, o que não pode e o que importa saber*

![bg right:40% brightness:0.5](https://images.unsplash.com/photo-1677442136019-21780ecad995?w=600&h=400&fit=crop)

---

## 💡 O Que É IA?

> Sistema que percebe o ambiente e age para maximizar desempenho. — Russell & Norvig, 2021

| | Como humanos | Racionalmente |
|:-:|:---:|:---:|
| 🧠 **Pensando** | Ciência cognitiva | Lógica formal |
| 🏃 **Agindo** | Teste de Turing | **Agente racional** ← dominante |

---

## 📅 Cronologia Essencial

| Ano | Marco |
|:---:|-------|
| 1950 | 🧪 Turing — "Máquinas podem pensar?" |
| 1956 | 🏷️ Dartmouth — termo "AI" cunhado |
| 1997 | ♟️ Deep Blue vence Kasparov |
| 2012 | 👁️ AlexNet — DL domina visão |
| 2017 | ⚡ Transformer — *Attention Is All You Need* |
| 2020+ | 💬 GPT-3 → ChatGPT → GPT-4 → Gemini |

> ❄️ *Invernos da IA:* 1974–80 e 1987–93 (euforia → decepção → corte de verba)

---

## 🧬 Paradigmas de IA

| Paradigma | Como funciona | Exemplo |
|-----------|-------------|---------|
| 🔣 **Simbólica** | Regras IF-THEN | Sistemas especialistas |
| 📊 **Machine Learning** | Aprende dos dados | Detecção de spam |
| 🧠 **Deep Learning** | Redes neurais profundas | Reconhecimento de imagem |

---

## 📈 Tipos de Aprendizado

| Tipo | Dados | Exemplo |
|------|:-----:|---------|
| **Supervisionado** | Rotulados | Spam / não-spam |
| **Não supervisionado** | Sem rótulos | Segmentação de clientes |
| **Por reforço** | Recompensas | AlphaGo, robótica |

```
Dados → Pré-proc. → 🏋️ Treino → Modelo → ⚡ Inferência
  ↑                                              │
  └──────── Monitoramento + Retreino ←──────────┘
```

---

## 🏗️ Arquiteturas Deep Learning

| Arquitetura | Uso principal |
|:-----------:|-------------|
| **MLP** | Dados tabulares |
| **CNN** | 🖼️ Imagens, visão |
| **RNN / LSTM** | 📈 Séries temporais |
| **Transformer** | 🌐 NLP, visão, multimodal — domina tudo |

> **Backpropagation:** erro na saída é propagado de volta, ajustando pesos camada a camada.

---

## 🛠️ IA no Dev

| Aplicação | Ferramenta |
|-----------|-----------|
| ✍️ Code completion | Copilot, Codeium |
| 🔍 Code review | CodeQL, SonarQube |
| 🧪 Testes auto | Diffblue Cover |
| 💬 Chatbots | Dialogflow, Lex |
| 📊 AIOps | Datadog AI, New Relic |

---

## ⚠️ Limitações

| Limitação | Exemplo |
|-----------|--------|
| 📉 Dependência de dados | Dados enviesados → resultado enviesado |
| 🔗 Correlação ≠ causa | Sorvete ↔ afogamentos |
| 🔲 Caixa preta | Difícil explicar *por que* decidiu |
| 👻 Alucinação | LLMs inventam com cara confiável |
| 💸 Custo | GPT-4 ≈ US$ 100M para treinar |

---

## ⚖️ Viés Algorítmico

- 👁️ Reconhecimento facial: **erro 34.7% maior** para mulheres de pele escura — Buolamwini & Gebru, 2018
- 💼 Amazon: algoritmo de recrutamento penalizava termos femininos

**Mitigação:** auditoria de dados · métricas de fairness · diversidade na equipe

---

## 🇪🇺 EU AI Act (2024)

| Risco | Exemplo | Requisito |
|:-----:|---------|----------|
| 🚫 Inaceitável | Scoring social | Proibido |
| 🔴 Alto | Diagnóstico médico | Transparência, auditoria |
| 🟡 Limitado | Chatbots | Informar que é IA |
| 🟢 Mínimo | Filtros de spam | Sem requisitos |

> Primeira legislação abrangente do mundo sobre IA.

---

## 📚 Referências

- Russell & Norvig (2021). *AI: A Modern Approach*, 4ª ed.
- Goodfellow et al. (2016). *Deep Learning*
- Buolamwini & Gebru (2018). *Gender Shades*
- Vaswani et al. (2017). *Attention Is All You Need*

**→ Checkpoint 04** · com módulo 08
