# Sprint 1 — Modelagem de Solução

> **Módulos de referência:** [02 — Lógica e Algoritmos](../../conteudo/02-logica-algoritmos-fluxo.md) e [03 — Hardware e Arquitetura](../../conteudo/03-hardware-arquitetura.md)  
> **Duração:** Semanas 3–6  
> **Entrega:** algoritmos, fluxogramas e especificação de hardware

---

## Objetivo

Transformar as funcionalidades priorizadas na Sprint 0 em **fluxos estruturados, algoritmos documentados e requisitos de hardware**.

---

## Tarefas

### T1. Fluxo principal do usuário

Desenhe o **fluxo completo** de uso do sistema para o cenário principal:

- Usuário abre o app → cadastra tarefa → define prioridade → recebe lembrete → marca como concluída.
- Inclua **pelo menos 3 pontos de decisão** (ex: tarefa com prazo vencido? notificação ativa?).
- Formato: fluxograma ISO 5807 (draw.io, Mermaid ou Excalidraw).

### T2. Regras de negócio

Documente **pelo menos 8 regras** no formato:

| # | Regra | Condição | Ação | Exceção |
|---|-------|---------|------|---------|
| RN01 | Prioridade automática | Se prazo < 24h | Tarefa vira "urgente" | Tarefa já concluída |
| RN02 | ... | ... | ... | ... |

### T3. Pseudocódigo de 3 funcionalidades

Para **3 funcionalidades do MVP**, escreva pseudocódigo contendo:

- Estruturas condicionais (SE/SENÃO).
- Pelo menos 1 laço de repetição.
- Tratamento de exceção (entrada inválida, lista vazia).
- Variáveis com nomes descritivos.
- Comentários explicando decisões.

**Mínimo:** 15 linhas por funcionalidade.

### T4. Trace table

Para **1 funcionalidade**, simule a execução com trace table para 2 cenários:

- Cenário de sucesso (happy path).
- Cenário de erro (edge case).

### T5. Especificação de hardware

Defina os **requisitos mínimos de hardware** para executar o sistema, considerando:

| Componente | Desenvolvimento (notebook do aluno) | Produção (servidor) |
|-----------|-----------------------------------|-------------------|
| Processador | | |
| RAM | | |
| Armazenamento | | |
| Rede | | |

**Justifique** cada escolha com base nos conceitos de arquitetura (módulo 03):

- Por que essa quantidade de RAM?
- SSD ou HDD? Por quê?
- A hierarquia de memória impacta a performance do sistema? Como?

### T6. Métricas de sucesso do MVP

Defina **4 métricas** para avaliar se o MVP funciona:

| Métrica | Como medir | Meta |
|---------|-----------|------|
| Ex: Tempo para cadastrar tarefa | Cronômetro desde abertura até confirmação | < 30 segundos |
| | | |

---

## Critérios de entrega

| Item | Presente? |
|------|----------|
| Fluxograma completo com 3+ decisões | |
| 8+ regras de negócio documentadas | |
| Pseudocódigo de 3 funcionalidades | |
| Trace table para 2 cenários | |
| Especificação de hardware justificada | |
| 4 métricas de sucesso | |
| Commits de todos os membros | |

---

## Reflexão de sprint (obrigatória)

Cada membro responde (3–5 linhas):

1. Qual funcionalidade foi mais difícil de modelar e por quê?
2. Alguma regra de negócio mudou durante a sprint? O que motivou?
3. Como o pensamento computacional (sprint 0) facilitou ou dificultou esta etapa?
