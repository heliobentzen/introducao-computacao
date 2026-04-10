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

# 03 — Hardware e Arquitetura de Computadores

**Introdução à Computação — ADS**
Do silício ao software: como a máquina funciona.

---

## 5 Gerações de Computadores

| Geração | Período | Tecnologia | Exemplo |
|---------|---------|-----------|---------|
| 1ª | 1940–1956 | Válvulas | ENIAC (30 ton, 18.000 válvulas) |
| 2ª | 1956–1963 | Transistores | IBM 7094 |
| 3ª | 1963–1971 | Circuitos integrados | IBM System/360 |
| 4ª | 1971–2010 | Microprocessadores | Intel 4004 → Core i7 |
| 5ª | 2010+ | IA, quântico, paralelo | GPUs, TPUs, QPUs |

---

## Arquitetura de Von Neumann

```
┌─────────────────────────────────────┐
│              CPU                     │
│  ┌──────────┐  ┌──────────────┐     │
│  │    UC     │  │    ULA       │     │
│  │ (controle)│  │ (aritmética) │     │
│  └──────────┘  └──────────────┘     │
│       ┌────────────────┐            │
│       │  Registradores │            │
│       └────────────────┘            │
└──────────────┬──────────────────────┘
               │ Barramento
┌──────────────┴──────────────────────┐
│         Memória Principal            │
│    (dados + instruções juntos)       │
└─────────────────────────────────────┘
               │ I/O
         [Dispositivos]
```

**Princípio:** programa armazenado na mesma memória que os dados.

---

## Ciclo Fetch–Decode–Execute

1. **Fetch:** UC busca instrução na memória (endereço no PC)
2. **Decode:** UC interpreta o opcode da instrução
3. **Execute:** ULA executa operação, resultado vai para registrador
4. **PC++:** contador de programa avança para próxima instrução

**Repete** bilhões de vezes por segundo (GHz = bilhões de ciclos/s).

---

## Von Neumann Bottleneck

> O gargalo entre CPU e memória limita o desempenho — **a CPU é mais rápida que o caminho até os dados.** (Backus, 1978)

**Soluções:**

- Cache (memória intermediária ultrarrápida)
- Pipeline (execução paralela de fases)
- Arquitetura Harvard (barramentos separados para dados e instruções)

---

## Hierarquia de Memória

```
        Registradores  (~0.3ns, bytes)
           Cache L1    (~1ns, 64KB)
           Cache L2    (~4ns, 256KB)
           Cache L3    (~10ns, 8-32MB)
          RAM DDR5     (~80ns, 16-64GB)
         SSD NVMe      (~25μs, 512GB-4TB)
           HDD         (~5ms, 1-20TB)
```

**Regra:** sobe → mais rápido, menor, mais caro
          desce → mais lento, maior, mais barato

---

## CISC vs RISC

| Aspecto | CISC | RISC |
|---------|------|------|
| Instruções | Complexas, variáveis | Simples, fixas |
| Ciclos/instrução | Múltiplos | ~1 (pipeline) |
| Exemplo | Intel x86, AMD64 | ARM, RISC-V, Apple M-series |
| Onde domina | Desktops, servidores | Mobile, embarcados, Apple Silicon |

**Apple M1/M2/M3:** RISC superando CISC em performance/watt.

---

## GPU e Processamento Paralelo

| | CPU | GPU |
|---|-----|-----|
| Núcleos | 4–64 (potentes) | 1.000–16.000 (simples) |
| Melhor para | Tarefas sequenciais complexas | Tarefas paralelas massivas |
| Uso em IA | Pré-processamento | Treinamento de redes neurais |

**GPGPU:** usar GPU para computação geral (CUDA, OpenCL).
Deep Learning não existiria sem GPUs.

---

## Diagnóstico de Gargalos

| Sintoma | Componente provável | Verificação |
|---------|-------------------|------------|
| Sistema lento ao abrir apps | RAM insuficiente ou HDD | Verificar uso de memória e tipo de disco |
| Fan alta, throttling | CPU superaquecendo | Monitorar temperatura |
| Jogo travando | GPU ou VRAM | Verificar FPS e uso de GPU |
| Compilação lenta | CPU (poucos núcleos) | Monitorar uso de CPU |

---

## Referências-chave

- Tanenbaum, A. (2013). *Structured Computer Organization* (6ª ed.)
- Patterson & Hennessy (2021). *Computer Organization and Design* (RISC-V)
- Stallings, W. (2022). *Computer Organization and Architecture* (11ª ed.)
- Backus, J. (1978). Can Programming Be Liberated from the Von Neumann Style?

---

## Checkpoint

**→ Checkpoint 02** (com módulo 04)
Ciclo de instrução, hierarquia de memória, CISC vs RISC + conversões de base.
