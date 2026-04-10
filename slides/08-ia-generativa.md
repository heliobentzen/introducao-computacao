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

## Módulo 08 · IA Generativa e Uso Responsável

**Prof. Hélio Bentzen**
IFPE · Análise e Desenvolvimento de Sistemas

---

# IA Generativa e Uso Responsável

---

## Como LLMs Funcionam

> Rede Transformer treinada em texto massivo para **prever o próximo token**.

- Não é busca em banco de dados
- Não "sabe" o que é verdade
- Gera texto que **parece** plausível

```
Pré-treino → Fine-tuning (RLHF) → Inferência (seu prompt)
```

---

## Pipeline de um LLM

```
┌─────────────────┐
│ 1. Pré-treino   │  Texto massivo → aprende padrões de linguagem
│ (self-supervised)│  Tarefa: prever próximo token
└────────┬────────┘
         ↓
┌─────────────────┐
│ 2. Fine-tuning  │  Dados curados → segue comandos
│   (RLHF / SFT)  │  Reforço com feedback humano
└────────┬────────┘
         ↓
┌─────────────────┐
│ 3. Inferência   │  Prompt → resposta token por token
└─────────────────┘
```

---

## Escala dos Modelos

| Modelo | Parâmetros | Ano |
|--------|:---------:|:---:|
| GPT-2 | 1.5 B | 2019 |
| GPT-3 | 175 B | 2020 |
| GPT-4 | >1 T (est.) | 2023 |
| LLaMA 3 | 8 B – 405 B | 2024 |

GPT-4 ≈ **US$ 100M** em computação para treinar.

---

## Custo e Impacto Ambiental

Treinar um LLM de ponta:

- Milhares de GPUs por semanas/meses
- GPT-4: ~US$ 100M em computação
- Emissão de CO₂ comparável a **voos transatlânticos**

**Usar** (inferência) é muito mais barato, mas em escala de bilhões de usuários...

> O custo ambiental da IA é tema de debate crescente.

---

## Tokenização

LLMs processam **tokens**, não palavras.

| Texto | Tokens |
|-------|--------|
| "Computação" | `["Comput", "ação"]` |
| "Hello world" | `["Hello", " world"]` |

- Palavras comuns = 1 token · Raras = vários
- Português usa **mais tokens** que inglês

---

## Tokens: Implicações Práticas

- **Limite de contexto:** modelo só "vê" N tokens por vez
  - GPT-4: ~128k tokens ≈ 200 páginas
- **Custo:** APIs cobram por token (input + output)
- **Idioma importa:** texto em inglês = menos tokens = mais barato e mais coerente
- **Emojis e símbolos:** cada um pode ser vários tokens

> Um prompt bem escrito é mais barato e gera respostas melhores.

---

## Alucinação: O Problema Central

> Modelo gera informação **incorreta com aparência confiável**.

| Caso | O que aconteceu |
|------|----------------|
| Mata v. Avianca (2023) | Advogados citaram casos que **não existiam** |
| Referências acadêmicas | DOIs e artigos **inventados** |
| Recomendações médicas | Plausíveis mas clinicamente erradas |

Causa: otimiza *coerência textual*, não *veracidade*.

---

## Engenharia de Prompt

| Componente | Função |
|:----------:|--------|
| **Role** | Persona do modelo |
| **Context** | Informação de fundo |
| **Task** | O que você quer |
| **Format** | Estrutura da resposta |
| **Constraints** | Limites e condições |

---

## Técnicas de Prompting

| Técnica | Descrição |
|---------|----------|
| **Zero-shot** | Pergunta direta |
| **Few-shot** | Fornece exemplos antes |
| **Chain-of-Thought** | Passo a passo (Wei, 2022) |
| **Self-consistency** | Múltiplas respostas → mais frequente |

---

## Prompt Ruim vs Bom

| Ruim | Melhor |
|---------|----------|
| "Me fala de cloud" | "Explique IaaS, PaaS, SaaS com exemplo para iniciante ADS" |
| "Faz um código bom" | "Função Python: lista de notas → média/max/min com validação" |
| "Tá certo isso?" | "Avalie esta definição de processo em SO: [def]. Corrija se necessário" |

---

## Framework FACT

Avalie **toda** resposta de IA:

| Letra | Pergunta-chave |
|:-----:|---------------|
| **F** | A informação é *verificável*? |
| **A** | Está *atualizada*? (data de corte) |
| **C** | Cobre o que foi *pedido*? |
| **T** | Terminologia *correta*? |

Red flags: confiança excessiva · citações desconhecidas · números perfeitos demais

---

## Regra Feynman p/ Aprender com IA

1. Estude o tema (com ou sem IA)
2. **Feche tudo** e explique com suas palavras
3. Travou? Volte ao material **naquele ponto**
4. Repita até explicar fluentemente

> Se não consegue explicar sem consultar, *não aprendeu*, apenas leu.

---

## Política de IA na Disciplina

| Uso | OK? |
|-----|:---:|
| Entender conceito | Sim |
| Gerar exercícios para praticar | Sim |
| Revisar seu texto/código | Sim (cite) |
| Submeter output como trabalho | Não (fraude) |
| Usar sem verificar | Atenção: Risco |

---

## Ecossistema de Ferramentas

| Categoria | Exemplos |
|-----------|---------|
| Chat LLM | ChatGPT, Claude, Gemini |
| Code | Copilot, Codeium, Cursor |
| Imagem | DALL-E, Midjourney, SD |
| Busca RAG | Perplexity, Gemini |
| Open source | LLaMA, Mistral, Phi |

---

## Síntese

A meta não é ser bom em **usar** IA.
É ser bom **com ou sem** IA.

> *A IA é uma ferramenta poderosa. Seu cérebro é insubstituível.*

**→ Checkpoint 04** · com módulo 07
