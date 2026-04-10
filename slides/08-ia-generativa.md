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

# 08 — IA Generativa e Uso Responsável

**Introdução à Computação — ADS**
Entender a ferramenta. Verificar o resultado. Construir competência real.

---

## Como LLMs Funcionam

> Rede neural Transformer treinada em texto massivo para **prever o próximo token**.

Não é busca em banco de dados.
Não "sabe" o que é verdade.
Gera texto que **parece** plausível.

```
Pré-treino (self-supervised)
    → Fine-tuning (RLHF)
        → Inferência (seu prompt)
```

---

## Escala dos Modelos

| Modelo | Parâmetros | Ano |
|--------|-----------|-----|
| GPT-2 | 1.5 bilhão | 2019 |
| GPT-3 | 175 bilhões | 2020 |
| GPT-4 | >1 trilhão (estimado) | 2023 |
| LLaMA 3 | 8B–405B | 2024 |

**Custo:** GPT-4 ≈ US$ 100M em computação para treinar.
**Impacto ambiental:** consumo de energia é debate crescente.

---

## Tokenização

LLMs não processam palavras — processam **tokens** (pedaços de texto).

| Texto | Tokens |
|-------|--------|
| "Computação" | ["Comput", "ação"] |
| "Hello world" | ["Hello", " world"] |

Palavras comuns = 1 token. Palavras raras = vários tokens.
Português geralmente usa **mais tokens** que inglês para o mesmo conteúdo.

---

## Alucinação — O Problema Central

> Modelo gera informação **factualmente incorreta com aparência confiável**.

**Casos reais:**

- Advogados citaram casos jurídicos que **não existiam** (Mata v. Avianca, 2023)
- Referências bibliográficas inventadas com DOI fictício
- Recomendações médicas plausíveis mas clinicamente incorretas

**Causa:** otimiza **coerência textual**, não **veracidade**.

---

## Engenharia de Prompt

| Componente | Função |
|-----------|--------|
| **Role** | Persona do modelo |
| **Context** | Informação de fundo |
| **Task** | O que você quer |
| **Format** | Estrutura da resposta |
| **Constraints** | Limites e condições |

---

## Técnicas de Prompting

| Técnica | Descrição |
|---------|----------|
| **Zero-shot** | Pergunta direta, sem exemplos |
| **Few-shot** | Fornece exemplos antes (Brown et al., 2020) |
| **Chain-of-Thought** | Pede raciocínio passo a passo (Wei et al., 2022) |
| **Self-consistency** | Gera múltiplas respostas, seleciona mais frequente |
| **Tree of Thoughts** | Explora múltiplos caminhos de raciocínio |

---

## Prompt Ruim vs. Bom

| ❌ Ruim | ✅ Melhor |
|---------|----------|
| "Me fala de cloud" | "Explique IaaS, PaaS e SaaS com exemplo prático cada, para iniciante de ADS" |
| "Faz um código bom" | "Função Python: recebe lista de notas, retorna média/max/min com validação" |
| "Tá certo isso?" | "Avalie esta definição de processo em SO: [definição]. Está correto? Se não, corrija" |

---

## Framework FACT

Avalie toda resposta de IA:

| Critério | Pergunta |
|----------|---------|
| **F**actual | A informação é verídica e verificável? |
| **A**tualidade | Está atualizado? (data de corte) |
| **C**ompletude | Cobre o que foi pedido? |
| **T**écnica | Terminologia correta? |

**Red flags:** confiança excessiva, citações desconhecidas, números "perfeitos demais".

---

## IA no Aprendizado — Regra Feynman

1. Estude o tema (com ou sem IA)
2. **Feche tudo** e explique com suas palavras
3. Travou? Volte ao material **naquele ponto**
4. Repita até explicar fluentemente

> Se não consegue explicar sem consultar a resposta, não aprendeu — apenas leu.

---

## Política de IA na Disciplina

| Uso | OK? |
|-----|-----|
| Entender conceito | ✅ Sim |
| Gerar exercícios para praticar | ✅ Sim |
| Revisar seu texto/código | ✅ Sim (cite) |
| Submeter output como trabalho | ❌ Fraude |
| Usar sem verificar informações | ⚠️ Risco |

**Sempre citar** quando IA contribuiu significativamente.

---

## Ecossistema de Ferramentas

| Categoria | Exemplos |
|-----------|---------|
| Chat LLM | ChatGPT, Claude, Gemini |
| Code assistant | Copilot, Codeium, Cursor |
| Imagem | DALL-E, Midjourney, Stable Diffusion |
| Busca com RAG | Perplexity, Gemini grounded |
| Open source | LLaMA, Mistral, Phi (Ollama) |

---

## Referências-chave

- Vaswani et al. (2017). Attention Is All You Need
- Brown et al. (2020). Language Models Are Few-Shot Learners
- Wei et al. (2022). Chain-of-Thought Prompting
- Ouyang et al. (2022). Training LMs with Human Feedback
- Bender et al. (2021). On the Dangers of Stochastic Parrots

---

## Síntese

A meta não é que você seja bom em usar IA.
É que você seja bom **com ou sem** IA.

**→ Checkpoint 04** (com módulo 07)
Prompt engineering comparativo, caça às alucinações, produção autoral verificada.
