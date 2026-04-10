# 07 — Introdução à Inteligência Artificial

## Objetivos de aprendizagem

Ao final deste módulo o estudante será capaz de:

- Definir inteligência artificial e situar o campo historicamente.
- Distinguir IA simbólica, aprendizado de máquina e aprendizado profundo.
- Explicar o ciclo básico de um sistema de ML: dados → treinamento → modelo → inferência.
- Identificar aplicações práticas de IA no desenvolvimento de software.
- Discutir limitações técnicas e implicações éticas com fundamentação.

---

## 1. O Que É Inteligência Artificial?

Não existe consenso universal sobre a definição de IA. Russell e Norvig (2021), no livro-texto mais adotado do mundo sobre o tema, organizam as definições em quatro quadrantes:

| | **Como humanos** | **Racionalmente** |
|---|---|---|
| **Pensando** | Modelar processos cognitivos humanos (ciência cognitiva) | Raciocinar com lógica formal (leis do pensamento) |
| **Agindo** | Passar no Teste de Turing (comportamento indistinguível de humano) | Agir de forma ótima dada a informação disponível (agentes racionais) |

A visão dominante atualmente é a do **agente racional:** um sistema que percebe o ambiente e toma ações que maximizam alguma medida de desempenho, dadas suas crenças e restrições.

### 1.1 Breve Cronologia

| Ano | Marco | Significado |
|-----|-------|-----------|
| 1943 | McCulloch & Pitts | Modelo matemático do neurônio artificial |
| 1950 | Turing publica "Computing Machinery and Intelligence" | Propõe o Teste de Turing — "As máquinas podem pensar?" |
| 1956 | Conferência de Dartmouth | O termo "Artificial Intelligence" é cunhado por McCarthy et al. |
| 1966 | ELIZA (Weizenbaum) | Primeiro chatbot — simulava terapeuta com casamento de padrões |
| 1969 | Perceptron de Minsky & Papert | Aponta limitações de redes neurais simples → "inverno da IA" |
| 1986 | Backpropagation (Rumelhart, Hinton & Williams) | Treinar redes neurais multicamada — renascimento das redes neurais |
| 1997 | Deep Blue vence Kasparov | IA vence campeão mundial de xadrez (abordagem de busca + heurísticas) |
| 2012 | AlexNet (Krizhevsky, Sutskever & Hinton) | Deep learning domina classificação de imagens → boom do DL |
| 2016 | AlphaGo (DeepMind) vence Lee Sedol | IA domina o Go — 10^170 posições possíveis, intratável por força bruta |
| 2017 | Transformer (Vaswani et al.) | Arquitetura que revoluciona NLP → base de GPT, BERT, etc. |
| 2020+ | GPT-3, DALL-E, ChatGPT, GPT-4, Gemini | IA generativa entra no mainstream |

### 1.2 Os "Invernos" da IA

A história da IA é marcada por ciclos de euforia e decepção:

- **1º Inverno (1974-1980):** promessas exageradas dos anos 60 não se concretizaram; cortes de financiamento.
- **2º Inverno (1987-1993):** sistemas especialistas caros e frágeis falharam fora de domínios restritos.

Cada inverno ensinou que IA funciona melhor quando expectativas são calibradas com as capacidades reais da tecnologia. Lição relevante para quem chega ao campo hoje.

---

## 2. Paradigmas de IA

### 2.1 IA Simbólica (GOFAI — Good Old-Fashioned AI)

Baseada em **manipulação explícita de símbolos e regras lógicas**. O conhecimento é codificado manualmente por especialistas.

**Exemplo — Sistema Especialista:**

```
SE febre > 38°C E tosse_seca = verdadeiro E perda_olfato = verdadeiro
ENTÃO suspeita ← "COVID-19 — encaminhar para teste"
```

**Vantagens:** interpretável, rastreável, auditável.
**Limitações:** frágil fora do domínio, escala mal, depende de codificação manual exaustiva.

Sistemas especialistas ainda são usados em nichos (diagnóstico industrial, configuradores de produto), mas foram largamente substituídos por abordagens baseadas em dados.

### 2.2 Aprendizado de Máquina (Machine Learning)

Em vez de programar regras explícitas, o sistema **aprende padrões a partir de dados**. Mitchell (1997) define formalmente:

> *"Um programa de computador aprende com a experiência E em relação a uma classe de tarefas T e medida de desempenho P, se seu desempenho em T, medido por P, melhora com a experiência E."*

**Tipos de aprendizado:**

| Tipo | Dados de treino | Objetivo | Exemplo |
|------|---------------|---------|---------|
| **Supervisionado** | Entrada + saída esperada (rótulos) | Prever rótulo para novas entradas | Classificar e-mails como spam/não-spam |
| **Não supervisionado** | Apenas entradas (sem rótulos) | Encontrar estrutura nos dados | Agrupar clientes por perfil de compra |
| **Por reforço** | Recompensas/punições por ações | Aprender política de ação ótima | IA de jogos (AlphaGo), robótica |

### O Ciclo de Machine Learning

```
┌──────────┐    ┌──────────────┐    ┌──────────────┐    ┌───────────┐
│  Dados   │ →  │ Pré-         │ →  │ Treinamento  │ →  │  Modelo   │
│  Brutos  │    │ processamento│    │ (algoritmo)  │    │ Treinado  │
└──────────┘    └──────────────┘    └──────────────┘    └─────┬─────┘
                                                              │
                ┌──────────────┐    ┌──────────────┐          │
                │  Decisão /   │ ←  │  Inferência  │ ←────────┘
                │  Ação        │    │ (predição)   │
                └──────────────┘    └──────────────┘
                                          ↑
                                    Novos dados
```

**Conceitos-chave:**

| Conceito | Significado |
|----------|-----------|
| **Feature (atributo)** | Variável de entrada que o modelo usa para aprender (ex: idade, renda, histórico) |
| **Label (rótulo)** | Saída esperada em aprendizado supervisionado (ex: aprovado/reprovado) |
| **Overfitting** | Modelo "decora" os dados de treino e falha com dados novos |
| **Underfitting** | Modelo simples demais, não captura os padrões |
| **Treino / Validação / Teste** | Divisão dos dados para treinar, ajustar e avaliar o modelo |

### 2.3 Aprendizado Profundo (Deep Learning)

Subconjunto de ML que utiliza **redes neurais artificiais com múltiplas camadas** (daí "deep"). Inspirado livremente na estrutura do cérebro, mas é fundamentalmente álgebra linear + cálculo + otimização.

**Arquiteturas principais:**

| Arquitetura | Uso principal | Referência |
|------------|--------------|-----------|
| **MLP** (Multilayer Perceptron) | Classificação e regressão tabular | Rosenblatt (1958), Rumelhart et al. (1986) |
| **CNN** (Convolutional Neural Network) | Visão computacional (imagens, vídeo) | LeCun et al. (1998) |
| **RNN / LSTM** | Sequências (texto, séries temporais) | Hochreiter & Schmidhuber (1997) |
| **Transformer** | NLP, visão, multimodal — domina tudo atualmente | Vaswani et al. (2017) |

### Como uma Rede Neural Aprende (Visão Simplificada)

1. **Forward pass:** dados entram, passam por camadas de neurônios com pesos, produzem uma saída.
2. **Cálculo do erro:** a saída é comparada com o resultado esperado (função de perda/loss).
3. **Backpropagation:** o erro é propagado de volta, camada por camada, calculando qual peso contribuiu mais para o erro.
4. **Atualização de pesos:** ajusta os pesos para reduzir o erro (gradient descent).
5. **Repetir** por milhares/milhões de iterações (epochs) até convergir.

```
Entrada → [Camada 1] → [Camada 2] → ... → [Camada N] → Saída
             ↕              ↕                  ↕
         pesos w1       pesos w2           pesos wN
              ←──── backpropagation ←──── erro
```

---

## 3. IA no Desenvolvimento de Software

| Aplicação | Como funciona | Ferramenta |
|-----------|--------------|-----------|
| **Code completion** | Prediz próximo trecho de código baseado em contexto | GitHub Copilot, Codeium, Tabnine |
| **Code review** | Analisa código em busca de bugs e vulnerabilidades | CodeQL, SonarQube com ML |
| **Testes automatizados** | Gera casos de teste a partir de especificação ou código | Diffblue Cover, Codium AI |
| **Documentação** | Gera docstrings e explicações de código | Copilot Chat, Mintlify |
| **DevOps/AIOps** | Detecção de anomalias em métricas de infraestrutura | Datadog AI, New Relic AIOps |
| **Chatbots/suporte** | Atendimento automatizado com compreensão de linguagem natural | Dialogflow, Amazon Lex, Azure Bot |
| **Detecção de fraude** | Classificação em tempo real de transações suspeitas | Modelos ML em produção |

---

## 4. Limitações Técnicas

IA não é magia e possui limitações fundamentais que todo profissional precisa conhecer:

| Limitação | Descrição | Implicação |
|-----------|----------|-----------|
| **Dependência de dados** | Modelo é tão bom quanto os dados de treino | Dados enviesados → resultados enviesados |
| **Falta de causalidade** | ML encontra correlações, não causas | "Vendas de sorvete correlacionam com afogamentos" ≠ causa |
| **Opacidade** | Redes neurais profundas são "caixas pretas" | Difícil explicar *por que* uma decisão foi tomada |
| **Fragilidade** | Pequenas perturbações na entrada podem mudar drasticamente a saída (adversarial examples) | Adesivo em placa de trânsito engana visão computacional (Goodfellow et al., 2014) |
| **Alucinação** | Modelos generativos inventam informações com aparência confiável | LLMs geram citações fictícias, fatos incorretos |
| **Custo computacional** | Treinar modelos grandes exige hardware caro e muita energia | GPT-4 custou estimados US$ 100 milhões para treinar |

---

## 5. Dimensões Éticas e Sociais

### 5.1 Viés Algorítmico

Modelos treinados com dados historicamente enviesados reproduzem e amplificam esses vieses (Buolamwini & Gebru, 2018):

- Sistemas de reconhecimento facial com taxas de erro até 34.7% maiores para mulheres de pele escura.
- Algoritmos de recrutamento que penalizavam currículos com termos associados ao gênero feminino (caso Amazon, 2018).

**Mitigação:** auditoria de dados, métricas de fairness, diversidade na equipe de desenvolvimento.

### 5.2 Responsabilidade e Accountability

Quando um modelo erra — e modelos erram — quem responde?

- O desenvolvedor que treinou o modelo?
- A empresa que o deployou?
- O provedor de dados?
- O regulador que aprovou?

A EU AI Act (2024) é a primeira legislação abrangente do mundo sobre IA, classificando sistemas por nível de risco e impondo requisitos proporcionais:

| Nível de risco | Exemplo | Requisitos |
|---------------|---------|-----------|
| Inaceitável | Scoring social pelo governo | Proibido |
| Alto | Diagnóstico médico, recrutamento | Transparência, auditoria, registro |
| Limitado | Chatbots | Informar que é IA |
| Mínimo | Filtros de spam | Sem requisitos especiais |

### 5.3 O Debate Sobre IA Geral (AGI)

**IA Estreita (ANI):** faz uma tarefa específica muito bem (tudo que existe hoje).
**IA Geral (AGI):** hipotética; faria qualquer tarefa intelectual humana.
**Superinteligência (ASI):** hipotética; superaria capacidade humana em todos os domínios.

Pesquisadores como Yann LeCun (Meta AI) argumentam que estamos longe de AGI e que LLMs não são o caminho. Outros, como Demis Hassabis (DeepMind), acreditam que estamos mais perto. O debate é legítimo e importante — mas no dia a dia de ADS, o que importa é dominar ANI e usá-la com responsabilidade.

---

## 6. Atividade Prática — Progressão em 3 Níveis

### Nível 1 — Classificação conceitual (10 min)

Classifique cada cenário como IA simbólica, ML supervisionado, ML não supervisionado ou ML por reforço:

| Cenário | Tipo |
|---------|------|
| Sistema que identifica spam pelo conteúdo do e-mail usando histórico rotulado | |
| Robô que aprende a andar por tentativa e erro | |
| Chatbot que segue árvore de decisão fixa | |
| Sistema que agrupa clientes por comportamento de compra | |
| Filtro de fotos que detecta rostos | |
| Sistema de regras IF-THEN para diagnóstico médico | |

### Nível 2 — Análise de caso real (20 min)

Escolha uma aplicação de IA em empresa brasileira (Nubank, iFood, Magazine Luiza, Globo ou outra) e descreva:

1. Qual problema a IA resolve.
2. Qual tipo provável de abordagem (simbólica, ML, DL).
3. Que dados provavelmente são utilizados.
4. Qual seria o impacto de viés nos dados de treinamento.
5. Como auditar se o sistema está funcionando corretamente.

### Nível 3 — Pensamento crítico (20 min)

1. Leia o artigo "On the Dangers of Stochastic Parrots" (Bender et al., 2021). Resuma em 15 linhas o argumento central.
2. Considere o cenário: uma empresa usa IA para triar currículos. O modelo rejeita sistematicamente candidatos de uma região específica. Descreva:
   - A causa técnica provável.
   - O impacto social.
   - 3 medidas para corrigir.
3. Defenda ou critique (com argumentos técnicos) a seguinte afirmação: "Modelos de IA generativa entendem o que estão dizendo."

---

## 7. Síntese

IA é uma das áreas mais impactantes e mais incompreendidas da computação. Para o profissional de ADS, o essencial é: entender o que IA pode e não pode fazer, saber onde ela se encaixa no ciclo de desenvolvimento de software, e desenvolver senso crítico para avaliar resultados e implicações. A hype vai passar; a necessidade de profissionais que entendam os fundamentos, não.

---

## Referências

- BENDER, Emily M. et al. On the dangers of stochastic parrots: can language models be too big? *Proceedings of FAccT*, 2021. Disponível em: <https://doi.org/10.1145/3442188.3445922>
- BUOLAMWINI, Joy; GEBRU, Timnit. Gender shades: intersectional accuracy disparities in commercial gender classification. *Proceedings of FAT*, 2018. Disponível em: <https://proceedings.mlr.press/v81/buolamwini18a.html>
- EUROPEAN UNION. *Artificial Intelligence Act*. 2024. Disponível em: <https://artificialintelligenceact.eu/>
- GOODFELLOW, Ian; BENGIO, Yoshua; COURVILLE, Aaron. *Deep Learning*. MIT Press, 2016. Disponível em: <https://www.deeplearningbook.org/>
- GOODFELLOW, Ian; SHLENS, Jonathon; SZEGEDY, Christian. Explaining and harnessing adversarial examples. *ICLR*, 2015. Disponível em: <https://arxiv.org/abs/1412.6572>
- HOCHREITER, Sepp; SCHMIDHUBER, Jürgen. Long short-term memory. *Neural Computation*, v. 9, n. 8, p. 1735-1780, 1997.
- LECUN, Yann et al. Gradient-based learning applied to document recognition. *Proceedings of the IEEE*, v. 86, n. 11, p. 2278-2324, 1998.
- MITCHELL, Tom. *Machine Learning*. McGraw-Hill, 1997.
- RUMELHART, David E.; HINTON, Geoffrey E.; WILLIAMS, Ronald J. Learning representations by back-propagating errors. *Nature*, v. 323, p. 533-536, 1986. Disponível em: <https://doi.org/10.1038/323533a0>
- RUSSELL, Stuart; NORVIG, Peter. *Artificial Intelligence: A Modern Approach*. 4. ed. Pearson, 2021.
- TURING, Alan M. Computing machinery and intelligence. *Mind*, v. 59, n. 236, p. 433-460, 1950. Disponível em: <https://doi.org/10.1093/mind/LIX.236.433>
- VASWANI, Ashish et al. Attention is all you need. *NeurIPS*, 2017. Disponível em: <https://arxiv.org/abs/1706.03762>
- FACELI, Katti et al. *Inteligência Artificial: Uma Abordagem de Aprendizado de Máquina*. 2. ed. LTC, 2021.
