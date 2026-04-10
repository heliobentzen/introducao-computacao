# Guia de Ferramentas

Stack recomendada para a disciplina de Introdução à Computação — ADS.

---

## Ferramentas essenciais

| Categoria | Ferramenta | Para que serve | Como instalar |
|-----------|-----------|---------------|--------------|
| **Editor de código** | VS Code | Edição de markdown, pseudocódigo, HTML | [code.visualstudio.com](https://code.visualstudio.com) |
| **Terminal** | Bash (Linux/macOS), WSL ou Git Bash (Windows) | Prática de comandos de SO (módulo 05) | WSL: `wsl --install` no PowerShell |
| **Versionamento** | Git + GitHub | Controle de versão, entrega de atividades | [git-scm.com](https://git-scm.com) |
| **Diagramas** | draw.io / Mermaid / Excalidraw | Fluxogramas, diagramas de arquitetura | draw.io: [app.diagrams.net](https://app.diagrams.net) |
| **Planejamento** | GitHub Projects / Trello / Notion | Kanban, sprints do projeto integrador | Integrado no GitHub |
| **Apresentações** | Marp (Markdown → slides) | Slides técnicos exportáveis | Extensão VS Code: Marp for VS Code |

---

## Ferramentas de IA (com orientações de uso)

| Ferramenta | Tipo | Acesso | Observação |
|-----------|------|--------|-----------|
| ChatGPT | Chat LLM | [chat.openai.com](https://chat.openai.com) | Free tier disponível; versão Plus para GPT-4 |
| Claude | Chat LLM | [claude.ai](https://claude.ai) | Bom para textos longos e análise |
| Gemini | Chat LLM | [gemini.google.com](https://gemini.google.com) | Integração com Google Workspace |
| GitHub Copilot | Code assistant | Extensão VS Code | Free para estudantes via GitHub Education |
| Perplexity | Busca com IA (RAG) | [perplexity.ai](https://perplexity.ai) | Cita fontes automaticamente — bom para verificação |

**Regra:** IA é ferramenta de apoio. Sempre verificar resultados, nunca submeter output bruto como trabalho autoral.

---

## Extensões VS Code recomendadas

| Extensão | Utilidade |
|----------|----------|
| Marp for VS Code | Criar slides em markdown |
| Markdown All in One | Preview e atalhos para markdown |
| Draw.io Integration | Diagramas dentro do VS Code |
| GitLens | Histórico detalhado de Git |
| Live Server | Preview de HTML local |
| Mermaid Editor | Preview de diagramas Mermaid |
| WSL | Integração com Windows Subsystem for Linux |

---

## Cloud (free tier para estudantes)

| Provedor | Programa | O que inclui | Link |
|----------|---------|-------------|------|
| AWS | AWS Educate / Free Tier | EC2, S3, Lambda gratuitos por 12 meses | [aws.amazon.com/free](https://aws.amazon.com/free) |
| Azure | Azure for Students | US$ 100 em créditos + serviços gratuitos | [azure.microsoft.com/free/students](https://azure.microsoft.com/en-us/free/students) |
| Google Cloud | Google Cloud Free Tier | US$ 300 em créditos por 90 dias | [cloud.google.com/free](https://cloud.google.com/free) |

---

## Boas práticas operacionais

### Git

1. **Commits pequenos** com mensagem descritiva (`feat: adiciona pseudocódigo do checkout`).
2. **README atualizado** em toda atividade.
3. **Issues** para registrar dúvidas, bugs e ideias.
4. **Branches** para experimentos (`feature/prototipo-ia`).
5. Nunca commitar senhas, tokens ou chaves de API.

### Organização de repositório

```
meu-projeto/
├── README.md          ← Visão geral + como rodar
├── docs/              ← Documentação técnica
├── prototipos/        ← Figma exports, HTML, screenshots
├── src/               ← Código fonte (quando houver)
└── .gitignore         ← Arquivos a ignorar
```

### Checklist de entrega (use antes de submeter)

- [ ] O problema está bem descrito?
- [ ] O raciocínio está explícito (não apenas o resultado)?
- [ ] A solução foi testada com pelo menos 2 cenários?
- [ ] Os limites e riscos foram discutidos?
- [ ] Se usou IA, está citada e verificada?
- [ ] O README está atualizado?
- [ ] Todos os membros commitaram?

---

## Conversões e cálculos rápidos (referência)

| Ferramenta online | Uso |
|------------------|-----|
| [RapidTables Converter](https://www.rapidtables.com/convert/number/) | Conversão de bases (bin/oct/dec/hex) |
| [IEEE 754 Visualization](https://www.h-schmidt.net/FloatConverter/IEEE754.html) | Visualizador interativo de ponto flutuante |
| [CyberChef](https://gchq.github.io/CyberChef/) | Codificação/decodificação (ASCII, UTF-8, Base64) |
| [Explain Shell](https://explainshell.com/) | Explicação de comandos Unix |
