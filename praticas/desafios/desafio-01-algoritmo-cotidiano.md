# Desafio 01 — Modelagem Computacional de Processo Real

> **Módulos cobertos:** 01 (Pensamento Computacional), 02 (Lógica e Algoritmos), 03 (Hardware)  
> **Tipo:** Individual ou dupla  
> **Duração estimada:** 2–3 horas (fora de sala)  
> **Peso na avaliação:** desafio substitui nota de atividade regular

---

## Cenário

O **SAMU 192** de uma cidade com 500 mil habitantes precisa otimizar o atendimento de chamadas de emergência. O processo envolve:

1. Recepção da ligação (telefonista).
2. Triagem de gravidade (protocolos Manchester: vermelho, laranja, amarelo, verde, azul).
3. Despacho de ambulância com base na gravidade e localização.
4. Atendimento pré-hospitalar.
5. Transporte e encaminhamento (UPA, hospital, alta no local).
6. Registro e encerramento do chamado.

**Dados do cenário:**

- 3 ambulâncias de suporte básico, 1 de suporte avançado.
- Tempo médio de deslocamento: 12 min (básica), 18 min (avançada).
- Pico de chamadas: 17h–22h (média de 15 chamados/hora).
- A ambulância avançada deve ser reservada para vermelho/laranja.

---

## Entregas

### E1. Decomposição e abstração (Módulo 01)

- Decomponha o sistema em **pelo menos 8 subproblemas**.
- Para cada subproblema, identifique: entrada, processamento e saída.
- Proponha **3 abstrações** que simplifiquem a modelagem (ex: ignorar condições de trânsito variáveis).
- Identifique **5 padrões** que se repetem entre atendimentos de gravidades diferentes.

### E2. Algoritmo completo (Módulo 02)

Escreva em pseudocódigo estruturado o algoritmo de **despacho de ambulância** contendo:

- Estrutura de **fila por prioridade** (vermelho > laranja > amarelo > verde > azul).
- **Laço principal** que processa chamados enquanto houver chamadas na fila.
- **Condicionais** para: ambulância disponível vs. todas ocupadas; tipo de ambulância compatível com gravidade.
- **Tratamento de exceções**: todas as ambulâncias ocupadas, chamado trote, endereço inválido.
- Mínimo de **25 linhas** de pseudocódigo com comentários.

### E3. Fluxograma completo (Módulo 02)

- Converta o algoritmo em fluxograma com **pelo menos 15 blocos**.
- Use padrão ISO 5807 (retângulo, losango, paralelogramo, terminadores).
- Inclua **pelo menos 4 pontos de decisão**.
- Ferramenta: draw.io, Mermaid ou Excalidraw.

### E4. Análise de hardware (Módulo 03)

Especifique o **hardware mínimo** para o servidor central do SAMU:

- Processador: justifique a escolha (CISC ou RISC? quantos núcleos?).
- Memória RAM: quanto? por quê?
- Armazenamento: HDD ou SSD? capacidade estimada para 1 ano de registros.
- Redundância: o que acontece se o servidor falhar? Proposta de contingência.

### E5. Trace table e teste

Simule a execução do seu algoritmo para **3 cenários distintos**:

| Cenário | Gravidade | Ambulâncias disponíveis | Resultado esperado |
|---------|----------|------------------------|-------------------|
| Emergência cardíaca | Vermelho | Avançada livre | Despacho imediato da avançada |
| Queda sem fratura | Verde | 2 básicas livres | Despacho de básica |
| AVC em idoso | Laranja | Nenhuma disponível | Fila de espera + remanejamento |

Para cada cenário, preencha trace table passo a passo.

### E6. Análise de falhas

Identifique **5 possíveis falhas** no sistema e para cada uma proponha:

- Causa provável.
- Impacto (baixo/médio/alto/crítico).
- Mitigação.

---

## Critérios de Excelência

| Critério | Peso |
|----------|------|
| Profundidade da decomposição e abstrações | 20% |
| Robustez e completude do algoritmo | 25% |
| Qualidade do fluxograma | 15% |
| Coerência da especificação de hardware | 15% |
| Trace tables e análise de falhas | 15% |
| Comunicação técnica e organização do documento | 10% |

---

## Formato de entrega

- Repositório Git com README explicativo.
- Documento principal em markdown.
- Fluxograma como imagem ou código Mermaid embutido.
- Seção final: **"Lições aprendidas"** — o que quebrou, como resolveu e o que faria diferente.
