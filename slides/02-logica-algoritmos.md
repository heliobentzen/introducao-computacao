---
marp: true
theme: default
paginate: true
backgroundColor: #1a1a2e
color: #eaeaea
style: |
  section {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }
  h1 { color: #e94560; }
  h2 { color: #fff; background: #e94560; padding: 4px 16px; border-radius: 4px; }
  table { font-size: 0.78em; }
  code { background: #16213e; color: #e94560; }
  a { color: #00d2ff; }
  blockquote { border-left: 4px solid #e94560; color: #ccc; }
---

# 02 — Lógica, Algoritmos e Controle de Fluxo

**Introdução à Computação — ADS**
Estruturar. Decidir. Repetir. Testar.

---

## Teorema de Böhm-Jacopini (1966)

> Todo algoritmo computável pode ser expresso com apenas **3 estruturas**:

1. **Sequência** — passos executados em ordem
2. **Seleção** — decisão (SE / SENÃO)
3. **Iteração** — repetição (ENQUANTO / PARA)

Não precisa de GOTO. Toda lógica se resolve com essas três.

---

## Lógica Proposicional — Base

| Operador | Símbolo | Exemplo |
|----------|---------|---------|
| E (AND) | ∧ | `idade ≥ 18 ∧ habilitado = V` |
| OU (OR) | ∨ | `vip = V ∨ convidado = V` |
| NÃO (NOT) | ¬ | `¬ bloqueado` |

**Tabela verdade (AND):**

| A | B | A ∧ B |
|---|---|-------|
| V | V | **V** |
| V | F | F |
| F | V | F |
| F | F | F |

---

## Leis de De Morgan

Essenciais para simplificar condicionais:

```
¬(A ∧ B) = ¬A ∨ ¬B
¬(A ∨ B) = ¬A ∧ ¬B
```

**Exemplo prático:**

```
SE NÃO (logado E admin) → equivale a
SE (NÃO logado OU NÃO admin)
```

Útil para refatorar condições complexas.

---

## Estrutura Condicional

```
SE nota >= 7.0 ENTÃO
    resultado ← "Aprovado"
SENÃO SE nota >= 5.0 ENTÃO
    resultado ← "Recuperação"
SENÃO
    resultado ← "Reprovado"
FIM SE
```

**Boas práticas:**

- Testar condição mais restritiva primeiro
- Evitar condicionais aninhados > 3 níveis
- Usar ESCOLHA/CASO quando muitas opções

---

## Laços de Repetição

| Tipo | Quando usar | Teste |
|------|------------|-------|
| `ENQUANTO` | Não sabe quantas vezes | Antes (pode não executar) |
| `REPITA...ATÉ` | Pelo menos 1 vez | Depois |
| `PARA` | Sabe o número de iterações | Contagem definida |

```
PARA i DE 1 ATÉ 10 FAÇA
    ESCREVA(i * 3)
FIM PARA
// Saída: 3, 6, 9, ..., 30
```

---

## Exemplo Evolutivo — Calculadora de Notas

**v1 — Sequência simples:**

```
LER nota1, nota2
media ← (nota1 + nota2) / 2
ESCREVER media
```

**v2 — Com decisão:**

```
SE media >= 7 ENTÃO "Aprovado"
SENÃO SE media >= 5 ENTÃO "Recuperação"
SENÃO "Reprovado"
```

---

## Exemplo Evolutivo (continuação)

**v3 — Com laço (turma inteira):**

```
PARA aluno DE 1 ATÉ 40 FAÇA
    LER nota1, nota2
    media ← (nota1 + nota2) / 2
    classificar(media)
FIM PARA
```

**v4 — Com validação:**

```
REPITA
    LER nota
ATÉ (nota >= 0 E nota <= 10)  // rejeita entradas inválidas
```

---

## Fluxograma — Padrão ISO 5807

| Símbolo | Significado |
|---------|-----------|
| ⬭ Oval | Início / Fim |
| ▭ Retângulo | Processo |
| ◇ Losango | Decisão |
| ▱ Paralelogramo | Entrada / Saída |

**Regra:** fluxograma deve ser legível sem o pseudocódigo.
Cada caminho deve terminar em um ponto definido.

---

## Trace Table — Depuração Manual

Simula a execução passo a passo:

| Passo | i | soma | i ≤ 3? |
|-------|---|------|--------|
| 0 | 1 | 0 | V |
| 1 | 1 | 1 | V |
| 2 | 2 | 3 | V |
| 3 | 3 | 6 | F → sai |

**Resultado:** soma = 6

Trace tables encontram bugs **antes** de executar código.

---

## Referências-chave

- Böhm & Jacopini (1966). Flow diagrams, Turing machines and languages
- Cormen et al. (2022). *Introduction to Algorithms* (4ª ed.)
- Forbellone & Eberspächer (2022). *Lógica de Programação* (4ª ed.)
- ISO 5807:1985 — Documentation symbols for flowcharts

---

## Checkpoint

**→ Checkpoint 01** (com módulo 01)
Farmácia + medicamentos controlados: pseudocódigo completo, fluxograma ISO, trace table.
