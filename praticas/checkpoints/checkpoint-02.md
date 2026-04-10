# Checkpoint 02 — Hardware, Arquitetura e Representação de Dados

> **Módulos de referência:** [03 — Hardware e Arquitetura](../../conteudo/03-hardware-arquitetura.md) e [04 — Dados e Numeração](../../conteudo/04-dados-numeracao.md)  
> **Duração estimada:** 45–60 min  
> **Entrega:** repositório Git com resoluções comentadas

---

## Parte A — Arquitetura de Computadores (20 min)

### A1. Ciclo de instrução

Descreva passo a passo o que acontece em cada fase do ciclo **fetch–decode–execute** quando o processador executa a instrução `ADD R1, R2, R3` (somar conteúdo de R2 e R3, armazenar em R1). Inclua:

- Qual registrador é usado em cada fase.
- O papel do barramento nesse fluxo.
- O que a UC (Unidade de Controle) e a ULA fazem em cada etapa.

### A2. Hierarquia de memória

Complete a tabela e responda às perguntas:

| Nível | Tecnologia | Capacidade típica (2024) | Latência aproximada | Volátil? |
|-------|-----------|------------------------|---------------------|----------|
| Registradores | SRAM | ??? | ??? | ??? |
| Cache L1 | ??? | ??? | ~1 ns | ??? |
| Cache L3 | ??? | ??? | ??? | ??? |
| RAM | ??? | ??? | ??? | ??? |
| SSD NVMe | ??? | ??? | ??? | ??? |
| HDD | Magnético | ??? | ??? | ??? |

**Perguntas:**

1. Por que não usamos apenas o tipo de memória mais rápido para tudo?
2. Explique o conceito de **localidade temporal e espacial** e como o cache explora isso.
3. O que é o **Von Neumann bottleneck** e qual solução arquitetural foi proposta (Backus, 1978)?

### A3. CISC vs RISC

Compare as arquiteturas em 3 critérios e dê 1 exemplo real de processador para cada:

| Critério | CISC | RISC |
|----------|------|------|
| Complexidade das instruções | | |
| Número de ciclos por instrução | | |
| Uso de pipeline | | |
| Exemplo de processador | | |

---

## Parte B — Representação de Dados e Numeração (25 min)

### B1. Conversões de base

Resolva mostrando **todos os passos** (divisões sucessivas, multiplicações ou agrupamento):

| Conversão | Valor | Resultado |
|-----------|-------|----------|
| Decimal → Binário | 93 | |
| Decimal → Binário | 200 | |
| Binário → Decimal | 11010110 | |
| Binário → Hexadecimal | 10111100 01010011 | |
| Hexadecimal → Decimal | 0x1A3F | |
| Octal → Binário | 0o375 | |

### B2. Aritmética binária

Efetue as operações em binário de 8 bits. Indique se houve overflow:

| Operação | Operandos | Resultado (binário) | Resultado (decimal) | Overflow? |
|----------|-----------|-------------------|--------------------|----|
| Soma | 01101010 + 00110101 | | | |
| Soma | 01111111 + 00000001 | | | |
| Subtração (complemento de 2) | 01010000 - 00110000 | | | |

### B3. Complemento de 2

1. Represente **-58** em complemento de 2 com 8 bits. Mostre cada passo.
2. Dado o byte `10110100` em complemento de 2, qual o valor decimal? Mostre o cálculo.
3. Explique em 5 linhas por que complemento de 2 é preferido a sinal-magnitude.

### B4. Ponto flutuante IEEE 754

Analise o número **-13.625** em IEEE 754 precisão simples (32 bits):

1. Converta para binário.
2. Normalize.
3. Identifique: sinal, expoente (com bias 127) e mantissa.
4. Escreva a representação final em 32 bits.

**Pergunta bônus:** Explique por que `0.1 + 0.2 ≠ 0.3` em ponto flutuante. Cite Goldberg (1991).

### B5. Codificação de texto

1. Codifique a palavra **"ADS"** em ASCII (decimal e binário).
2. Quantos bytes ocupa a string **"Computação"** em UTF-8? Justifique (lembre-se: caracteres acentuados usam 2 bytes em UTF-8).
3. Por que o Unicode foi necessário? Cite 2 problemas que ASCII causava em software internacional.

---

## Critérios de Avaliação

| Critério | Peso | Excelente | Suficiente | Insuficiente |
|----------|------|-----------|------------|-------------|
| Ciclo de instrução e hierarquia | 25% | Descrição completa com terminologia correta | Descrição parcial | Incompleta ou com erros conceituais |
| Conversões de base | 25% | Todas corretas com passos visíveis | 4+ corretas | Menos de 4 ou sem passos |
| Aritmética e complemento de 2 | 25% | Tudo correto, overflow identificado | Operações corretas, overflow parcial | Erros fundamentais |
| IEEE 754 e codificação | 15% | Representação completa e correta | Parcialmente correto | Ausente ou incorreto |
| Clareza e reflexão | 10% | Erros documentados, explicações próprias | Organizado | Cópia sem reflexão |

---

## Entrega

1. Arquivo `checkpoint-02.md` com todas as resoluções comentadas.
2. Seção obrigatória: **"Erros que cometi"** — liste pelo menos 3 erros que cometeu durante a resolução e o que aprendeu com cada um.
3. Seção obrigatória: **"Conexão com o módulo anterior"** — em 5 linhas, conecte a representação de dados com o pensamento computacional do módulo 01 (como abstração e padrões aparecem aqui?).
