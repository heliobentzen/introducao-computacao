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

## Módulo 04 · Representação de Dados e Sistemas de Numeração

**Prof. Hélio Bentzen**
IFPE · Análise e Desenvolvimento de Sistemas

---

# Dados e Sistemas de Numeração

---

## Por que Binário?

**Shannon (1948):** dois estados (0/1) é o mais robusto contra ruído elétrico.

| Conceito | Definição |
|----------|----------|
| **Bit** | 0 ou 1, menor unidade |
| **Byte** | 8 bits = 256 combinações |
| **Palavra** | 32 ou 64 bits (largura da CPU) |

`1 KB = 1.024 B` · `1 MB = 1.024 KB` · `1 GB = 1.024 MB`

---

## Sistemas de Numeração

$$N = \sum_{i} d_i \times b^i$$

| Base | Nome | Dígitos | Uso típico |
|:----:|------|---------|-----------|
| 2 | Binário | 0–1 | Representação interna |
| 8 | Octal | 0–7 | Permissões Unix |
| 10 | Decimal | 0–9 | Cotidiano humano |
| 16 | Hex | 0–F | Cores, endereços |

---

## Decimal → Binário

Divisões sucessivas por 2, **restos de baixo p/ cima**:

```
45 ÷ 2 = 22 r 1
22 ÷ 2 = 11 r 0
11 ÷ 2 =  5 r 1     ▲ leitura
 5 ÷ 2 =  2 r 1     │
 2 ÷ 2 =  1 r 0     │
 1 ÷ 2 =  0 r 1     │
```

Resultado: 45₁₀ = **`101101`₂**

---

## Binário ↔ Hexadecimal

Agrupar em **blocos de 4 bits** (direita → esquerda):

```
  1011   0011   1010
   B      3      A     →  0xB3A
```

| Bits | Hex | | Bits | Hex |
|------|:---:|-|------|:---:|
| 0000 | 0 | | 1000 | 8 |
| 0001 | 1 | | 1001 | 9 |
| 0010 | 2 | | 1010 | A |
| 0011 | 3 | | 1011 | B |
| 0100–0111 | 4–7 | | 1100–1111 | C–F |

---

## Complemento de 2

Representação padrão de **inteiros com sinal**.

Representar −45 em 8 bits:

```
 +45 =  00101101
 Inv →  11010010
  +1 →  11010011  ← este é -45
```

- Soma de positivo + negativo usa **o mesmo circuito** da ULA.

---

## IEEE 754: Ponto Flutuante

32 bits (precisão simples):

| Sinal (1) | Expoente (8) | Mantissa (23) |
|:---------:|:-----------:|:------------:|
| `0` ou `1` | bias = 127 | fração normalizada |

### Por que `0.1 + 0.2 ≠ 0.3`?

0.1 em binário é **dízima periódica** → truncamento → erro.

---

## Caso Real: Ariane 5 (1996)

- Foguete de **US$ 370 mi** explodiu em 37 segundos
- Causa: float 64-bit → int 16-bit = **overflow**
- Velocidade excedeu 32.767 (máx de int16)

> Representação de dados não é detalhe, é **infraestrutura**.

---

## Codificação de Texto

| Padrão | Bits | Cobertura |
|--------|:----:|----------|
| ASCII | 7 | 128 chars, inglês |
| Unicode | variável | 155k+ chars, 168 scripts |
| **UTF-8** | 1–4 bytes | Padrão da web |

`"A"` = 1 byte · `"ç"` = 2 · `"漢"` = 3 · `"emoji"` = 4

---

## Imagem e Áudio

**Imagem (bitmap):**
$$\text{Tamanho} = W \times H \times \text{profundidade}$$
1920×1080 × 3 B (RGB) ≈ **5.9 MB** / frame

**Áudio (PCM):**
$$\text{Tamanho} = \text{taxa} \times \text{bits} \times \text{canais} \times \text{seg}$$
44.1 kHz × 16 bit × 2 ch × 60 s ≈ **10 MB** / min

---

## Referências

- Shannon (1948). *A Mathematical Theory of Communication*
- Goldberg (1991). *What Every CS Should Know About FP Arithmetic*
- Unicode Consortium: unicode.org

**→ Checkpoint 02** · com módulo 03
