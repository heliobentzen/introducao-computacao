---
marp: true
theme: default
paginate: true
style: |
  section { font-family: 'Segoe UI', system-ui, sans-serif; background: linear-gradient(135deg,#0c0c1d,#1a1a3e); color: #e8e8f0; }
  h1 { color: #ff6b6b; font-size: 2.2em; }
  h2 { background: linear-gradient(90deg,#e94560,#c23152); color: #fff; padding: 6px 20px; border-radius: 8px; display: inline-block; }
  strong { color: #00d4ff; } em { color: #ffd166; font-style: normal; }
  table { font-size: 0.72em; } th { background: rgba(233,69,96,0.85); color: #fff; }
  td { background: rgba(255,255,255,0.04); }
  code { background: rgba(0,212,255,0.12); color: #ff6b6b; padding: 2px 6px; border-radius: 4px; }
  pre { background: #12122a !important; border-radius: 10px; border: 1px solid rgba(233,69,96,0.3); }
  pre code { color: #e8e8f0; background: none; }
  blockquote { border-left: 4px solid #e94560; background: rgba(233,69,96,0.08); padding: 8px 16px; border-radius: 0 8px 8px 0; }
  a { color: #00d4ff; } img { border-radius: 10px; }
  section::after { color: rgba(255,255,255,0.3); font-size: 0.7em; }
---

<!-- _class: lead -->

# 🐧 Sistemas Operacionais

**Introdução à Computação · ADS**

*A camada que faz o hardware servir ao software*

![bg right:40% brightness:0.6](https://images.unsplash.com/photo-1629654297299-c8506221ca97?w=600&h=400&fit=crop)

---

## 🎯 O que é um SO?

Interface entre **hardware** e **aplicações** — gerencia recursos de forma justa, segura e eficiente.

```
  ┌─ Aplicações ──────────┐
  ├─ Bibliotecas / APIs ──┤
  ├─ 🔲 Kernel ───────────┤  ← coração do SO
  └─ Hardware ────────────┘
```

**Funções:** processos · memória · arquivos · I/O · segurança

---

## 🧬 Tipos de Kernel

| Tipo | Característica | Exemplo |
|------|---------------|---------|
| **Monolítico** | Tudo no kernel — rápido | Linux |
| **Microkernel** | Mínimo no kernel | MINIX, QNX |
| **Híbrido** | Meio-termo pragmático | Windows NT, macOS |

---

## 🔄 Processos — Ciclo de Vida

```
 [Novo] → [Pronto] → [Executando] → [Terminado]
               ↑            │
               └── [Bloqueado] ← esperando I/O
```

| Estado | Significado |
|--------|-----------|
| 🟡 Pronto | Na fila, esperando CPU |
| 🟢 Executando | Usando a CPU agora |
| 🔴 Bloqueado | Esperando evento externo |

---

## ⏱️ Escalonamento de CPU

| Algoritmo | Preemptivo? | Problema |
|-----------|:----------:|---------|
| **FCFS** | ❌ | Convoy effect |
| **SJF** | ❌ | Starvation |
| **Round Robin** | ✅ | Troca de contexto |
| **Prioridade** | ✅/❌ | Starvation (aging) |

> **Round Robin** (quantum fixo) é o mais usado em sistemas interativos.

---

## 📊 Round Robin — Exemplo

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

## 📄 Paginação de Memória

Memória dividida em **páginas** de tamanho fixo (ex: 4 KB).

```
 Página Virtual  →  Tabela  →  Frame Físico
      P0         →   [3]   →   Frame 3
      P1         →   [7]   →   Frame 7
```

⚠️ **Page fault:** página fora da RAM → busca no disco → lento!

---

## 🔃 Substituição de Página

| Algoritmo | Regra | Ótimo? |
|-----------|-------|:------:|
| **FIFO** | Remove a mais antiga | ❌ |
| **LRU** | Menos recentemente usada | ≈ ✅ |
| **Ótimo** | Usada mais tarde no futuro | 🏆 teórico |

> 🐛 **Anomalia de Bélády:** com FIFO, mais frames pode causar *mais* page faults!

---

## 📂 Sistemas de Arquivos

| FS | SO | Journaling | Máx. arquivo |
|----|:--:|:----------:|:------------:|
| ext4 | Linux | ✅ | 16 TB |
| NTFS | Windows | ✅ | 16 EB |
| APFS | macOS | ✅ | 8 EB |
| FAT32 | Universal | ❌ | 4 GB |

---

## 💻 Terminal — Comandos Essenciais

| Comando | Ação |
|---------|------|
| `pwd` | Onde estou |
| `ls -la` | Listar com detalhes |
| `cd` · `mkdir` · `rm` | Navegar / gerenciar |
| `grep "x" arq` | Buscar texto |
| `chmod 755 script.sh` | Permissões |

---

## 🔐 Permissões Unix → Octal

```
  rwx  r-x  r--  =  754₈
```

| Dono (rwx) | Grupo (r-x) | Outros (r--) |
|:----------:|:-----------:|:------------:|
| 4+2+1 = **7** | 4+0+1 = **5** | 4+0+0 = **4** |

> 🔗 **Módulo 04 em ação:** permissões usam octal diretamente!

---

## 📚 Referências

- Tanenbaum (2015). *Modern Operating Systems*, 4ª ed.
- Silberschatz et al. (2018). *OS Concepts*, 10ª ed.
- Maziero (2019). *Sistemas Operacionais* (open access)

**→ Checkpoint 03** · com módulo 06
