# Slides da Disciplina

Apresentações em Markdown compatíveis com **[Marp](https://marp.app/)** — exportáveis para PDF, PPTX e HTML.

---

## Arquivos

| Slide | Módulo | Conteúdo |
|-------|--------|---------|
| [01-pensamento-computacional.md](01-pensamento-computacional.md) | 01 | 4 pilares, computabilidade, aplicações |
| [02-logica-algoritmos.md](02-logica-algoritmos.md) | 02 | Böhm-Jacopini, lógica, fluxogramas, trace table |
| [03-hardware-arquitetura.md](03-hardware-arquitetura.md) | 03 | Von Neumann, hierarquia de memória, CISC/RISC |
| [04-dados-numeracao.md](04-dados-numeracao.md) | 04 | Conversões, complemento de 2, IEEE 754, UTF-8 |
| [05-sistemas-operacionais.md](05-sistemas-operacionais.md) | 05 | Processos, escalonamento, paginação, terminal |
| [06-cloud-computing.md](06-cloud-computing.md) | 06 | NIST, modelos de serviço, SLA, CAP, FinOps |
| [07-inteligencia-artificial.md](07-inteligencia-artificial.md) | 07 | Paradigmas, ML, Deep Learning, viés, EU AI Act |
| [08-ia-generativa.md](08-ia-generativa.md) | 08 | LLMs, alucinação, prompt engineering, uso responsável |

---

## Como usar

### VS Code (recomendado)

1. Instale a extensão **Marp for VS Code**.
2. Abra qualquer arquivo `.md` da pasta `slides/`.
3. Clique no ícone de preview (Marp) no canto superior direito.
4. Para exportar: `Ctrl+Shift+P` → "Marp: Export Slide Deck" → escolha PDF, PPTX ou HTML.

### CLI (linha de comando)

```bash
# Instalar Marp CLI
npm install -g @marp-team/marp-cli

# Exportar para PDF
marp slides/01-pensamento-computacional.md --pdf

# Exportar todos para PDF
for f in slides/*.md; do marp "$f" --pdf; done

# Exportar para HTML (interativo)
marp slides/01-pensamento-computacional.md --html

# Exportar para PPTX
marp slides/01-pensamento-computacional.md --pptx
```

---

## Design

- **Tema:** dark (fundo `#1a1a2e`, texto `#eaeaea`, destaque `#e94560`).
- **Estilo:** cada `---` separa um slide.
- **Conteúdo:** objetivo e visual — tabelas, diagramas ASCII, listas curtas.
- **Paginação:** habilitada automaticamente.

---

## Customização

Para alterar o tema, edite o frontmatter YAML no topo de cada arquivo:

```yaml
---
marp: true
theme: default          # ou 'gaia', 'uncover'
paginate: true
backgroundColor: #fff   # fundo claro
color: #333             # texto escuro
---
```

Consulte a [documentação do Marp](https://marpit.marp.app/) para temas e diretivas avançadas.
