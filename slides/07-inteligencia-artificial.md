---
marp: true
theme: default
paginate: true
backgroundColor: #1a1a2e
color: #eaeaea
style: |
  section { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
  h1 { color: #e94560; }
  h2 { color: #fff; background: #e94560; padding: 4px 16px; border-radius: 4px; }
  table { font-size: 0.78em; }
  code { background: #16213e; color: #e94560; }
  a { color: #00d2ff; }
  blockquote { border-left: 4px solid #e94560; color: #ccc; }
---

# 07 — Inteligência Artificial

**Introdução à Computação — ADS**
O que IA pode, o que não pode e o que importa saber.

---

## O Que É IA?

> Sistema que percebe o ambiente e toma ações que maximizam alguma medida de desempenho. — Russell & Norvig (2021)

**4 abordagens históricas:**

| | Como humanos | Racionalmente |
|---|---|---|
| **Pensando** | Ciência cognitiva | Lógica formal |
| **Agindo** | Teste de Turing | **Agente racional** ← dominante |

---

## Cronologia Essencial

| Ano | Marco |
|-----|-------|
| 1950 | Turing — "As máquinas podem pensar?" |
| 1956 | Dartmouth — termo "AI" é cunhado |
| 1986 | Backpropagation (Rumelhart, Hinton, Williams) |
| 1997 | Deep Blue vence Kasparov (xadrez) |
| 2012 | AlexNet — Deep Learning domina visão |
| 2017 | Transformer — "Attention is All You Need" |
| 2020+ | GPT-3, ChatGPT, GPT-4, Gemini |

**Invernos da IA:** 1974–80 e 1987–93 (euforia → decepção → corte de verba).

---

## Paradigmas de IA

| Paradigma | Como funciona | Exemplo |
|-----------|-------------|---------|
| **IA Simbólica** | Regras explícitas IF-THEN | Sistemas especialistas |
| **Machine Learning** | Aprende padrões dos dados | Classificação de spam |
| **Deep Learning** | Redes neurais profundas | Reconhecimento de imagem |

---

## Tipos de Aprendizado de Máquina

| Tipo | Dados | Objetivo | Exemplo |
|------|-------|---------|---------|
| **Supervisionado** | Rotulados (entrada + saída) | Prever rótulo | Spam / não-spam |
| **Não supervisionado** | Sem rótulos | Encontrar estrutura | Segmentação de clientes |
| **Por reforço** | Recompensas/punições | Aprender política | AlphaGo, robótica |

---

## Ciclo de Machine Learning

```
Dados → Pré-processamento → Treinamento → Modelo → Inferência
  ↑                                                      |
  └──────────── Monitoramento + Retreino ←───────────────┘
```

**Conceitos-chave:**

- **Feature:** variável de entrada
- **Label:** saída esperada (supervisionado)
- **Overfitting:** decorou os dados, falha com novos
- **Underfitting:** simples demais, não captura padrões

---

## Deep Learning — Arquiteturas

| Arquitetura | Uso principal |
|------------|-------------|
| **MLP** | Classificação tabular |
| **CNN** | Imagens, visão computacional |
| **RNN / LSTM** | Séries temporais, texto |
| **Transformer** | NLP, visão, multimodal — domina tudo |

**Backpropagation:** erro na saída é propagado de volta, ajustando pesos camada por camada.

---

## IA no Desenvolvimento de Software

| Aplicação | Ferramenta |
|-----------|-----------|
| Code completion | GitHub Copilot, Codeium |
| Code review | CodeQL, SonarQube |
| Testes automatizados | Diffblue Cover |
| Chatbots | Dialogflow, Amazon Lex |
| AIOps | Datadog AI, New Relic |

---

## Limitações Fundamentais

| Limitação | Exemplo |
|-----------|--------|
| **Dependência de dados** | Dados enviesados → resultado enviesado |
| **Correlação ≠ causa** | Sorvete ↔ afogamentos |
| **Caixa preta** | Difícil explicar *por que* decidiu |
| **Adversarial examples** | Adesivo em placa engana visão |
| **Alucinação** | LLMs inventam com cara confiável |
| **Custo** | GPT-4: ~US$ 100M para treinar |

---

## Viés Algorítmico

- Reconhecimento facial: erro 34.7% maior para mulheres de pele escura (Buolamwini & Gebru, 2018)
- Recrutamento: algoritmo da Amazon penalizava termos femininos
- **Mitigação:** auditoria de dados, métricas de fairness, diversidade na equipe

---

## EU AI Act (2024)

| Nível de risco | Exemplo | Requisitos |
|---------------|---------|-----------|
| Inaceitável | Scoring social | Proibido |
| Alto | Diagnóstico médico | Transparência, auditoria |
| Limitado | Chatbots | Informar que é IA |
| Mínimo | Filtros de spam | Sem requisitos |

Primeira legislação abrangente do mundo sobre IA.

---

## Referências-chave

- Russell & Norvig (2021). *AI: A Modern Approach* (4ª ed.)
- Goodfellow, Bengio & Courville (2016). *Deep Learning*
- Buolamwini & Gebru (2018). Gender Shades
- Vaswani et al. (2017). Attention Is All You Need

---

## Checkpoint

**→ Checkpoint 04** (com módulo 08)
Taxonomia de IA, ciclo ML, viés, prompt engineering, verificação de alucinações.
