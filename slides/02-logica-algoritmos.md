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

# ⚙️ Lógica, Algoritmos e Fluxo

**Introdução à Computação · ADS**

*Estruturar · Decidir · Repetir · Testar*

![bg right:40% brightness:0.7](https://images.unsplash.com/photo-1509228627152-72ae9ae6848d?w=600&h=400&fit=crop)

---

## 🧱 Teorema de Böhm–Jacopini (1966)

Todo algoritmo computável usa **apenas 3 estruturas**:

| # | Estrutura | Significado |
|:-:|-----------|------------|
| 1️⃣ | **Sequência** | Passos em ordem |
| 2️⃣ | **Seleção** | Decisão (SE / SENÃO) |
| 3️⃣ | **Iteração** | Repetição (ENQUANTO / PARA) |

> Sem GOTO. Toda lógica se resolve com essas três.

---

## 🔣 Lógica Proposicional

| Operador | Símbolo | Exemplo |
|----------|:-------:|---------|
| E (AND)  | ∧ | `idade ≥ 18 ∧ habilitado` |
| OU (OR)  | ∨ | `vip ∨ convidado` |
| NÃO (NOT)| ¬ | `¬bloqueado` |

**Leis de De Morgan** — simplificam condicionais:

```
¬(A ∧ B)  =  ¬A ∨ ¬B
¬(A ∨ B)  =  ¬A ∧ ¬B
```

---

## 🔀 Estrutura Condicional

```
SE nota >= 7.0 ENTÃO
    resultado ← "Aprovado"
SENÃO SE nota >= 5.0 ENTÃO
    resultado ← "Recuperação"
SENÃO
    resultado ← "Reprovado"
FIM SE
```

💡 **Boas práticas:**

- Condição mais restritiva primeiro
- Evitar aninhamento > 3 níveis

---

## 🔁 Laços de Repetição

| Tipo | Quando usar | Teste |
|------|------------|:-----:|
| `ENQUANTO` | Não sabe quantas vezes | Antes |
| `REPITA…ATÉ` | Pelo menos 1 vez | Depois |
| `PARA` | Quantidade definida | Contagem |

```
PARA i DE 1 ATÉ 5 FAÇA
    ESCREVA(i * 3)       ⟶ 3, 6, 9, 12, 15
FIM PARA
```

---

## 📈 Exemplo Evolutivo — Notas

**v1 — Sequência:**

```
media ← (nota1 + nota2) / 2
```

**v2 — Com decisão:**

```
SE media >= 7 → "Aprovado"
SENÃO SE media >= 5 → "Recuperação"
```

**v3 — Com laço (turma):**

```
PARA aluno DE 1 ATÉ 40 FAÇA …
```

---

## 📐 Fluxograma — ISO 5807

| Símbolo | Significado |
|:-------:|-----------|
| ⬭ Oval | Início / Fim |
| ▭ Retângulo | Processo |
| ◇ Losango | Decisão |
| ▱ Paralelogramo | Entrada / Saída |

> Fluxograma deve ser legível **sem** o pseudocódigo.

![bg right:30% opacity:0.15](https://images.unsplash.com/photo-1454165804606-c3d57bc86b40?w=400&fit=crop)

---

## 🔎 Trace Table — Depuração Manual

Simula execução passo a passo — encontra bugs **antes** de rodar.

| Passo | i | soma | i ≤ 3? |
|:-----:|:-:|:----:|:------:|
| 0 | 1 | 0 | ✅ |
| 1 | 1 | 1 | ✅ |
| 2 | 2 | 3 | ✅ |
| 3 | 3 | 6 | ❌ sai |

**Resultado:** `soma = 6`

---

## 📚 Referências

- Böhm & Jacopini (1966). *Flow diagrams, Turing machines*
- Cormen et al. (2022). *Introduction to Algorithms*, 4ª ed.
- ISO 5807:1985 — Flowchart symbols

**→ Checkpoint 01** · com módulo 01
