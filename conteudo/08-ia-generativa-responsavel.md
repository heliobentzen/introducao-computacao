# 08 — IA Generativa: Fundamentos, Uso Responsável e Engenharia de Prompt

## Objetivos de aprendizagem

Ao final deste módulo o estudante será capaz de:

- Explicar como Large Language Models (LLMs) funcionam em nível conceitual.
- Construir prompts eficientes usando técnicas estruturadas.
- Avaliar criticamente respostas de IA generativa com método verificável.
- Aplicar IA generativa como ferramenta de aprendizado e produtividade sem dependência cega.
- Compreender as implicações de autoria, integridade acadêmica e uso profissional.

---

## 1. O Que São Large Language Models?

### 1.1 Definição Técnica

Um LLM (Large Language Model) é uma rede neural baseada na arquitetura **Transformer** (Vaswani et al., 2017), treinada em volumes massivos de texto para prever a próxima sequência de tokens. Em termos simplificados:

> Dado o contexto "O gato sentou no ___", o modelo calcula a probabilidade de cada possível próxima palavra e seleciona a mais provável (ou amostra com temperatura).

**Não é busca em banco de dados.** O modelo não "consulta" a internet em tempo real (a menos que tenha ferramentas de busca acopladas). Ele gera texto baseado em **padrões estatísticos** aprendidos durante o treinamento.

### 1.2 Escala e Treinamento

| Modelo | Parâmetros | Dados de treino | Ano |
|--------|-----------|----------------|-----|
| GPT-2 | 1.5 bilhão | ~40 GB de texto | 2019 |
| GPT-3 | 175 bilhões | ~570 GB | 2020 |
| GPT-4 | Não divulgado (estimado >1 trilhão) | Multimodal (texto + imagem) | 2023 |
| LLaMA 3 | 8B - 405B | ~15 trilhões de tokens | 2024 |
| Gemini Ultra | Não divulgado | Multimodal | 2024 |

**O custo:**  treinar um modelo de ponta exige milhares de GPUs por semanas/meses. O GPT-4 custou estimados US$ 100 milhões em computação. O impacto ambiental (consumo de energia, emissão de CO₂) é tema de debate crescente (Strubell, Ganesh & McCallum, 2019).

### 1.3 O Pipeline Completo (Simplificado)

```
┌─────────────────┐
│ 1. Pré-treino   │  Texto massivo da internet → modelo aprende padrões de linguagem
│ (self-supervised)│  Tarefa: prever próximo token
└────────┬────────┘
         ↓
┌─────────────────┐
│ 2. Fine-tuning  │  Dados curados + instruções → modelo aprende a seguir comandos
│   (RLHF / SFT)  │  Reforço com feedback humano
└────────┬────────┘
         ↓
┌─────────────────┐
│ 3. Inferência   │  Usuário envia prompt → modelo gera resposta token por token
│   (deploy)      │
└─────────────────┘
```

**RLHF (Reinforcement Learning from Human Feedback):** após o pré-treino, humanos avaliam respostas do modelo e esse feedback é usado para ajustar o comportamento — tornando-o mais útil, menos tóxico e mais alinhado com instruções (Ouyang et al., 2022).

### 1.4 Tokenização

LLMs não processam palavras inteiras — processam **tokens**, que são pedaços de texto (subpalavras). O algoritmo BPE (Byte Pair Encoding) é o mais comum:

| Texto | Tokens (aproximado) |
|-------|-------------------|
| "Computação" | ["Comput", "ação"] |
| "Hello world" | ["Hello", " world"] |
| "😀" | [token especial para emoji] |

Palavras comuns viram um token. Palavras raras ou de outros idiomas podem ser divididas em vários tokens — por isso respostas em português às vezes são levemente menos precisas: o modelo "viu" menos texto em português durante o treino.

---

## 2. Alucinação — O Problema Central

### 2.1 O Que É Alucinação em LLMs

Alucinação é quando o modelo gera informação **factualmente incorreta com aparência confiável**. Isso acontece porque o modelo otimiza **coerência textual**, não **veracidade**. Ele não "sabe" o que é verdade — ele gera texto que *parece* plausível.

**Exemplos reais documentados:**

- Advogados usaram ChatGPT para pesquisa jurídica e citaram casos que **não existiam** (Mata v. Avianca, 2023 — os advogados foram multados pelo juiz).
- Respostas médicas com recomendações plausíveis mas clinicamente incorretas.
- Referências bibliográficas inventadas com DOI, ano e autores fictícios.

### 2.2 Por Que Acontece

| Causa | Explicação |
|-------|-----------|
| Treinamento probabilístico | O modelo aprendeu que certo formato de resposta é provável, não que é verdadeiro |
| Distribuição vs. factos | Sequências plausíveis na distribuição de treino não garantem correção factual |
| Falta de grounding | Sem acesso a fontes verificáveis em tempo real, o modelo "completa" lacunas |
| Prompt ambíguo | Perguntas vagas aumentam a margem para completação criativa (= inventada) |

### 2.3 Como Mitigar

1. **Verificar toda informação factual** com fontes primárias.
2. **Usar RAG** (Retrieval-Augmented Generation) — o modelo consulta base de conhecimento antes de responder.
3. **Pedir citações** e verificá-las manualmente.
4. **Aumentar especificidade** do prompt — menos ambiguidade = menos espaço para alucinação.
5. **Comparar respostas** entre modelos diferentes e com fontes tradicionais.

---

## 3. Engenharia de Prompt — Técnicas Estruturadas

Prompt engineering é a disciplina de construir instruções que maximizam a qualidade e relevância das respostas de LLMs.

### 3.1 Anatomia de um Bom Prompt

| Componente | Função | Exemplo |
|-----------|--------|---------|
| **Papel (Role)** | Define a persona do modelo | "Você é um professor de Ciência da Computação especializado em algoritmos" |
| **Contexto** | Informação de fundo relevante | "Estou no 1º período de ADS e estudando pensamento computacional" |
| **Tarefa** | O que exatamente você quer | "Explique decomposição com um exemplo de sistema de entregas" |
| **Formato** | Como a resposta deve ser estruturada | "Responda em 5 tópicos numerados, cada um com no máximo 3 linhas" |
| **Restrições** | Limites e condições | "Não use jargão avançado. Inclua analogia com cotidiano" |

### 3.2 Técnicas Avançadas de Prompting

**Zero-shot:** pergunta direta, sem exemplos.

```
Classifique o sentimento do texto: "O atendimento foi péssimo"
```

**Few-shot:** fornecer exemplos antes da pergunta (Brown et al., 2020).

```
Classifique o sentimento:
"Adorei o produto" → Positivo
"Entrega atrasou muito" → Negativo
"Chegou no prazo" → Positivo
"O atendimento foi péssimo" → ???
```

**Chain-of-Thought (CoT):** pedir que o modelo raciocine passo a passo antes de responder (Wei et al., 2022).

```
Resolva passo a passo: Se um servidor processa 100 requisições por segundo
e recebe 1.000 requisições simultâneas, qual o tempo mínimo de atendimento?
Mostre cada etapa do raciocínio.
```

**Self-consistency:** gerar múltiplas respostas com CoT e selecionar a mais frequente (Wang et al., 2022).

**Tree of Thoughts:** explorar múltiplos caminhos de raciocínio e avaliar qual é mais promissor (Yao et al., 2023).

### 3.3 Prompt Ruim vs. Prompt Bom

| Prompt ruim | Problema | Prompt melhorado |
|------------|---------|-----------------|
| "Me fala de cloud" | Vago, sem escopo | "Explique os 3 modelos de serviço cloud (IaaS, PaaS, SaaS) com um exemplo prático de cada, para um aluno iniciante de ADS" |
| "Faz um código bom" | Sem especificação | "Escreva uma função em Python que recebe uma lista de notas (0 a 10) e retorna a média, a maior e a menor nota. Inclua validação de entrada e testes" |
| "Tá certo isso?" | Sem contexto | "Avalie esta definição de processo em SO: [definição]. Está tecnicamente correta? Se não, indique o erro e a correção" |

---

## 4. Avaliação Crítica de Respostas

### 4.1 Framework FACT

Checklist para avaliar qualquer resposta de IA:

| Critério | Pergunta | Ação se falhar |
|----------|---------|---------------|
| **F**actual | A informação é verídica e verificável? | Consultar fonte primária |
| **A**tualidade | A informação está atualizada? (dados de treino têm data de corte) | Verificar timeline |
| **C**ompletude | A resposta cobre o que foi pedido por inteiro? | Reformular prompt com mais especificidade |
| **T**écnica | A terminologia e os conceitos estão corretos? | Cruzar com livro-texto ou documentação oficial |

### 4.2 Sinais de Alerta (Red Flags)

- Resposta excessivamente confiante em tema controverso.
- Citações bibliográficas com formato perfeito mas autores/títulos desconhecidos.
- Números muito redondos ou "convenientes demais" em estatísticas.
- Contradição interna entre parágrafos da mesma resposta.
- Resposta que não reconhece limitações ou incertezas.

### 4.3 Prática de Verificação

**Exercício estruturado:**

1. Peça a um LLM: "Liste 5 artigos acadêmicos sobre pensamento computacional publicados entre 2010 e 2024."
2. Para cada artigo citado, verifique no Google Scholar se:
   - O artigo existe.
   - Os autores estão corretos.
   - O ano está correto.
   - O DOI funciona.
3. Registre a taxa de acerto. Esse exercício costuma revelar 30-60% de alucinações em citações não verificadas.

---

## 5. IA Generativa no Aprendizado

### 5.1 Usos Produtivos para Estudantes

| Uso | Como fazer certo | Armadilha |
|-----|-----------------|-----------|
| **Explicar conceito** | Pedir explicação + analogia + contra-exemplo | Aceitar sem verificar |
| **Gerar exercícios** | Pedir problemas com gabarito para praticar | Praticar sem entender |
| **Revisar código** | Colar código e pedir análise de bugs/melhorias | Copiar sugestão sem compreender |
| **Resumir texto** | Pedir resumo estruturado de material longo | Usar resumo como substituto do original |
| **Praticar inglês técnico** | Pedir tradução/explicação de documentação | Ignorar nuances e contexto |

### 5.2 A Regra do "Explica Pra Mim"

**Depois de usar IA para estudar um tema, você deve ser capaz de explicá-lo para outra pessoa sem consultar a resposta.** Se não consegue, não aprendeu — apenas leu.

Técnica de estudo Feynman adaptada para a era da IA:

1. Estude o tema (com ou sem IA).
2. Feche tudo e explique em voz alta (ou por escrito) com suas palavras.
3. Identifique onde travou.
4. Volte ao material **naquele ponto específico**.
5. Repita até conseguir explicar fluentemente.

### 5.3 Integridade Acadêmica

**Política desta disciplina:**

- IA pode ser usada como **ferramenta de apoio** ao estudo e prototipação.
- IA **não substitui** entendimento — entregas devem refletir autoria e compreensão.
- **Citar o uso de IA** quando ela contribuiu significativamente para a elaboração.
- Apresentar resposta de IA como produção própria sem entendimento é **fraude acadêmica**.

Universidades como MIT, Stanford e USP já publicaram diretrizes específicas. O consenso é: transparência no uso, responsabilidade no resultado.

---

## 6. IA Generativa no Contexto Profissional

### 6.1 Produtividade Real vs. Ilusória

Pesquisa da McKinsey (2023) indica que desenvolvedores usando Copilot completam tarefas **30-55% mais rápido** em cenários controlados. Porém:

- A aceleração é maior em **código boilerplate** e tarefas repetitivas.
- Em **lógica complexa e arquitetura**, o ganho é menor e o risco de erros sutis aumenta.
- Desenvolvedores juniores tendem a aceitar sugestões incorretas com mais frequência que seniores.

### 6.2 Quando NÃO Usar IA Generativa

| Cenário | Risco |
|---------|------|
| Código de segurança crítica | Vulnerabilidades sutis geradas pelo modelo |
| Decisões médicas ou jurídicas | Alucinação com consequências graves |
| Dados confidenciais no prompt | Vazamento de informação proprietária |
| Substituir aprendizado fundamental | Ilusão de competência — o mercado testa de verdade |

---

## 7. Ferramentas do Ecossistema (Mapa Atual)

| Categoria | Ferramentas | Acesso |
|-----------|-----------|--------|
| Assistentes de chat | ChatGPT, Claude, Gemini, Perplexity | Web, API |
| Code assistants | GitHub Copilot, Codeium, Cursor, Amazon Q | IDE (VS Code, JetBrains) |
| Geração de imagem | DALL-E, Midjourney, Stable Diffusion | Web, API, local |
| Áudio/Voz | Whisper (transcrição), ElevenLabs (síntese) | API |
| Busca aumentada (RAG) | Perplexity, Gemini com grounding, Bing Chat | Web |
| Open source | LLaMA, Mistral, Phi, Gemma | Hugging Face, Ollama (local) |

---

## 8. Atividade Prática — Progressão em 3 Níveis

### Nível 1 — Prompt engineering básico (10 min)

Construa 3 prompts para aprender o conceito de **paginação de memória** (módulo 05):

1. Prompt zero-shot simples.
2. Prompt com role + contexto + formato.
3. Prompt com chain-of-thought.

Compare as 3 respostas em qualidade, profundidade e clareza. Qual técnica produziu melhor resultado?

### Nível 2 — Verificação e curadoria (20 min)

1. Peça a um LLM: "Sugira 5 referências bibliográficas sobre arquitetura de Von Neumann publicadas entre 2000 e 2024."
2. Verifique cada referência no Google Scholar.
3. Monte uma tabela:

| Referência citada | Existe? | Autores corretos? | Ano correto? | DOI válido? |
|-------------------|---------|-------------------|-------------|-------------|

1. Escreva uma análise de 10 linhas sobre a confiabilidade de citações geradas por IA.

### Nível 3 — Produção autoral com apoio de IA (25 min)

1. Peça a um LLM que gere um resumo de 300 palavras sobre **representação de ponto flutuante IEEE 754**.
2. Avalie a resposta usando o framework FACT (seção 4.1).
3. Identifique pelo menos 2 imprecisões ou lacunas.
4. Reescreva o texto **com suas próprias palavras**, corrigindo os problemas encontrados e adicionando pelo menos 1 exemplo numérico original.
5. O texto final deve ter entre 400-500 palavras e demonstrar compreensão real, não paráfrase cosmética.

---

## 9. Síntese

IA generativa é a ferramenta mais poderosa — e mais perigosa — que já chegou às mãos de estudantes e profissionais de tecnologia. Poderosa porque acelera aprendizado, prototipação e produção. Perigosa porque cria a **ilusão de competência** em quem não verifica, não questiona e não entende o que recebe. O profissional que vai se destacar não é o que gera mais prompts por dia — é o que sabe avaliar criticamente os resultados e construir conhecimento real por cima deles.

A meta desta disciplina não é que você seja bom em usar IA. É que você seja bom **com ou sem** IA.

---

## Referências

- BROWN, Tom B. et al. Language models are few-shot learners. *NeurIPS*, 2020. Disponível em: <https://arxiv.org/abs/2005.14165>
- OUYANG, Long et al. Training language models to follow instructions with human feedback. *NeurIPS*, 2022. Disponível em: <https://arxiv.org/abs/2203.02155>
- STRUBELL, Emma; GANESH, Ananya; MCCALLUM, Andrew. Energy and policy considerations for deep learning in NLP. *Proceedings of ACL*, 2019. Disponível em: <https://doi.org/10.18653/v1/P19-1355>
- VASWANI, Ashish et al. Attention is all you need. *NeurIPS*, 2017. Disponível em: <https://arxiv.org/abs/1706.03762>
- WANG, Xuezhi et al. Self-consistency improves chain of thought reasoning in language models. *ICLR*, 2023. Disponível em: <https://arxiv.org/abs/2203.11171>
- WEI, Jason et al. Chain-of-thought prompting elicits reasoning in large language models. *NeurIPS*, 2022. Disponível em: <https://arxiv.org/abs/2201.11903>
- YAO, Shunyu et al. Tree of thoughts: deliberate problem solving with large language models. *NeurIPS*, 2023. Disponível em: <https://arxiv.org/abs/2305.10601>
- MCKINSEY & COMPANY. *The economic potential of generative AI*. 2023. Disponível em: <https://www.mckinsey.com/capabilities/mckinsey-digital/our-insights/the-economic-potential-of-generative-ai-the-next-productivity-frontier>
- MIT. *Guidelines for AI in education*. 2023. Disponível em: <https://genai.mit.edu/>
- RUSSELL, Stuart; NORVIG, Peter. *Artificial Intelligence: A Modern Approach*. 4. ed. Pearson, 2021.
- BOMMASANI, Rishi et al. On the opportunities and risks of foundation models. *Stanford CRFM*, 2021. Disponível em: <https://arxiv.org/abs/2108.07258>
