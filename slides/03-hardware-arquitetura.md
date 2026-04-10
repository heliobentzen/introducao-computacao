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

## Módulo 03 · Hardware e Arquitetura de Computadores

**Prof. Hélio Bentzen**
IFPE · Análise e Desenvolvimento de Sistemas

---

# 🖥️ Hardware e Arquitetura

---

## 5 Gerações de Computadores

| Geração | Tecnologia | Marco |
|:-------:|-----------|-------|
| 1ª 1940s | Válvulas | ENIAC — 30 ton |
| 2ª 1950s | Transistores | IBM 7094 |
| 3ª 1960s | Circuitos integrados | IBM System/360 |
| 4ª 1970s+ | Microprocessadores | Intel 4004 → Core |
| 5ª 2010s+ | IA · Quântico · Paralelo | GPUs · TPUs · QPUs |

---

## Arquitetura de Von Neumann

```
 ┌──────────── CPU ────────────────┐
 │  UC (controle)   ULA (cálculo)  │
 │       Registradores             │
 └─────────────┬───────────────────┘
           Barramento
 ┌─────────────┴───────────────────┐
 │       Memória Principal          │
 │   (dados + instruções juntos)    │
 └─────────────┬───────────────────┘
         [Dispositivos I/O]
```

> Programa armazenado na **mesma memória** que os dados.

---

## Ciclo Fetch – Decode – Execute

| Etapa | O que acontece |
|:-----:|---------------|
| **Fetch** | UC busca instrução (endereço no PC) |
| **Decode** | UC interpreta o opcode |
| **Execute** | ULA executa; resultado → registrador |
| **PC++** | Avança para próxima instrução |

Repete **bilhões** de vezes/segundo (GHz).

---

## Von Neumann Bottleneck

> CPU é mais rápida que o caminho até a memória. — Backus, 1978

| Técnica | Como resolve |
|---------|-------------|
| **Cache** | Memória intermediária ultrarrápida |
| **Pipeline** | Execução paralela de fases |
| **Harvard** | Barramentos separados dados/instruções |

---

## Hierarquia de Memória

```
    ⚡ Registradores   ~0.3 ns    bytes
    ⚡ Cache L1        ~1 ns      64 KB
    ⚡ Cache L2/L3     ~4-10 ns   256 KB–32 MB
    💾 RAM DDR5        ~80 ns     16–64 GB
    💿 SSD NVMe        ~25 μs     512 GB–4 TB
    📀 HDD             ~5 ms      1–20 TB
```

⬆️ *Mais rápido, menor, mais caro* · ⬇️ *Mais lento, maior, mais barato*

---

## CISC vs RISC

| Aspecto | CISC | RISC |
|---------|------|------|
| Instruções | Complexas, variáveis | Simples, fixas |
| Ciclos/instr. | Múltiplos | ~1 (pipeline) |
| Exemplo | Intel x86, AMD64 | ARM, RISC-V, Apple M |
| Domina em | Desktops, servers | Mobile, Apple Silicon |

> Apple M1/M2/M3: RISC superando CISC em **performance/watt**.

---

## CPU vs GPU

| | CPU | GPU |
|:-:|:---:|:---:|
| Núcleos | 4–64 potentes | 1k–16k simples |
| Ideal para | Tarefas sequenciais | Paralelismo massivo |
| Uso em IA | Pré-processamento | Treinamento de redes |

> Deep Learning **não existiria** sem GPUs.

---

## Referências

- Tanenbaum (2013). *Structured Computer Organization*
- Patterson & Hennessy (2021). *Computer Org. and Design* — RISC-V
- Backus (1978). *Can Programming Be Liberated…?*

**→ Checkpoint 02** · com módulo 04
