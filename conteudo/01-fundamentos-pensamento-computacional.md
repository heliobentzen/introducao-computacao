# 01 — Fundamentos e Pensamento Computacional

## Objetivos de aprendizagem

Ao final deste módulo o estudante será capaz de:

- Definir computação como ciência e distingui-la de programação.
- Aplicar os quatro pilares do pensamento computacional a problemas reais.
- Construir algoritmos informais com rastreabilidade de passos.
- Avaliar a qualidade de uma solução algorítmica por critérios de correção, eficiência e clareza.

---

## 1. O que é Computação?

Computação não se resume a escrever código. A definição clássica de Aho e Ullman (1992) descreve a Ciência da Computação como o estudo de **processos mecânicos de manipulação de informação** — o que inclui algoritmos, estruturas de dados, linguagens formais e a própria teoria da complexidade.

Em termos práticos, computação é a disciplina que investiga **o que pode ser calculado**, **como calcular de forma eficiente** e **quais são os limites do cálculo**. Esse tripé conceitual guia toda a formação em Análise e Desenvolvimento de Sistemas.

### 1.1 Computação vs. Programação

| Aspecto | Computação | Programação |
|---------|-----------|-------------|
| Escopo | Ciência: teoria, modelos, limites | Prática: implementação em linguagem |
| Pergunta central | "Esse problema tem solução?" | "Como codifico esta solução?" |
| Produto | Algoritmo, modelo, prova | Código, sistema, aplicação |

Programar é uma **ferramenta** da computação, não seu sinônimo. Quem confunde as duas coisas tende a pular para o código antes de entender o problema — o erro mais caro que existe em engenharia de software (Boehm & Turner, 2004).

### 1.2 Áreas da Computação — Visão Panorâmica

A ACM e a IEEE-CS definem cinco grandes áreas de formação em computação (ACM/IEEE-CS, 2020):

| Área | Foco principal |
|------|---------------|
| Ciência da Computação | Teoria, algoritmos, inteligência artificial |
| Engenharia de Software | Processo, qualidade, ciclo de vida de sistemas |
| Sistemas de Informação | Tecnologia aplicada a organizações |
| Engenharia de Computação | Hardware, sistemas embarcados, arquitetura |
| Tecnologia da Informação | Infraestrutura, redes, segurança |

ADS (Análise e Desenvolvimento de Sistemas) navega principalmente entre Engenharia de Software e Sistemas de Informação, mas bebe de todas as fontes acima.

---

## 2. Pensamento Computacional — Definição Formal

O termo foi popularizado por Jeannette Wing (2006) em artigo seminal na *Communications of the ACM*. Wing argumenta que o pensamento computacional é uma habilidade fundamental para todos, não apenas para cientistas da computação, pois envolve **resolver problemas, projetar sistemas e compreender comportamento humano usando conceitos da ciência da computação**.

Barr e Stephenson (2011) expandem a definição para o contexto educacional: pensamento computacional é um processo de solução de problemas que inclui formular problemas de forma que computadores possam ajudar a resolvê-los, organizar dados logicamente, representar dados por abstrações, automatizar soluções via pensamento algorítmico e generalizar soluções para classes de problemas.

O framework mais adotado no ensino divide o pensamento computacional em quatro pilares:

### 2.1 Decomposição

Dividir um problema complexo em subproblemas menores e gerenciáveis.

**Por que funciona:** a capacidade de memória de trabalho humana é limitada a aproximadamente 7 ± 2 itens simultâneos (Miller, 1956). Decompor reduz a carga cognitiva em cada etapa.

**Exemplo nível 1 — Cotidiano:**
Organizar uma mudança de apartamento.

- Subproblema 1: inventariar pertences por cômodo.
- Subproblema 2: embalar por categoria (frágil, pesado, roupas).
- Subproblema 3: contratar transporte adequado ao volume.
- Subproblema 4: definir ordem de desembalagem no destino.

**Exemplo nível 2 — Técnico:**
Construir um sistema de cadastro de alunos.

- Subproblema 1: capturar dados de entrada (nome, matrícula, curso).
- Subproblema 2: validar formato (e-mail válido, matrícula numérica).
- Subproblema 3: persistir em banco de dados com integridade referencial.
- Subproblema 4: exibir confirmação com resumo ao usuário.
- Subproblema 5: tratar erros (duplicidade, falha de conexão).

A decomposição é análoga ao princípio **Divide et Impera** (Dividir para Conquistar) presente em algoritmos clássicos como Merge Sort e Quick Sort (Cormen et al., 2022). Na engenharia de software, manifesta-se como modularização e separação de responsabilidades.

### 2.2 Reconhecimento de Padrões

Identificar regularidades, repetições e semelhanças entre subproblemas ou conjuntos de dados.

**Exemplo nível 1:**
Em uma planilha de vendas, perceber que todo mês de dezembro tem pico de faturamento é reconhecer um padrão sazonal. Isso permite prever demanda e ajustar estoque antecipadamente.

**Exemplo nível 2:**
Ao modelar diferentes formulários em um sistema (cadastro de cliente, cadastro de fornecedor, cadastro de produto), perceber que todos compartilham a estrutura: campo de entrada → validação → persistência → resposta de sucesso ou erro. Esse padrão recorrente pode ser abstraído em um componente genérico reutilizável.

**Exemplo nível 3 — Formal:**
Na teoria de linguagens formais, reconhecimento de padrões em cadeias de caracteres é formalizado por **autômatos finitos** e **expressões regulares** (Hopcroft, Motwani & Ullman, 2006). Na inteligência artificial, redes neurais convolucionais detectam padrões visuais em imagens (LeCun et al., 1998).

### 2.3 Abstração

Filtrar a informação irrelevante e manter apenas o que é essencial para a solução. É o processo de criar **modelos simplificados** da realidade.

**Exemplo nível 1:**
Para calcular o tempo de viagem entre duas cidades, você precisa de distância e velocidade média. Cor do carro, nome do motorista e marca do pneu são irrelevantes — são ruído.

**Exemplo nível 2:**
Um mapa do metrô é uma abstração topológica: não mostra escala real, topografia nem curvatura dos trilhos. Mostra apenas estações e conexões — exatamente o que o passageiro precisa para decidir o caminho. Harry Beck criou o icônico mapa do metrô de Londres em 1931 usando esse princípio.

**Exemplo nível 3 — Formal:**
Em computação, abstração é formalizada no conceito de **Tipos Abstratos de Dados (TAD)**, proposto por Liskov e Zilles (1974). Um TAD define *o que* as operações fazem (interface) sem especificar *como* fazem (implementação). Esse princípio é a base do encapsulamento na programação orientada a objetos e do design por contrato (Meyer, 1997).

### 2.4 Algoritmos

Sequência finita, ordenada e não ambígua de instruções que resolve um problema.

**Propriedades formais de um algoritmo (Knuth, 1997):**

1. **Finitude:** termina após um número finito de passos.
2. **Definição:** cada passo é preciso e sem ambiguidade.
3. **Entrada:** recebe zero ou mais valores de um conjunto bem definido.
4. **Saída:** produz um ou mais resultados relacionados às entradas.
5. **Efetividade:** cada passo é suficientemente básico para ser executado em tempo finito com recursos finitos.

**Exemplo nível 1 — Receita algorítmica:**

```
Algoritmo: Calcular média de 3 notas
Entrada: nota1, nota2, nota3
1. soma ← nota1 + nota2 + nota3
2. media ← soma / 3
3. Se media >= 7.0 então
     resultado ← "Aprovado"
   Senão
     resultado ← "Em recuperação"
4. Retornar resultado
```

**Exemplo nível 2 — Busca sequencial:**

```
Algoritmo: Buscar nome em lista
Entrada: lista[1..n] de nomes, nome_alvo
1. Para i de 1 até n faça
   1.1 Se lista[i] = nome_alvo então
         Retornar i  // posição encontrada
2. Retornar -1  // não encontrado
```

Este é o algoritmo de **busca linear**, com complexidade O(n) no pior caso — percorre todos os n elementos (Cormen et al., 2022).

**Exemplo nível 3 — Busca binária (comparação):**

```
Algoritmo: Buscar em lista ordenada
Entrada: lista[1..n] ordenada, valor_alvo
1. inicio ← 1
2. fim ← n
3. Enquanto inicio <= fim faça
   3.1 meio ← (inicio + fim) / 2  // divisão inteira
   3.2 Se lista[meio] = valor_alvo então
         Retornar meio
   3.3 Senão Se lista[meio] < valor_alvo então
         inicio ← meio + 1
   3.4 Senão
         fim ← meio - 1
4. Retornar -1
```

Complexidade O(log n) — para 1 milhão de elementos, a busca binária precisa de no máximo ~20 comparações, enquanto a busca linear pode precisar de 1 milhão. Essa diferença ilustra por que **análise de algoritmos** é uma das disciplinas mais importantes da computação.

---

## 3. Qualidade de Soluções Algorítmicas

Não basta resolver; é preciso resolver **bem**. Três critérios fundamentais avaliam a qualidade:

| Critério | Pergunta-chave | Exemplo de falha |
|----------|---------------|------------------|
| **Correção** | Produz o resultado certo para todas as entradas válidas? | Algoritmo que aprova aluno com nota 6.99 por erro de comparação (>= vs >) |
| **Eficiência** | Usa recursos (tempo, memória) de forma razoável? | Buscar sequencialmente em 1 milhão de registros ordenados quando busca binária resolve em 20 passos |
| **Clareza** | Outro ser humano consegue ler, entender e manter? | Variáveis chamadas `a`, `b`, `c` sem qualquer contexto semântico |

A área de **Análise de Algoritmos**, formalizada por Knuth e posteriormente sistematizada por Cormen et al. (2022), estuda esses aspectos com rigor matemático. Neste estágio, o importante é internalizar que a solução precisa ser **correta primeiro, eficiente depois e legível sempre**.

---

## 4. Computabilidade — O Que Não Pode Ser Computado

Alan Turing (1936) provou que existem problemas que **nenhum algoritmo pode resolver**. O exemplo clássico é o **Problema da Parada (Halting Problem):** não existe um programa genérico capaz de determinar, para qualquer programa P e entrada I, se P irá parar ou executar infinitamente com a entrada I.

Isso não é limitação tecnológica — é limitação **matemática fundamental**. Saber que existem limites para a computação é tão importante quanto saber usá-la.

Na prática profissional, isso se manifesta em problemas NP-difíceis (como otimização de rotas e escalonamento complexo), onde buscamos soluções **aproximadas boas o suficiente** em vez de soluções perfeitas inviáveis.

---

## 5. Pensamento Computacional na Prática Profissional

O pensamento computacional transcende a programação. O World Economic Forum (2023) classifica pensamento analítico e pensamento criativo — ambos derivados do pensamento computacional — entre as 5 habilidades mais demandadas globalmente.

Aplicações por setor:

| Setor | Aplicação | Pilar dominante |
|-------|-----------|----------------|
| Saúde | Protocolos de triagem e diagnóstico | Decomposição + Algoritmo |
| Logística | Otimização de rotas de entrega | Padrões + Abstração |
| Finanças | Detecção de fraude em transações | Reconhecimento de Padrões |
| Educação | Sistemas adaptativos de aprendizagem | Abstração + Algoritmo |
| DevOps | Pipelines de deploy automatizado | Decomposição + Algoritmo |

---

## 6. Erros Clássicos de Iniciantes

| Erro | Por que acontece | Como evitar |
|------|-----------------|-------------|
| Codar antes de entender o problema | Ansiedade por resultado imediato | Escreva o algoritmo no papel primeiro — sempre |
| Passos ambíguos ("resolver isso") | Falta de precisão no pensamento | Cada passo deve ser verificável por outra pessoa |
| Ignorar casos extremos | Foco apenas no "caminho feliz" | Liste pelo menos 3 cenários: normal, limite e inválido |
| Não testar com dados reais | Excesso de confiança na lógica | Execute manualmente com valores concretos (teste de mesa) |
| Confundir complexidade com qualidade | Impressionar ao invés de resolver | Solução boa é a mais simples que resolve o problema |

---

## 7. Atividade Prática — Progressão em 3 Níveis

### Nível 1 — Aquecimento (10 min)

Escreva um algoritmo em até 8 passos para fazer café para 20 pessoas no laboratório. Deve prever: falta de água, falta de pó  e número insuficiente de xícaras.

### Nível 2 — Intermediário (15 min)

Modele o processo de triagem de atendimento em uma clínica:

- Paciente chega e informa sintomas.
- Sistema classifica urgência (verde, amarelo, vermelho) usando o Protocolo de Manchester.
- Fila respeita prioridade por cor e, dentro da mesma cor, ordem de chegada.
- Descreva o algoritmo completo com decisões e repetições.
- Identifique 3 casos extremos.

### Nível 3 — Desafio (20 min)

Proponha um algoritmo para distribuir 30 alunos em 5 grupos de trabalho, garantindo que:

- Nenhum grupo tenha todos os membros com a mesma faixa de nota (heterogeneidade).
- A diferença de média entre grupos não ultrapasse 1.0 ponto.
- Descreva como verificar (testar) se a distribuição atende aos critérios.
- Analise: seu algoritmo sempre termina? (Argumento de finitude)

---

## 8. Reflexão Final

Pensamento computacional não é talento místico. É processo treinável. Wing (2006) insiste que **pensar como um cientista da computação** significa ser capaz de reformular problemas difíceis em versões que sabemos resolver — e isso serve para qualquer área, qualquer carreira.

Apanhar do problema faz parte do método. Documentar *por que* apanhou é o que separa aprendizado de sofrimento aleatório.

---

## Referências

- ACM/IEEE-CS. *Computing Curricula 2020: Paradigms for Global Computing Education*. ACM/IEEE, 2020. Disponível em: <https://doi.org/10.1145/3467967>
- AHO, Alfred V.; ULLMAN, Jeffrey D. *Foundations of Computer Science*. W. H. Freeman, 1992. Disponível em: <http://infolab.stanford.edu/~ullman/focs.html>
- BARR, Valerie; STEPHENSON, Chris. Bringing computational thinking to K-12. *ACM Inroads*, v. 2, n. 1, p. 48-54, 2011. Disponível em: <https://doi.org/10.1145/1929887.1929905>
- BOEHM, Barry; TURNER, Richard. *Balancing Agility and Discipline*. Addison-Wesley, 2004.
- CORMEN, Thomas H. et al. *Introduction to Algorithms*. 4. ed. MIT Press, 2022.
- HOPCROFT, John E.; MOTWANI, Rajeev; ULLMAN, Jeffrey D. *Introduction to Automata Theory, Languages, and Computation*. 3. ed. Pearson, 2006.
- KNUTH, Donald E. *The Art of Computer Programming, Volume 1: Fundamental Algorithms*. 3. ed. Addison-Wesley, 1997.
- LECUN, Yann et al. Gradient-based learning applied to document recognition. *Proceedings of the IEEE*, v. 86, n. 11, p. 2278-2324, 1998.
- LISKOV, Barbara; ZILLES, Stephen. Programming with abstract data types. *ACM SIGPLAN Notices*, v. 9, n. 4, p. 50-59, 1974. Disponível em: <https://doi.org/10.1145/942572.807045>
- MEYER, Bertrand. *Object-Oriented Software Construction*. 2. ed. Prentice Hall, 1997.
- MILLER, George A. The magical number seven, plus or minus two. *Psychological Review*, v. 63, n. 2, p. 81-97, 1956. Disponível em: <https://doi.org/10.1037/h0043158>
- TURING, Alan M. On computable numbers, with an application to the Entscheidungsproblem. *Proceedings of the London Mathematical Society*, s2-42, p. 230-265, 1936. Disponível em: <https://doi.org/10.1112/plms/s2-42.1.230>
- WING, Jeannette M. Computational thinking. *Communications of the ACM*, v. 49, n. 3, p. 33-35, 2006. Disponível em: <https://doi.org/10.1145/1118178.1118215>
- WORLD ECONOMIC FORUM. *Future of Jobs Report 2023*. Disponível em: <https://www.weforum.org/reports/the-future-of-jobs-report-2023>
