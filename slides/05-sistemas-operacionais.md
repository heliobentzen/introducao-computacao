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

# 05 — Sistemas Operacionais Modernos

**Introdução à Computação — ADS**
A camada que faz o hardware servir ao software.

---

## O que é um Sistema Operacional?

> Interface entre hardware e aplicações. Gerencia recursos de forma justa, segura e eficiente.

```
  [Aplicações]     ← Onde você programa
  [  Bibliotecas ] ← APIs, frameworks
  [    Kernel    ] ← Coração do SO
  [   Hardware   ] ← CPU, RAM, disco, rede
```

**Funções:** gerenciar processos, memória, sistema de arquivos, I/O e segurança.

---

## Tipos de Kernel

| Tipo | Descrição | Exemplo |
|------|----------|---------|
| **Monolítico** | Tudo no kernel, rápido mas grande | Linux |
| **Microkernel** | Mínimo no kernel, serviços em user space | MINIX, QNX |
| **Híbrido** | Meio-termo pragmático | Windows NT, macOS (XNU) |

---

## Processos — Ciclo de Vida

```
[Novo] → [Pronto] → [Executando] → [Terminado]
              ↑            |
              └── [Bloqueado] (esperando I/O)
```

| Estado | Significado |
|--------|-----------|
| Novo | Criado, aguardando admissão |
| Pronto | Na fila, esperando CPU |
| Executando | Usando a CPU agora |
| Bloqueado | Esperando evento (I/O, recurso) |
| Terminado | Execução concluída |

---

## Escalonamento de CPU

| Algoritmo | Preemptivo | Como funciona | Problema |
|-----------|-----------|---------------|---------|
| FCFS | Não | Primeiro a chegar | Convoy effect |
| SJF | Não | Menor burst primeiro | Starvation |
| Round Robin | Sim | Quantum fixo, reveza | Muita troca de contexto |
| Prioridade | Sim/Não | Maior prioridade primeiro | Starvation (resolvível com aging) |

**Round Robin (quantum=4):** o mais usado em sistemas interativos.

---

## Round Robin — Exemplo

Processos: P1(burst=8), P2(burst=4), P3(burst=2), quantum=4

```
Gantt: |P1(4)|P2(4)|P3(2)|P1(4)|
t:      0    4    8   10   14
```

| Processo | Espera | Turnaround |
|----------|--------|-----------|
| P1 | 6 | 14 |
| P2 | 4 | 8 |
| P3 | 8 | 10 |
| **Média** | **6.0** | **10.7** |

---

## Gerenciamento de Memória — Paginação

Memória dividida em **páginas** de tamanho fixo (ex: 4 KB).

```
Página Virtual → Tabela de Páginas → Frame Físico
    P0         →      [3]         →    Frame 3
    P1         →      [7]         →    Frame 7
    P2         →      [1]         →    Frame 1
```

**Page fault:** página não está na RAM → buscar no disco → lento!

---

## Algoritmos de Substituição de Página

| Algoritmo | Regra | Optimal? |
|-----------|-------|----------|
| **FIFO** | Remove a mais antiga | Não (anomalia de Bélády) |
| **LRU** | Remove a menos recentemente usada | Próximo do ótimo |
| **Ótimo** | Remove a que será usada mais tarde no futuro | Impossível (teórico) |

**Anomalia de Bélády:** com FIFO, mais frames pode causar MAIS page faults!

---

## Sistema de Arquivos

| Sistema | SO | Journaling | Tamanho máx. arquivo |
|---------|-----|-----------|---------------------|
| ext4 | Linux | Sim | 16 TB |
| NTFS | Windows | Sim | 16 EB |
| APFS | macOS | Sim | 8 EB |
| FAT32 | Universal | Não | 4 GB |

**Journaling:** registra operações antes de executar → protege contra corrupção em queda de energia.

---

## Terminal — Comandos Essenciais

| Comando | O que faz |
|---------|----------|
| `pwd` | Onde estou |
| `ls -la` | Listar com detalhes |
| `cd`, `mkdir`, `rm` | Navegar e gerenciar |
| `cat`, `head`, `tail` | Ver conteúdo |
| `grep "texto" arquivo` | Buscar |
| `chmod 755 script.sh` | Alterar permissões |
| `ps aux \| grep java` | Pipeline: processos filtrados |

---

## Permissões Unix — Conexão com Octal

```
rwxr-xr-- = 754₈
```

| Dono (rwx) | Grupo (r-x) | Outros (r--) |
|-----------|-------------|-------------|
| 4+2+1 = **7** | 4+0+1 = **5** | 4+0+0 = **4** |

**Módulo 04 em ação:** permissões usam representação octal direta!

---

## Referências-chave

- Tanenbaum, A. (2015). *Modern Operating Systems* (4ª ed.)
- Silberschatz et al. (2018). *Operating System Concepts* (10ª ed.)
- Maziero, C. (2019). *Sistemas Operacionais: Conceitos e Mecanismos* (open access)

---

## Checkpoint

**→ Checkpoint 03** (com módulo 06)
Escalonamento Round Robin, paginação FIFO/LRU, comandos de terminal, modelos cloud.
