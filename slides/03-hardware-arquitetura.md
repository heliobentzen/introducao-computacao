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

# 🖥️ Hardware e Arquitetura

**Introdução à Computação · ADS**

*Do silício ao software: como a máquina funciona*

![bg right:40% brightness:0.6](https://images.unsplash.com/photo-1518770660439-4636190af475?w=600&h=400&fit=crop)

---

## 📜 5 Gerações de Computadores

| Geração | Tecnologia | Marco |
|:-------:|-----------|-------|
| 1️⃣ 1940s | Válvulas | ENIAC — 30 ton |
| 2️⃣ 1950s | Transistores | IBM 7094 |
| 3️⃣ 1960s | Circuitos integrados | IBM System/360 |
| 4️⃣ 1970s+ | Microprocessadores | Intel 4004 → Core |
| 5️⃣ 2010s+ | IA · Quântico · Paralelo | GPUs · TPUs · QPUs |

---

## 🏗️ Arquitetura de Von Neumann

```
 ┌──────────── CPU ─────────────┐
 │  UC (controle)    ULA (cálculo) │
 │       Registradores             │
 └─────────────┬───────────────┘
           Barramento
 ┌─────────────┴───────────────┐
 │    Memória Principal         │
 │  (dados + instruções juntos) │
 └─────────────┬───────────────┘
          [Dispositivos I/O]
```

> **Princípio:** programa armazenado na mesma memória que os dados.

---

## 🔄 Ciclo Fetch – Decode – Execute

| Etapa | O que acontece |
|:-----:|---------------|
| **Fetch** | UC busca instrução (endereço no PC) |
| **Decode** | UC interpreta o opcode |
| **Execute** | ULA executa; resultado → registrador |
| **PC++** | Avança para próxima instrução |

⚡ Repete **bilhões** de vezes/segundo (GHz)

---

## ⚠️ Von Neumann Bottleneck

> CPU é mais rápida que o caminho até a memória. — Backus, 1978

**Soluções modernas:**

| Técnica | Como resolve |
|---------|-------------|
| 🗄️ Cache | Memória intermediária ultrarrápida |
| ⛓️ Pipeline | Execução paralela de fases |
| 🔀 Harvard | Barramentos separados dados/instruções |

---

## 📊 Hierarquia de Memória

```
          ⚡ Registradores   ~0.3 ns     bytes
          ⚡ Cache L1        ~1 ns       64 KB
          ⚡ Cache L2/L3     ~4-10 ns    256 KB–32 MB
          💾 RAM DDR5        ~80 ns      16–64 GB
          💿 SSD NVMe        ~25 μs      512 GB–4 TB
          📀 HDD             ~5 ms       1–20 TB
```

⬆️ *Mais rápido, menor, mais caro*
⬇️ *Mais lento, maior, mais barato*

---

## ⚔️ CISC vs RISC

| Aspecto | CISC | RISC |
|---------|------|------|
| Instruções | Complexas, variáveis | Simples, fixas |
| Ciclos/instr. | Múltiplos | ~1 (pipeline) |
| Exemplo | Intel x86, AMD64 | ARM, RISC-V, Apple M |
| Domina em | Desktops, servers | Mobile, Apple Silicon |

> 🍎 Apple M1/M2/M3: RISC superando CISC em **performance/watt**.

---

## 🎮 CPU vs GPU

| | CPU | GPU |
|:-:|:---:|:---:|
| Núcleos | 4–64 potentes | 1k–16k simples |
| Ideal para | Tarefas sequenciais | Paralelismo massivo |
| Uso em IA | Pré-processamento | Treinamento de redes |

> Deep Learning **não existiria** sem GPUs.

---

## 📚 Referências

- Tanenbaum (2013). *Structured Computer Organization*
- Patterson & Hennessy (2021). *Computer Org. and Design* — RISC-V
- Backus (1978). *Can Programming Be Liberated…?*

**→ Checkpoint 02** · com módulo 04
