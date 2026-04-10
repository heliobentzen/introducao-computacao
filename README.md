# Introdução à Computação

**Curso:** Análise e Desenvolvimento de Sistemas  
**Carga Horária:** 40 aulas de 45 minutos (30h)  
**Avaliações:** 2 unidades  

---

## Navegação Rápida

| Seção | Acesso |
|-------|--------|
| 📚 Conteúdo teórico | [conteudo/](conteudo/) |
| 🧪 Práticas e checkpoints | [praticas/](praticas/) |
| 🖥️ Slides (Marp) | [slides/](slides/) |
| 🛠️ Recursos e ferramentas | [recursos/](recursos/) |

---

## Trilha de Aprendizagem

```mermaid
flowchart LR
    A([🚀 Início]) --> M01
    M01["📖 01 · Pensamento\nComputacional"] --> M02
    M02["📖 02 · Lógica &\nAlgoritmos"] --> CP1{{"✅ Checkpoint 1"}}
    CP1 --> M03
    M03["📖 03 · Hardware &\nArquitetura"] --> M04
    M04["📖 04 · Dados &\nNumeração"] --> CP2{{"✅ Checkpoint 2"}}
    CP2 --> M05
    M05["📖 05 · Sistemas\nOperacionais"] --> M06
    M06["📖 06 · Cloud\nComputing"] --> CP3{{"✅ Checkpoint 3"}}
    CP3 --> M07
    M07["📖 07 · Inteligência\nArtificial"] --> M08
    M08["📖 08 · IA Generativa\nResponsável"] --> CP4{{"✅ Checkpoint 4"}}
    CP4 --> Z([🎓 Conclusão])

    style A fill:#4CAF50,color:#fff
    style Z fill:#2196F3,color:#fff
    style CP1 fill:#FF9800,color:#fff
    style CP2 fill:#FF9800,color:#fff
    style CP3 fill:#FF9800,color:#fff
    style CP4 fill:#FF9800,color:#fff
```

---

## Módulos de Conteúdo

| # | Módulo | Conteúdo | Slides | Checkpoint |
|---|--------|---------|--------|-----------|
| 01 | [Fundamentos e Pensamento Computacional](conteudo/01-fundamentos-pensamento-computacional.md) | Computação, 4 pilares, algoritmos, computabilidade | [Slides](slides/01-pensamento-computacional.md) | [CP 01](praticas/checkpoints/checkpoint-01.md) |
| 02 | [Lógica, Algoritmos e Fluxo](conteudo/02-logica-algoritmos-fluxo.md) | Estruturas de controle, pseudocódigo, fluxogramas, teste de mesa | [Slides](slides/02-logica-algoritmos.md) | [CP 01](praticas/checkpoints/checkpoint-01.md) |
| 03 | [Hardware e Arquitetura](conteudo/03-hardware-arquitetura.md) | Von Neumann, CPU, hierarquia de memória, CISC/RISC | [Slides](slides/03-hardware-arquitetura.md) | [CP 02](praticas/checkpoints/checkpoint-02.md) |
| 04 | [Dados e Sistemas de Numeração](conteudo/04-dados-numeracao.md) | Binário, conversões, complemento de 2, IEEE 754, codificação | [Slides](slides/04-dados-numeracao.md) | [CP 02](praticas/checkpoints/checkpoint-02.md) |
| 05 | [Sistemas Operacionais](conteudo/05-sistemas-operacionais.md) | Processos, escalonamento, memória virtual, terminal | [Slides](slides/05-sistemas-operacionais.md) | [CP 03](praticas/checkpoints/checkpoint-03.md) |
| 06 | [Cloud Computing](conteudo/06-cloud-computing.md) | NIST, IaaS/PaaS/SaaS, nuvem híbrida, FinOps | [Slides](slides/06-cloud-computing.md) | [CP 03](praticas/checkpoints/checkpoint-03.md) |
| 07 | [Inteligência Artificial](conteudo/07-inteligencia-artificial.md) | Paradigmas de IA, ML, Deep Learning, ética | [Slides](slides/07-inteligencia-artificial.md) | [CP 04](praticas/checkpoints/checkpoint-04.md) |
| 08 | [IA Generativa Responsável](conteudo/08-ia-generativa-responsavel.md) | LLMs, prompt engineering, alucinação, uso ético | [Slides](slides/08-ia-generativa.md) | [CP 04](praticas/checkpoints/checkpoint-04.md) |

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
