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

## Módulo 05 · Sistemas Operacionais Modernos

**Prof. Hélio Bentzen**
IFPE · Análise e Desenvolvimento de Sistemas

---

# Sistemas Operacionais

---

## O que é um SO?

Interface entre **hardware** e **aplicações**, gerencia recursos de forma justa, segura e eficiente.

```
  ┌─ Aplicações ──────────┐
  ├─ Bibliotecas / APIs ──┤
  ├─ Kernel ─────────────┤  ← coração do SO
  └─ Hardware ────────────┘
```

Funções: processos · memória · arquivos · I/O · segurança

---

## Tipos de Kernel

| Tipo | Característica | Exemplo |
|------|---------------|---------|
| **Monolítico** | Tudo no kernel, rápido | Linux |
| **Microkernel** | Mínimo no kernel | MINIX, QNX |
| **Híbrido** | Meio-termo pragmático | Windows NT, macOS |

---

## Processos: Ciclo de Vida

```
 [Novo] → [Pronto] → [Executando] → [Terminado]
               ↑            │
               └── [Bloqueado] ← esperando I/O
```

| Estado | Significado |
|--------|-----------|
| Pronto | Na fila, esperando CPU |
| Executando | Usando a CPU |
| Bloqueado | Esperando evento externo |

---

## Escalonamento de CPU

| Algoritmo | Preemptivo? | Problema |
|-----------|:----------:|---------|
| **FCFS** | Não | Convoy effect |
| **SJF** | Não | Starvation |
| **Round Robin** | Sim | Troca de contexto |
| **Prioridade** | Sim/Não | Starvation (aging) |

> **Round Robin** (quantum fixo) é o mais usado em sistemas interativos.

---

## Round Robin: Exemplo

P1=8 · P2=4 · P3=2 · **quantum=4**

```
Gantt: │ P1(4) │ P2(4) │ P3(2) │ P1(4) │
    t:  0       4       8      10      14
```

| Processo | Espera | Turnaround |
|:--------:|:------:|:----------:|
| P1 | 6 | 14 |
| P2 | 4 | 8 |
| P3 | 8 | 10 |

---

## Paginação de Memória

Memória dividida em **páginas** de tamanho fixo (ex: 4 KB).

```
 Página Virtual  →  Tabela  →  Frame Físico
      P0         →   [3]   →   Frame 3
      P1         →   [7]   →   Frame 7
```

**Page fault:** página fora da RAM → busca no disco → lento!

---

## Substituição de Página

| Algoritmo | Regra | Ótimo? |
|-----------|-------|:------:|
| **FIFO** | Remove a mais antiga | Não |
| **LRU** | Menos recentemente usada | ≈ Sim |
| **Ótimo** | Usada mais tarde no futuro | teórico |

> **Anomalia de Bélády:** com FIFO, mais frames pode causar *mais* page faults!

---

## Sistemas de Arquivos

| FS | SO | Journaling | Máx. arquivo |
|----|:--:|:----------:|:------------:|
| ext4 | Linux | Sim | 16 TB |
| NTFS | Windows | Sim | 16 EB |
| APFS | macOS | Sim | 8 EB |
| FAT32 | Universal | Não | 4 GB |

---

## Terminal: Comandos Essenciais

| Comando | Ação |
|---------|------|
| `pwd` | Onde estou |
| `ls -la` | Listar com detalhes |
| `cd` · `mkdir` · `rm` | Navegar / gerenciar |
| `grep "x" arq` | Buscar texto |
| `chmod 755 script.sh` | Permissões |

---

## Permissões Unix → Octal

```
  rwx  r-x  r--  =  754₈
```

| Dono (rwx) | Grupo (r-x) | Outros (r--) |
|:----------:|:-----------:|:------------:|
| 4+2+1 = **7** | 4+0+1 = **5** | 4+0+0 = **4** |

> *Módulo 04 em ação:* permissões usam octal diretamente!

---

## Referências

- Tanenbaum (2015). *Modern Operating Systems*, 4ª ed.
- Silberschatz et al. (2018). *OS Concepts*, 10ª ed.
- Maziero (2019). *Sistemas Operacionais* (open access)

**→ Checkpoint 03** · com módulo 06
