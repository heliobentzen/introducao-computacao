# Checkpoint 03 — Sistemas Operacionais e Cloud Computing

> **Módulos de referência:** [05 — Sistemas Operacionais](../../conteudo/05-sistemas-operacionais.md) e [06 — Cloud Computing](../../conteudo/06-cloud-computing.md)  
> **Duração estimada:** 45–60 min  
> **Entrega:** repositório Git com resoluções + capturas de tela do terminal

---

## Parte A — Sistemas Operacionais (25 min)

### A1. Processos e escalonamento

Considere a seguinte tabela de processos chegando a um sistema com escalonamento **Round Robin (quantum = 3)**:

| Processo | Chegada (ms) | Burst (ms) |
|----------|-------------|-----------|
| P1 | 0 | 8 |
| P2 | 1 | 4 |
| P3 | 2 | 2 |
| P4 | 3 | 5 |

**Tarefas:**

1. Desenhe o **diagrama de Gantt** da execução completa.
2. Calcule para cada processo: tempo de espera, tempo de turnaround.
3. Calcule o **tempo médio de espera** e **turnaround médio**.
4. Compare (em 5 linhas): o que mudaria se usássemos **SJF não-preemptivo** em vez de Round Robin?

### A2. Gerenciamento de memória

Um sistema com memória física de **16 frames** (páginas de 4 KB cada) recebe as seguintes referências de página:

```
7, 0, 1, 2, 0, 3, 0, 4, 2, 3, 0, 3, 2, 1, 2, 0, 1, 7, 0, 1
```

**Tarefas:**

1. Simule o algoritmo **FIFO** com 3 frames. Conte os **page faults**.
2. Simule o algoritmo **LRU** com 3 frames. Conte os **page faults**.
3. Qual algoritmo teve melhor desempenho? Por quê?
4. Agora simule **FIFO com 4 frames**. O número de page faults diminuiu? Se não, explique a **anomalia de Bélády**.

### A3. Prática em terminal

Execute os seguintes comandos no terminal (Bash, WSL ou Git Bash) e documente a saída:

| Comando | O que faz | Sua saída (resumida) |
|---------|----------|---------------------|
| `whoami` | Identifica o usuário | |
| `pwd` | Diretório atual | |
| `ls -la` (ou `dir`) | Lista com permissões | |
| `cat /etc/os-release` (Linux/WSL) | Info do SO | |
| `ps aux \| head -10` (ou `tasklist \| head`) | Processos ativos | |
| `df -h` (ou `wmic logicaldisk`) | Uso de disco | |
| `echo "Hello ADS" > teste.txt && cat teste.txt` | Redirecionamento | |

**Bônus:** Crie um pipeline que liste todos os arquivos `.md` do repositório, conte quantos são e exiba o resultado. Documente o comando completo.

### A4. Permissões Unix

Traduza as seguintes permissões e responda:

| Simbólico | Octal | Quem pode ler? | Quem pode executar? |
|-----------|-------|----------------|-------------------|
| `-rwxr-xr--` | ??? | | |
| `-rw-r-----` | ??? | | |
| `drwxrwxrwx` | ??? | | |

**Conexão com módulo 04:** Explique em 3 linhas como a representação octal de permissões usa o sistema de numeração octal que você estudou.

---

## Parte B — Cloud Computing (20 min)

### B1. Modelos de serviço

Para cada cenário, indique o modelo de serviço mais adequado (**IaaS, PaaS, SaaS, FaaS ou CaaS**) e justifique:

| Cenário | Modelo | Justificativa |
|---------|--------|-------------|
| Startup precisa hospedar app web Python sem gerenciar servidor | | |
| Empresa quer migrar servidor legado Linux tal como está | | |
| Escola adota e-mail corporativo para professores | | |
| Dev quer executar função que redimensiona imagens sob demanda | | |
| Time DevOps quer orquestrar microserviços com Kubernetes | | |

### B2. Disponibilidade e SLA

Um serviço tem SLA de **99.95%**. Calcule:

1. Tempo máximo de indisponibilidade por **mês** (30 dias).
2. Tempo máximo de indisponibilidade por **ano**.
3. Se o serviço usa 2 zonas de disponibilidade independentes, cada uma com 99.95%, qual a disponibilidade combinada? (Use: `A_total = 1 - (1 - A)²`)

### B3. Modelo de responsabilidade compartilhada

Preencha a matriz indicando quem é responsável (Provedor ou Cliente):

| Camada | IaaS | PaaS | SaaS |
|--------|------|------|------|
| Hardware físico | | | |
| Rede/virtualização | | | |
| Sistema operacional | | | |
| Runtime/middleware | | | |
| Aplicação | | | |
| Dados | | | |
| Controle de acesso | | | |

### B4. Análise de custo

Uma aplicação consome:

- 1 VM t3.medium (2 vCPU, 4 GB RAM) por 730h/mês → US$ 0.0416/h
- 50 GB de armazenamento S3 → US$ 0.023/GB/mês
- 100 GB de transferência de saída → US$ 0.09/GB

Calcule o **custo mensal total**. Depois, proponha **2 estratégias de otimização** (instâncias reservadas, autoscaling, etc.) e estime a economia.

---

## Critérios de Avaliação

| Critério | Peso | Excelente | Suficiente | Insuficiente |
|----------|------|-----------|------------|-------------|
| Escalonamento (Gantt + cálculos) | 25% | Diagrama correto, todos os tempos calculados | Diagrama correto, cálculos parciais | Diagrama incorreto |
| Paginação e Bélády | 20% | Simulações corretas, anomalia explicada | 2 simulações corretas | 1 ou menos corretas |
| Terminal e permissões | 15% | Todos os comandos + pipeline bônus | Comandos básicos documentados | Ausente |
| Cloud (modelos + SLA + custo) | 30% | Tudo correto com justificativas | Modelos corretos, cálculos parciais | Erros conceituais |
| Reflexão e conexões | 10% | Conexões entre módulos explícitas | Reflexão presente | Ausente |

---

## Entrega

1. Arquivo `checkpoint-03.md` com todas as resoluções.
2. Capturas de tela dos comandos de terminal (ou output colado no markdown).
3. Seção obrigatória: **"Mapa de conexões"** — em 8-10 linhas, explique como os conceitos de SO e Cloud se conectam entre si e com os módulos anteriores (ex: como paginação se relaciona com representação binária, como permissões usam octal, como hierarquia de memória impacta performance em cloud).
