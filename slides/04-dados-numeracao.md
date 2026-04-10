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

# 04 — Representação de Dados e Sistemas de Numeração

**Introdução à Computação — ADS**
Por que o computador só entende 0 e 1 — e como isso vira tudo.

---

## Por que Binário?

**Shannon (1948):** um sistema com 2 estados (0/1) é o mais robusto contra ruído elétrico.

| Conceito | Definição |
|----------|----------|
| **Bit** | Menor unidade de informação (0 ou 1) |
| **Byte** | 8 bits = 256 combinações (2⁸) |
| **Palavra** | 32 ou 64 bits (largura nativa do processador) |

1 KB = 1.024 bytes | 1 MB = 1.024 KB | 1 GB = 1.024 MB

---

## Sistemas de Numeração — Fórmula Geral

$$N = \sum_{i} d_i \times b^i$$

| Base | Nome | Dígitos | Uso |
|------|------|---------|-----|
| 2 | Binário | 0, 1 | Representação interna |
| 8 | Octal | 0–7 | Permissões Unix |
| 10 | Decimal | 0–9 | Cotidiano humano |
| 16 | Hexadecimal | 0–F | Cores, endereços de memória |

---

## Conversão: Decimal → Binário

**Método:** divisões sucessivas por 2, ler restos de baixo para cima.

**Exemplo: 45₁₀ → binário:**

| Divisão | Quociente | Resto |
|---------|----------|-------|
| 45 ÷ 2 | 22 | **1** |
| 22 ÷ 2 | 11 | **0** |
| 11 ÷ 2 | 5 | **1** |
| 5 ÷ 2 | 2 | **1** |
| 2 ÷ 2 | 1 | **0** |
| 1 ÷ 2 | 0 | **1** |

**Resultado:** 45₁₀ = **101101₂**

---

## Conversão: Binário ↔ Hexadecimal

Agrupar bits em blocos de 4 (da direita pra esquerda):

```
1011 0011 1010₂
  B    3    A₁₆

Resultado: 0xB3A
```

| 4 bits | Hex |  | 4 bits | Hex |
|--------|-----|--|--------|-----|
| 0000 | 0 | | 1000 | 8 |
| 0001 | 1 | | 1001 | 9 |
| 0010 | 2 | | 1010 | A |
| 0011 | 3 | | 1011 | B |
| 0100 | 4 | | 1100 | C |
| 0101 | 5 | | 1101 | D |
| 0110 | 6 | | 1110 | E |
| 0111 | 7 | | 1111 | F |

---

## Complemento de 2

Representação padrão para **inteiros com sinal** em computadores.

**Para representar -45 em 8 bits:**

1. +45 = `00101101`
2. Inverter: `11010010`
3. Somar 1: `11010011` ← este é **-45**

**Vantagem:** soma de positivo + negativo funciona com o mesmo circuito da ULA (sem circuito separado para subtração).

---

## IEEE 754 — Ponto Flutuante

**32 bits (precisão simples):**

| Sinal | Expoente (8 bits) | Mantissa (23 bits) |
|-------|-------------------|-------------------|
| 1 bit | bias = 127 | fração normalizada |

**Por que `0.1 + 0.2 ≠ 0.3`?**

0.1 em binário é dízima periódica (0.0001100110011...).
O truncamento na mantissa gera erro de arredondamento.

> **Goldberg (1991):** "What Every Computer Scientist Should Know About Floating-Point Arithmetic"

---

## Caso Real: Ariane 5 (1996)

- Foguete de US$ 370 milhões explodiu 37 segundos após lançamento.
- **Causa:** conversão de float 64-bit para inteiro 16-bit → overflow.
- Valor de velocidade excedeu 32.767 (máximo de int16).
- **Lição:** representação de dados não é detalhe — é infraestrutura.

---

## Codificação de Texto

| Padrão | Bits/caractere | Cobertura |
|--------|---------------|----------|
| ASCII | 7 (128 chars) | Inglês básico |
| ISO 8859-1 | 8 (256 chars) | Europeu ocidental |
| Unicode | Variável | 154.998 caracteres, 168 scripts |
| UTF-8 | 1–4 bytes | Compatível com ASCII, padrão da web |

**UTF-8:** "A" = 1 byte, "ç" = 2 bytes, "漢" = 3 bytes, "😀" = 4 bytes

---

## Codificação de Imagem e Áudio

**Imagem não comprimida (bitmap):**
$$\text{Tamanho} = \text{largura} \times \text{altura} \times \text{profundidade de cor}$$

Ex: 1920×1080 × 3 bytes (RGB) = **5.93 MB** por frame

**Áudio (PCM):**
$$\text{Tamanho} = \text{taxa} \times \text{bits} \times \text{canais} \times \text{segundos}$$

Ex: 44.100 Hz × 16 bits × 2 ch × 60 seg = **10.09 MB/min**

---

## Referências-chave

- Shannon, C. (1948). A Mathematical Theory of Communication
- Goldberg, D. (1991). What Every Computer Scientist Should Know About Floating-Point Arithmetic
- Tanenbaum, A. (2013). *Structured Computer Organization*
- Unicode Consortium. unicode.org

---

## Checkpoint

**→ Checkpoint 02** (com módulo 03)
Conversões de base, aritmética binária, complemento de 2, IEEE 754, codificação UTF-8.
