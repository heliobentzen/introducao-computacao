# Sprint 2 — Infraestrutura, Dados e Deploy

> **Módulos de referência:** [04 — Dados e Numeração](../../conteudo/04-dados-numeracao.md), [05 — Sistemas Operacionais](../../conteudo/05-sistemas-operacionais.md) e [06 — Cloud Computing](../../conteudo/06-cloud-computing.md)  
> **Duração:** Semanas 7–12  
> **Entrega:** especificação técnica de infraestrutura + protótipo navegável

---

## Objetivo

Definir **como e onde** o sistema do projeto integrador será executado: representação de dados, infraestrutura de SO, arquitetura cloud e protótipo funcional.

---

## Tarefas

### T1. Modelagem de dados (Módulo 04)

Defina a **estrutura de dados** do sistema:

| Campo | Tipo | Tamanho (bytes) | Exemplo | Observação |
|-------|------|-----------------|---------|-----------|
| id_tarefa | inteiro 32-bit | 4 | 1025 | Auto-incremento |
| titulo | string UTF-8 | variável (max 200) | "Estudar SO" | Acentos = 2 bytes |
| prioridade | enum (1 byte) | 1 | 2 (alta) | 0=baixa, 1=média, 2=alta, 3=urgente |
| data_prazo | timestamp | 8 | 2026-04-15T23:59 | Unix timestamp |
| concluida | booleano | 1 | false | |
| ... | | | | |

**Exercícios obrigatórios:**

1. Calcule o **tamanho médio de um registro** em bytes.
2. Estime o armazenamento para **10.000 tarefas** (1 ano de uso de uma turma).
3. Represente o campo `prioridade` em **binário de 2 bits**. Por que 2 bits são suficientes para 4 valores?
4. Codifique o título "Revisão P1" em **UTF-8** (mostre os bytes em hexadecimal).

### T2. Ambiente de execução (Módulo 05)

Especifique o ambiente operacional:

1. **SO escolhido** para o servidor: qual e por quê? (Linux? Qual distribuição?)
2. **Gerenciamento de processos:** o sistema terá processos concorrentes? (ex: notificações rodando em paralelo ao servidor web). Qual estratégia de escalonamento é adequada?
3. **Sistema de arquivos:** onde os dados ficam? Qual filesystem? Justifique.
4. **Permissões:** defina 3 níveis de acesso com permissões Unix (octal):

| Usuário | Permissão (simbólica) | Permissão (octal) | Justificativa |
|---------|----------------------|-------------------|-------------|
| admin | | | |
| app (processo) | | | |
| aluno (leitura) | | | |

1. **Comandos essenciais:** liste 5 comandos de terminal que a equipe usaria para administrar o servidor.

### T3. Arquitetura cloud (Módulo 06)

Projete a infraestrutura cloud:

**Diagrama de arquitetura** (draw.io ou Mermaid):

```
[Usuário] → [CDN/Frontend] → [API/Backend] → [Banco de Dados]
                                    ↕
                              [Fila de tarefas]
                                    ↕
                            [Serviço de notificação]
```

**Especificação:**

| Componente | Serviço (AWS/Azure/GCP) | Modelo | Config | Custo estimado/mês |
|-----------|------------------------|--------|--------|-------------------|
| Frontend | | | | |
| API | | | | |
| Banco de dados | | | | |
| Notificações | | | | |
| Monitoramento | | | | |

**Perguntas obrigatórias:**

1. Qual o SLA combinado de toda a stack?
2. Como fazer backup? Frequência e retenção?
3. O que acontece se o banco de dados ficar indisponível? (plano de contingência)

### T4. Protótipo navegável

Construa **protótipo de baixa/média fidelidade** com:

- Tela de login/cadastro.
- Dashboard com lista de tarefas.
- Formulário de nova tarefa.
- Tela de configurações/notificações.

**Ferramentas sugeridas:** Figma, HTML/CSS simples, Canva, ou até slides navegáveis.

**Requisitos:**

- 2 fluxos completos navegáveis (cadastrar tarefa + marcar como concluída).
- Consistência visual (cores, fontes, layout).
- Responsividade básica (funcionar em mobile e desktop).

### T5. Estimativa de custo total

Monte a **tabela de custo mensal e anual**:

| Categoria | Custo mensal | Custo anual |
|-----------|-------------|------------|
| Infraestrutura cloud | | |
| Domínio + SSL | | |
| Monitoramento | | |
| **Total** | | |

Proponha **2 estratégias de economia** (free tier, reservadas, serverless, etc.).

---

## Critérios de entrega

| Item | Presente? |
|------|----------|
| Modelagem de dados com cálculos | |
| Ambiente de SO especificado e justificado | |
| Permissões Unix definidas em octal | |
| Diagrama de arquitetura cloud | |
| Especificação com serviços reais e custos | |
| Protótipo com 2 fluxos navegáveis | |
| Estimativa de custo | |
| Commits de todos os membros | |

---

## Reflexão de sprint (obrigatória)

Cada membro responde (3–5 linhas):

1. Qual decisão técnica foi mais difícil de tomar?
2. Como os conceitos de numeração/dados apareceram na prática?
3. O que surpreendeu sobre custos de cloud?
