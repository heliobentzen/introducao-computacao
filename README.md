# Introdução à Computação

**Curso:** Análise e Desenvolvimento de Sistemas  
**Carga Horária:** 40 aulas de 45 minutos (30h)  
**Avaliações:** 2 unidades  

---

## Ementa

- Conceitos fundamentais e pensamento computacional  
- Evolução da computação e arquitetura de computadores  
- Representação de dados e sistemas de numeração  
- Sistemas operacionais modernos e gerenciamento de recursos  
- Fundamentos de Computação em Nuvem (Cloud Computing) e infraestrutura como serviço  
- Introdução à Inteligência Artificial e suas aplicações computacionais  
- Uso prático de IA Generativa e ferramentas baseadas em LLMs como assistentes de produtividade  

---

## Objetivos

**Geral:**  
Apresentar ao estudante os fundamentos da computação, desde conceitos básicos até tecnologias contemporâneas como cloud computing e inteligência artificial, capacitando-o a compreender o ecossistema tecnológico atual e a utilizar ferramentas modernas com senso crítico.

**Específicos:**

- Compreender o conceito de pensamento computacional e sua aplicação na resolução de problemas  
- Conhecer a evolução histórica dos computadores e os princípios da arquitetura de Von Neumann  
- Realizar conversões entre sistemas de numeração e entender a representação interna de dados  
- Identificar as principais funções de um sistema operacional moderno  
- Entender os modelos de serviço em nuvem e os principais provedores do mercado  
- Distinguir os diferentes paradigmas de IA e suas aplicações práticas  
- Utilizar ferramentas de IA generativa com eficiência no contexto profissional  

---

## Conteúdo Programático

### Unidade I — Fundamentos e Infraestrutura (Aulas 1–20)

| Aula(s) | Tópico |
|---------|--------|
| 1 | Apresentação da disciplina. O que é computação? Panorama do mercado de TI |
| 2 | Pensamento computacional: decomposição, reconhecimento de padrões, abstração e algoritmos |
| 3 | Algoritmos e fluxogramas: representação e resolução de problemas |
| 4 | Lógica de programação: estruturas básicas de controle |
| 5 | História da computação: das máquinas mecânicas às gerações de computadores |
| 6 | Arquitetura de Von Neumann: CPU, memória e barramento |
| 7 | Componentes de hardware: processadores, memória RAM, armazenamento (HDD/SSD) |
| 8 | Periféricos, interfaces e padrões de conectividade |
| 9 | Sistemas de numeração: decimal, binário, octal e hexadecimal |
| 10 | Conversões entre bases e operações aritméticas em binário |
| 11 | Representação de inteiros com sinal e ponto flutuante (IEEE 754) |
| 12 | Codificação de texto (ASCII, Unicode/UTF-8), imagens e áudio |
| 13 | Introdução aos sistemas operacionais: conceitos e histórico |
| 14 | Gerenciamento de processos e escalonamento |

---

## Orientações Gerais

### Para acompanhar a disciplina

1. **Leia o material antes da aula.** Os arquivos na pasta `conteudo/` cobrem o que será discutido em sala.  
2. **Faça as práticas.** Os roteiros em `praticas/` são autoexplicativos e podem ser feitos no laboratório ou em casa.  
3. **Use ferramentas de IA como apoio, não como substituto.** Entender o que elas produzem é sua responsabilidade.  
4. **Participe das discussões.** Computação muda rápido; traga referências e experiências reais.  
5. **Versione seu trabalho.** Use Git e GitHub para organizar suas práticas.  

---

### Ferramentas recomendadas

| Finalidade | Ferramenta |
|------------|------------|
| Editor de código | VS Code |
| Terminal / Shell | Bash (Linux/macOS) ou WSL (Windows) |
| Controle de versão | Git + GitHub |
| Cloud (free tier) | AWS Free Tier, Azure for Students, Google Cloud Free |
| IA generativa | ChatGPT, Gemini, Claude, GitHub Copilot |
| Diagramas e fluxogramas | draw.io, Mermaid, Excalidraw |
| Containers | Docker Desktop |

---

### Netiqueta e conduta

- Respeite colegas e professor em todos os canais de comunicação  
- Prazos de entrega serão comunicados com antecedência — organize-se  
- Dúvidas técnicas: abra uma _issue_ neste repositório ou use o canal oficial da turma  
- Problemas pessoais que afetem seu desempenho: converse com o professor antes da avaliação  

---

## Estrutura Didática do Repositório

```text
.
├── conteudo/
│   ├── README.md
│   ├── 01-fundamentos-pensamento-computacional.md
│   ├── 02-logica-algoritmos-fluxo.md
│   ├── 03-hardware-arquitetura.md
│   ├── 04-dados-numeracao.md
│   ├── 05-sistemas-operacionais.md
│   ├── 06-cloud-computing.md
│   ├── 07-inteligencia-artificial.md
│   └── 08-ia-generativa-responsavel.md
├── praticas/
│   ├── README.md
│   ├── checkpoints/
│   │   ├── checkpoint-01.md   → Módulos 01 + 02
│   │   ├── checkpoint-02.md   → Módulos 03 + 04
│   │   ├── checkpoint-03.md   → Módulos 05 + 06
│   │   └── checkpoint-04.md   → Módulos 07 + 08
│   ├── desafios/
│   │   ├── desafio-01-algoritmo-cotidiano.md   → Módulos 01–03
│   │   ├── desafio-02-cloud-na-vida-real.md    → Módulos 04–06
│   │   └── desafio-03-ia-com-cabeca.md         → Módulos 07–08
│   └── projeto-integrador/
│       ├── README.md
│       ├── sprint-0-onboarding.md
│       ├── sprint-1-modelagem.md
│       ├── sprint-2-infraestrutura.md
│       └── sprint-3-ia-pitch.md
├── recursos/
│   ├── guia-ferramentas.md
│   ├── metodologias-ativas.md
│   └── rubrica-avaliacao.md
└── slides/
    ├── README.md
    ├── 01-pensamento-computacional.md
    ├── 02-logica-algoritmos.md
    ├── 03-hardware-arquitetura.md
    ├── 04-dados-numeracao.md
    ├── 05-sistemas-operacionais.md
    ├── 06-cloud-computing.md
    ├── 07-inteligencia-artificial.md
    └── 08-ia-generativa.md
```

## Trilha de Aprendizagem (Como usar)

1. Comece pelo módulo teórico em `conteudo/` correspondente à semana.
2. Faça o `checkpoint` da semana para validar o entendimento.
3. Avance para um desafio em `praticas/desafios/`.
4. Aplique o aprendizado no `projeto-integrador/` em sprints.
5. Use os arquivos em `recursos/` para revisão, organização e melhoria contínua.

## Proposta Pedagógica

O material foi construído com referência em práticas modernas de ensino técnico e superior (universidades e plataformas de mercado), com linguagem acessível, abordagem mão na massa e foco em autonomia do estudante.

Objetivo: transformar a disciplina de entrada em ADS no ponto de partida mais importante do curso.
