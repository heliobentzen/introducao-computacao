# Desafio 03 — IA com Cabeça: Uso Crítico de IA Generativa

> **Módulos cobertos:** 07 (Inteligência Artificial), 08 (IA Generativa Responsável)  
> **Tipo:** Individual  
> **Duração estimada:** 2–3 horas (fora de sala)  
> **Peso na avaliação:** desafio substitui nota de atividade regular

---

## Objetivo

Usar IA generativa como ferramenta de aprendizado para dominar um tema técnico da disciplina — sem terceirizar o entendimento. Ao final, você terá evidências concretas de que sabe avaliar, verificar e produzir conteúdo autoral com apoio de IA.

---

## Etapa 1 — Escolha do tema e pesquisa com IA (30 min)

### 1.1 Seleção

Escolha **um** tema dentre:

- Escalonamento de processos (Round Robin vs SJF).
- Hierarquia de memória e cache.
- Representação IEEE 754 de ponto flutuante.
- CAP Theorem em sistemas distribuídos.
- Backpropagation em redes neurais.
- Viés algorítmico em sistemas de ML.

### 1.2 Construção de prompts progressivos

Crie **4 prompts** para explorar o tema, um para cada técnica:

| # | Técnica | Prompt (cole o texto completo) | Modelo usado |
|---|---------|-------------------------------|-------------|
| 1 | Zero-shot | | |
| 2 | Few-shot (com 1-2 exemplos) | | |
| 3 | Chain-of-Thought | | |
| 4 | Role + Context + Format + Constraints | | |

### 1.3 Coleta de respostas

Para cada prompt, registre:

- Resposta completa do LLM (pode resumir se > 500 palavras).
- Tempo de resposta percebido.
- Primeira impressão: útil, vaga, incorreta, excelente?

---

## Etapa 2 — Avaliação crítica (30 min)

### 2.1 Framework FACT aplicado

Avalie **cada resposta** da Etapa 1:

| Prompt # | Factual (1-5) | Atualidade (1-5) | Completude (1-5) | Técnica (1-5) | Nota média |
|----------|--------------|-----------------|-----------------|--------------|-----------|
| 1 | | | | | |
| 2 | | | | | |
| 3 | | | | | |
| 4 | | | | | |

### 2.2 Identificação de erros

Para a **melhor resposta** (maior nota média), faça uma análise detalhada:

1. Liste **toda afirmação factual** (mínimo 5).
2. Verifique cada uma em **pelo menos 2 fontes confiáveis** (livro-texto, documentação oficial, artigo revisado por pares).
3. Preencha:

| Afirmação | Fonte 1 | Confirma? | Fonte 2 | Confirma? | Veredito |
|-----------|---------|----------|---------|----------|---------|
| | | | | | |

1. Calcule a **taxa de acerto** do LLM no seu tema.

### 2.3 Caça às alucinações (referências)

Peça ao LLM: *"Cite 5 referências acadêmicas sobre [seu tema] publicadas entre 2010 e 2024."*

Verifique cada uma no Google Scholar:

| # | Citação do LLM | Existe? | Dados corretos? | DOI funciona? |
|---|----------------|---------|-----------------|---------------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |

---

## Etapa 3 — Produção autoral (45 min)

### 3.1 Síntese crítica

Escreva um texto de **600–800 palavras** sobre o tema escolhido que:

- Demonstre compreensão real (não paráfrase de LLM).
- Inclua **pelo menos 1 exemplo numérico original** trabalhado por você.
- Contenha **pelo menos 1 analogia** criada por você.
- Cite **3 referências verificadas** (que você confirmou como reais na Etapa 2).
- Inclua **1 seção de limitações/controvérsias** do tema.
- Use terminologia técnica correta.

### 3.2 Meta-análise do processo

Escreva **200–300 palavras** analisando seu próprio processo:

1. Qual técnica de prompt gerou melhor resultado e por quê?
2. Que tipo de erro o LLM cometeu com mais frequência?
3. Quanto tempo a verificação levou comparado ao tempo de geração?
4. Em que o LLM foi genuinamente útil vs. onde atrapalhou?
5. Você teria aprendido mais ou menos sem usar IA? Justifique.

---

## Etapa 4 — Apresentação (opcional, para aula)

Prepare um **lightning talk de 5 minutos** contendo:

1. Tema escolhido (30 seg).
2. Melhor e pior prompt (1 min).
3. Alucinação mais surpreendente encontrada (1 min).
4. Insight principal do texto autoral (1.5 min).
5. Conselho para colegas sobre uso de IA (1 min).

---

## Critérios de Excelência

| Critério | Peso |
|----------|------|
| Qualidade e diversidade dos prompts | 15% |
| Rigor da avaliação FACT | 20% |
| Verificação de afirmações e referências | 20% |
| Qualidade do texto autoral | 25% |
| Meta-análise do processo | 15% |
| Organização e clareza do documento | 5% |

---

## Formato de entrega

- Repositório Git com README.
- Arquivo `desafio-03.md` com todas as etapas.
- Screenshots das verificações no Google Scholar.
- Indicação clara: modelo usado, versão, data de acesso.
- Seção final obrigatória: **"Antes e depois"** — sua visão sobre IA antes do desafio vs. depois, em 5-8 linhas.

---

## Regra de ouro

IA é estagiária incansável: trabalha rápido, nunca reclama e às vezes inventa dados com cara de quem leu o paper inteiro.

Seu trabalho é ser o orientador que verifica, questiona e assina embaixo.
