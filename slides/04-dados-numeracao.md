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

# 🔢 Dados e Sistemas de Numeração

**Introdução à Computação · ADS**

*Por que o computador só entende 0 e 1 — e como isso vira tudo*

![bg right:40% brightness:0.6](https://images.unsplash.com/photo-1526374965328-7f61d4dc18c5?w=600&h=400&fit=crop)

---

## 💡 Por que Binário?

**Shannon (1948):** dois estados (0/1) é o mais robusto contra ruído elétrico.

| Conceito | Definição |
|----------|----------|
| **Bit** | 0 ou 1 — menor unidade |
| **Byte** | 8 bits = 256 combinações |
| **Palavra** | 32 ou 64 bits (largura da CPU) |

`1 KB = 1.024 B` · `1 MB = 1.024 KB` · `1 GB = 1.024 MB`

---

## 🔄 Sistemas de Numeração

$$N = \sum_{i} d_i \times b^i$$

| Base | Nome | Dígitos | Uso típico |
|:----:|------|---------|-----------|
| 2 | Binário | 0–1 | Representação interna |
| 8 | Octal | 0–7 | Permissões Unix |
| 10 | Decimal | 0–9 | Cotidiano humano |
| 16 | Hex | 0–F | Cores, endereços |

---

## ➗ Decimal → Binário

Divisões sucessivas por 2, **restos de baixo p/ cima**:

```
45 ÷ 2 = 22 r 1
22 ÷ 2 = 11 r 0
11 ÷ 2 =  5 r 1     ▲ leitura
 5 ÷ 2 =  2 r 1     │
 2 ÷ 2 =  1 r 0     │
 1 ÷ 2 =  0 r 1     │
```

**45₁₀ = `101101`₂**

---

## 🔗 Binário ↔ Hexadecimal

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

## ➖ Complemento de 2

Representação padrão de **inteiros com sinal**.

**Representar −45 em 8 bits:**

```
 +45 =  00101101
 Inv →  11010010
  +1 →  11010011  ← este é -45
```

✅ Soma de positivo + negativo usa **o mesmo circuito** da ULA.

---

## 🎯 IEEE 754 — Ponto Flutuante

**32 bits (precisão simples):**

| Sinal (1) | Expoente (8) | Mantissa (23) |
|:---------:|:-----------:|:------------:|
| `0` ou `1` | bias = 127 | fração normalizada |

### Por que `0.1 + 0.2 ≠ 0.3`?

0.1 em binário é **dízima periódica** → truncamento → erro.

---

## 💥 Caso Real — Ariane 5 (1996)

- 🚀 Foguete de **US$ 370 mi** explodiu em 37 segundos
- 🐛 **Causa:** float 64-bit → int 16-bit = *overflow*
- 📏 Velocidade excedeu 32.767 (máx de int16)

> Representação de dados não é detalhe — é **infraestrutura**.

![bg right:30% opacity:0.2](https://images.unsplash.com/photo-1457364559154-aa2644600ebb?w=400&fit=crop)

---

## 🔤 Codificação de Texto

| Padrão | Bits | Cobertura |
|--------|:----:|----------|
| ASCII | 7 | 128 chars — inglês |
| Unicode | variável | 155k+ chars, 168 scripts |
| **UTF-8** | 1–4 bytes | Padrão da web |

`"A"` = 1 byte · `"ç"` = 2 · `"漢"` = 3 · `"😀"` = 4

---

## 🖼️ Imagem e Áudio

**Imagem (bitmap):**
$$\text{Tamanho} = W \times H \times \text{profundidade}$$
📸 1920×1080 × 3 B (RGB) ≈ **5.9 MB** / frame

**Áudio (PCM):**
$$\text{Tamanho} = \text{taxa} \times \text{bits} \times \text{canais} \times \text{seg}$$
🎵 44.1 kHz × 16 bit × 2 ch × 60 s ≈ **10 MB** / min

---

## 📚 Referências

- Shannon (1948). *A Mathematical Theory of Communication*
- Goldberg (1991). *What Every CS Should Know About FP Arithmetic*
- Unicode Consortium — unicode.org

**→ Checkpoint 02** · com módulo 03
