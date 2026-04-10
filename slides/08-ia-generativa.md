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

# ✨ IA Generativa e Uso Responsável

**Introdução à Computação · ADS**

*Entender a ferramenta · Verificar o resultado · Construir competência real*

![bg right:40% brightness:0.5](https://images.unsplash.com/photo-1684391962444-1048e55babfa?w=600&h=400&fit=crop)

---

## 🔮 Como LLMs Funcionam

> Rede Transformer treinada em texto massivo para **prever o próximo token**.

- ❌ Não é busca em banco de dados
- ❌ Não "sabe" o que é verdade
- ✅ Gera texto que **parece** plausível

```
Pré-treino → Fine-tuning (RLHF) → Inferência (seu prompt)
```

---

## 📏 Escala dos Modelos

| Modelo | Parâmetros | Ano |
|--------|:---------:|:---:|
| GPT-2 | 1.5 B | 2019 |
| GPT-3 | 175 B | 2020 |
| GPT-4 | >1 T (est.) | 2023 |
| LLaMA 3 | 8 B – 405 B | 2024 |

💸 GPT-4 ≈ **US$ 100M** em computação
🌍 Consumo de energia: debate crescente

---

## 🧩 Tokenização

LLMs processam **tokens**, não palavras.

| Texto | Tokens |
|-------|--------|
| "Computação" | `["Comput", "ação"]` |
| "Hello world" | `["Hello", " world"]` |

- Palavras comuns = 1 token
- Palavras raras = vários tokens
- 🇧🇷 Português usa **mais tokens** que inglês

---

## 👻 Alucinação — O Problema Central

> Modelo gera informação **incorreta com aparência confiável**.

| Caso | O que aconteceu |
|------|----------------|
| ⚖️ Mata v. Avianca (2023) | Advogados citaram casos que **não existiam** |
| 📖 Referências acadêmicas | DOIs e artigos **inventados** |
| 🏥 Recomendações médicas | Plausíveis mas clinicamente erradas |

**Causa:** otimiza *coerência textual*, não *veracidade*.

---

## 🎯 Engenharia de Prompt

| Componente | Função |
|:----------:|--------|
| 🎭 **Role** | Persona do modelo |
| 📋 **Context** | Informação de fundo |
| ✅ **Task** | O que você quer |
| 📐 **Format** | Estrutura da resposta |
| 🚫 **Constraints** | Limites e condições |

---

## 🧪 Técnicas de Prompting

| Técnica | Descrição |
|---------|----------|
| **Zero-shot** | Pergunta direta |
| **Few-shot** | Fornece exemplos antes |
| **Chain-of-Thought** | Passo a passo (Wei, 2022) |
| **Self-consistency** | Múltiplas respostas → mais frequente |

---

## ❌ Prompt Ruim vs ✅ Bom

| ❌ | ✅ |
|---|---|
| "Me fala de cloud" | "Explique IaaS, PaaS, SaaS com exemplo para iniciante ADS" |
| "Faz um código bom" | "Função Python: lista de notas → média/max/min com validação" |
| "Tá certo isso?" | "Avalie esta definição de processo em SO: [def]. Corrija se necessário" |

---

## ✅ Framework FACT

Avalie **toda** resposta de IA:

| Letra | Pergunta-chave |
|:-----:|---------------|
| **F** | A informação é *verificável*? |
| **A** | Está *atualizada*? (data de corte) |
| **C** | Cobre o que foi *pedido*? |
| **T** | Terminologia *correta*? |

🚩 **Red flags:** confiança excessiva · citações desconhecidas · números perfeitos demais

---

## 📖 Regra Feynman p/ Aprender com IA

1️⃣ Estude o tema (com ou sem IA)
2️⃣ **Feche tudo** e explique com suas palavras
3️⃣ Travou? Volte ao material **naquele ponto**
4️⃣ Repita até explicar fluentemente

> Se não consegue explicar sem consultar, **não aprendeu** — apenas leu.

---

## 📜 Política de IA na Disciplina

| Uso | OK? |
|-----|:---:|
| Entender conceito | ✅ |
| Gerar exercícios para praticar | ✅ |
| Revisar seu texto/código | ✅ (cite) |
| Submeter output como trabalho | ❌ Fraude |
| Usar sem verificar | ⚠️ Risco |

---

## 🧰 Ecossistema de Ferramentas

| Categoria | Exemplos |
|-----------|---------|
| 💬 Chat LLM | ChatGPT, Claude, Gemini |
| ✍️ Code | Copilot, Codeium, Cursor |
| 🖼️ Imagem | DALL-E, Midjourney, SD |
| 🔎 Busca RAG | Perplexity, Gemini |
| 🔓 Open source | LLaMA, Mistral, Phi |

---

## 🎯 Síntese

A meta não é ser bom em **usar** IA.
É ser bom **com ou sem** IA.

> *A IA é uma ferramenta poderosa. Seu cérebro é insubstituível.*

**→ Checkpoint 04** · com módulo 07

![bg right:30% opacity:0.15](https://images.unsplash.com/photo-1620712943543-bcc4688e7485?w=400&fit=crop)
