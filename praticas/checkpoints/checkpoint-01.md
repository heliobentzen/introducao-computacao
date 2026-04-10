---
marp: true
---

# Checkpoint 01 — Pensamento Computacional e Lógica de Algoritmos

> **Módulos de referência:** [01 — Pensamento Computacional](../../conteudo/01-fundamentos-pensamento-computacional.md) e [02 — Lógica e Algoritmos](../../conteudo/02-logica-algoritmos-fluxo.md)  
> **Duração estimada:** 45–60 min  
> **Entrega:** repositório Git com arquivo markdown + fluxograma

---

## Contexto

Uma rede de farmácias popular precisa otimizar o atendimento no balcão de medicamentos controlados. O processo atual é manual: o atendente recebe a receita, verifica validade, consulta estoque, separa o medicamento, registra a venda no sistema e orienta o cliente. Nos horários de pico, o tempo médio de espera passa de 25 minutos — e erros de verificação de receita já geraram multas da Anvisa.

---

## Parte A — Pensamento Computacional (20 min)

### A1. Decomposição

Quebre o processo de atendimento em **pelo menos 6 subproblemas** independentes. Para cada subproblema, indique:

- Entrada(s) necessária(s).
- Saída esperada.
- Critério de sucesso.

### A2. Reconhecimento de Padrões

Identifique **4 padrões** que se repetem entre diferentes cenários de atendimento (medicamento simples, controlado, em falta, receita vencida). Justifique por que cada um é um padrão.

### A3. Abstração

Proponha **2 abstrações** que simplifiquem o sistema sem perder informação essencial. Para cada abstração:

- O que foi removido (detalhe irrelevante).
- O que foi mantido (essência do processo).
- Como isso facilita a solução.

---

## Parte B — Algoritmo e Fluxo (25 min)

### B1. Pseudocódigo estruturado

Escreva o algoritmo completo de atendimento em pseudocódigo contendo:

- Pelo menos **2 estruturas condicionais** (SE/SENÃO).
- Pelo menos **1 laço de repetição** (ENQUANTO ou PARA).
- Tratamento de **3 exceções** (receita vencida, estoque zero, cliente sem documento).
- Comentários explicando decisões de design.

**Requisito:** use os nomes de variáveis de forma descritiva (ex: `receita_valida`, não `x`).

### B2. Fluxograma

Converta o pseudocódigo em fluxograma seguindo o padrão ISO 5807:

- Retângulo para processos.
- Losango para decisões.
- Paralelogramo para entrada/saída.
- Terminadores (oval) para início/fim.

**Ferramentas sugeridas:** draw.io, Mermaid, Excalidraw ou papel fotografado.

### B3. Trace Table (tabela de rastreamento)

Simule a execução do seu algoritmo para **2 cenários**:

| Cenário | receita_valida | estoque > 0 | documento_ok | Resultado esperado |
|---------|---------------|-------------|-------------|-------------------|
| 1. Normal | V | V | V | Venda realizada |
| 2. Receita vencida | F | — | — | Recusa + orientação |

Preencha a tabela de rastreamento passo a passo mostrando o valor de cada variável a cada iteração.

---

## Critérios de Avaliação

| Critério | Peso | Excelente | Suficiente | Insuficiente |
|----------|------|-----------|------------|-------------|
| Decomposição e padrões | 25% | 6+ subproblemas claros, 4 padrões com justificativa | 4-5 subproblemas, 2-3 padrões | Menos de 4 subproblemas, sem justificativa |
| Qualidade do pseudocódigo | 30% | Todas as estruturas, 3+ exceções, variáveis descritivas | Estruturas presentes, 1-2 exceções | Incompleto ou sem estruturas de controle |
| Fluxograma | 20% | Padrão ISO, legível, consistente com pseudocódigo | Legível mas com desvios menores | Ilegível ou inconsistente |
| Trace table | 15% | 2 cenários completos sem erros | 1 cenário completo | Ausente ou com erros lógicos |
| Comunicação técnica | 10% | Texto claro, organizado, com reflexão sobre escolhas | Organizado | Desorganizado ou sem contexto |

---

## Entrega

1. Arquivo `checkpoint-01.md` no seu repositório com todas as partes.
2. Fluxograma como imagem ou código Mermaid embutido.
3. Seção final obrigatória: **"Reflexão"** — responda em 5-10 linhas:
   - Qual parte foi mais difícil e por quê?
   - Que decisão de design você mudaria se refizesse?
   - Como o pensamento computacional ajudou a estruturar o problema?
