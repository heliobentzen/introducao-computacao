# Checkpoint 04 — Inteligência Artificial e IA Generativa Responsável

> **Módulos de referência:** [07 — Inteligência Artificial](../../conteudo/07-inteligencia-artificial.md) e [08 — IA Generativa](../../conteudo/08-ia-generativa-responsavel.md)  
> **Duração estimada:** 45–60 min  
> **Entrega:** repositório Git com resoluções + evidências de verificação

---

## Parte A — Fundamentos de IA (20 min)

### A1. Taxonomia de IA

Classifique cada cenário no paradigma correto e justifique em 1 linha:

| Cenário | IA Simbólica / ML Supervisionado / ML Não Supervisionado / ML por Reforço / Deep Learning |
|---------|---|
| Sistema de recomendação da Netflix que agrupa filmes por similaridade sem rótulos | |
| Chatbot bancário que segue árvore de decisão fixa com regras IF-THEN | |
| Filtro de spam treinado com 1 milhão de e-mails rotulados spam/não-spam | |
| AlphaGo aprendendo a jogar Go por tentativa e erro contra si mesmo | |
| CNN que classifica radiografias como "normal" ou "pneumonia" | |
| Sistema especialista de diagnóstico automotivo com base de regras | |

### A2. Ciclo de Machine Learning

Desenhe (diagrama, Mermaid ou à mão) o ciclo completo de ML para o seguinte cenário:

> Uma fintech quer prever quais clientes têm alta probabilidade de inadimplência.

Inclua e descreva cada etapa:

1. **Coleta de dados** — quais dados usar? (cite 5 features relevantes)
2. **Pré-processamento** — que limpeza/transformação é necessária?
3. **Divisão** — proporção treino/validação/teste sugerida e por quê.
4. **Treinamento** — que tipo de algoritmo é adequado? (justifique)
5. **Avaliação** — que métrica usar? (acurácia basta? por que sim/não?)
6. **Deploy** — como o modelo chega à produção?
7. **Monitoramento** — o que pode degradar o modelo ao longo do tempo?

### A3. Limitações e viés

1. Explique o conceito de **viés algorítmico** com o exemplo de Buolamwini & Gebru (2018) sobre reconhecimento facial.
2. Dê um exemplo **hipotético mas realista** de viés que poderia ocorrer no cenário da fintech (A2).
3. Proponha **3 medidas concretas** para mitigar esse viés.
4. Classifique o sistema da fintech na escala de risco do **EU AI Act** e justifique qual nível se aplica.

---

## Parte B — IA Generativa e Uso Responsável (25 min)

### B1. Engenharia de prompt — Prática comparativa

Escolha o conceito **"escalonamento de processos Round Robin"** (módulo 05) e construa:

| Técnica | Seu prompt | Avaliação da resposta (1-5) | Justificativa |
|---------|-----------|---------------------------|-------------|
| Zero-shot | | | |
| Few-shot (forneça 1 exemplo antes) | | | |
| Chain-of-Thought | | | |
| Role + Context + Format | | | |

Para cada prompt, cole a **resposta do LLM** (resumida em até 10 linhas) e avalie usando o framework FACT:

- **F**actual — A informação está correta?
- **A**tualidade — Está atualizado?
- **C**ompletude — Cobre o que foi pedido?
- **T**écnica — Terminologia correta?

### B2. Caça às alucinações

1. Peça a um LLM: *"Cite 5 artigos acadêmicos sobre arquitetura de Von Neumann publicados entre 2010 e 2024, incluindo autores, ano e DOI."*
2. Verifique **cada referência** no Google Scholar ou CrossRef.
3. Preencha:

| # | Referência citada pelo LLM | Existe? | Autores OK? | Ano OK? | DOI válido? |
|---|---------------------------|---------|-------------|---------|-------------|
| 1 | | | | | |
| 2 | | | | | |
| 3 | | | | | |
| 4 | | | | | |
| 5 | | | | | |

1. Calcule a **taxa de alucinação** (% de referências parcial ou totalmente inventadas).
2. Escreva 5 linhas de análise: o que isso ensina sobre confiar em LLMs para citações?

### B3. Produção autoral com apoio de IA

1. Peça a um LLM: *"Explique a diferença entre IaaS, PaaS e SaaS em 200 palavras, com exemplos."*
2. Avalie a resposta com o framework FACT.
3. Identifique **pelo menos 2 imprecisões ou lacunas**.
4. **Reescreva** o texto com suas próprias palavras (300-400 palavras), corrigindo problemas e adicionando:
   - 1 exemplo brasileiro (empresa ou serviço).
   - 1 conexão com outro módulo da disciplina.
   - 1 referência verificada.

### B4. Reflexão sobre integridade

Responda em 10-15 linhas:

1. Em que situações usar IA generativa para estudar **ajuda genuinamente** o aprendizado?
2. Em que situações o uso se torna **contraproducente ou desonesto**?
3. Onde está a linha entre **ferramenta de apoio** e **terceirização de entendimento**?
4. Qual é sua posição pessoal sobre o uso de IA em avaliações acadêmicas?

---

## Critérios de Avaliação

| Critério | Peso | Excelente | Suficiente | Insuficiente |
|----------|------|-----------|------------|-------------|
| Taxonomia e ciclo ML | 25% | Classificações corretas com justificativa, ciclo completo | Classificações corretas, ciclo parcial | Erros conceituais |
| Viés e ética | 15% | Exemplo realista, medidas concretas, EU AI Act correto | Exemplo e medidas presentes | Superficial ou ausente |
| Prompt engineering | 25% | 4 prompts com avaliação FACT detalhada | 3 prompts com avaliação | Menos de 3 ou sem avaliação |
| Verificação de alucinações | 20% | 5 referências verificadas com taxa calculada | 3+ verificadas | Sem verificação |
| Produção autoral + reflexão | 15% | Texto reescrito com qualidade, reflexão profunda | Texto presente, reflexão básica | Cópia ou ausente |

---

## Entrega

1. Arquivo `checkpoint-04.md` com todas as partes.
2. Screenshots ou links das verificações no Google Scholar.
3. Indicação clara de qual LLM foi usado (modelo, versão, data de acesso).
4. Seção final obrigatória: **"O que mudou na minha visão sobre IA"** — antes e depois de fazer este checkpoint, em 5-8 linhas.
