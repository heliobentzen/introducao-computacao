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

## Módulo 02 · Lógica, Algoritmos e Controle de Fluxo

**Prof. Hélio Bentzen**
IFPE · Análise e Desenvolvimento de Sistemas

---

# Lógica, Algoritmos e Fluxo

---

## Teorema de Böhm–Jacopini (1966)

Todo algoritmo computável usa **apenas 3 estruturas**:

| # | Estrutura | Significado |
|:-:|-----------|------------|
| 1 | **Sequência** | Passos em ordem |
| 2 | **Seleção** | Decisão (SE / SENÃO) |
| 3 | **Iteração** | Repetição (ENQUANTO / PARA) |

> Sem GOTO. Toda lógica se resolve com essas três.

---

## Lógica Proposicional

| Operador | Símbolo | Exemplo |
|----------|:-------:|---------|
| E (AND)  | ∧ | `idade ≥ 18 ∧ habilitado` |
| OU (OR)  | ∨ | `vip ∨ convidado` |
| NÃO (NOT)| ¬ | `¬bloqueado` |

**Leis de De Morgan**, simplificam condicionais:

```
¬(A ∧ B)  =  ¬A ∨ ¬B
¬(A ∨ B)  =  ¬A ∧ ¬B
```

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

Boas práticas:

- Condição mais restritiva **primeiro**
- Evitar aninhamento > 3 níveis

---

## Laços de Repetição

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

## Exemplo Evolutivo: Notas

**v1: Sequência:**

```
media ← (nota1 + nota2) / 2
```

**v2: Com decisão:**

```
SE media >= 7 → "Aprovado"
SENÃO SE media >= 5 → "Recuperação"
```

**v3: Com laço (turma):**

```
PARA aluno DE 1 ATÉ 40 FAÇA …
```

---

## Fluxograma: ISO 5807

| Símbolo | Significado |
|:-------:|-----------|
| ⬭ Oval | Início / Fim |
| ▭ Retângulo | Processo |
| ◇ Losango | Decisão |
| ▱ Paralelogramo | Entrada / Saída |

> Fluxograma deve ser legível **sem** o pseudocódigo.

---

## Trace Table: Depuração Manual

Simula execução passo a passo, encontra bugs **antes** de rodar.

| Passo | i | soma | i ≤ 3? |
|:-----:|:-:|:----:|:------:|
| 0 | 1 | 0 | Sim |
| 1 | 1 | 1 | Sim |
| 2 | 2 | 3 | Sim |
| 3 | 3 | 6 | Não, sai |

Resultado: `soma = 6`

---

## Referências

- Böhm & Jacopini (1966). *Flow diagrams, Turing machines*
- Cormen et al. (2022). *Introduction to Algorithms*, 4ª ed.
- ISO 5807:1985, Flowchart symbols

**→ Checkpoint 01** · com módulo 01
