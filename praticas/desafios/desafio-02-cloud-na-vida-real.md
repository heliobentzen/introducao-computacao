# Desafio 02 — Arquitetura Cloud para Negócio Real

> **Módulos cobertos:** 04 (Dados e Numeração), 05 (Sistemas Operacionais), 06 (Cloud Computing)  
> **Tipo:** Equipe de 3–4 pessoas  
> **Duração estimada:** 3–4 horas (fora de sala)  
> **Peso na avaliação:** desafio substitui nota de atividade regular

---

## Cenário

A **BoaEntrega**, uma cooperativa de entregadores de bicicleta, opera em 3 cidades brasileiras. Atualmente:

- O sistema roda num servidor físico no escritório (Windows Server, 16 GB RAM, HDD 1 TB).
- O banco de dados é MySQL local com 200 mil pedidos acumulados.
- O app dos entregadores é um site responsivo hospedado no mesmo servidor.
- Nos horários de pico (11h–14h e 18h–21h), o sistema trava e pedidos se perdem.
- Não há backup automático; o último backup manual foi há 45 dias.
- O "TI" é um dos sócios que "sabe mexer em computador".

A cooperativa recebeu um investimento de R$ 50 mil para modernização tecnológica e quer migrar para a nuvem.

---

## Entregas

### E1. Diagnóstico técnico (Módulo 05)

Analise o cenário atual identificando:

1. **5 problemas técnicos** com classificação de severidade (crítica/alta/média/baixa).
2. Para cada problema, cite o conceito de SO relevante (ex: "gargalo de I/O → HDD como bottleneck na hierarquia de memória").
3. **Análise de risco:** o que acontece se o servidor físico falhar hoje? Liste 3 consequências.

### E2. Representação de dados (Módulo 04)

1. Estime o **tamanho médio de um registro de pedido** em bytes (considere: ID, timestamp, endereço origem/destino como strings UTF-8, valor em ponto flutuante, status como enum de 1 byte).
2. Calcule o **armazenamento necessário** para 200 mil registros existentes + projeção de 500 mil novos pedidos/ano.
3. Represente o campo "valor do pedido" (R$ 27,50) em **IEEE 754 precisão simples**. Mostre os passos.
4. Explique em 5 linhas por que usar ponto flutuante para valores monetários pode causar problemas e qual a alternativa (inteiros em centavos).

### E3. Proposta de arquitetura cloud (Módulo 06)

Projete a arquitetura cloud contendo:

**Diagrama** (draw.io, Mermaid ou à mão):

- Frontend (app dos entregadores).
- Backend (API).
- Banco de dados.
- Armazenamento de arquivos (comprovantes, fotos).
- Serviço de filas (para picos).

**Especificação técnica:**

| Componente | Serviço cloud escolhido | Modelo (IaaS/PaaS/SaaS/FaaS) | Justificativa |
|-----------|------------------------|------------------------------|-------------|
| Servidor web/API | | | |
| Banco de dados | | | |
| Armazenamento de objetos | | | |
| Fila de mensagens | | | |
| CDN (conteúdo estático) | | | |
| Monitoramento | | | |

**Provedor:** escolha **um** (AWS, Azure ou GCP) e use serviços reais com nomes corretos.

### E4. Segurança e acesso

1. Preencha a **matriz de responsabilidade compartilhada** para cada componente escolhido.
2. Defina **3 papéis de acesso** (admin, desenvolvedor, entregador) e suas permissões.
3. Proponha estratégia de **backup automatizado**: frequência, retenção, teste de restore.
4. Calcule a disponibilidade combinada se usar **2 zonas** com SLA individual de 99.95%.

### E5. Estimativa de custo (FinOps)

Monte uma planilha de custo mensal estimado:

| Serviço | Configuração | Custo unitário | Horas/mês | Custo mensal |
|---------|-------------|---------------|-----------|-------------|
| | | | | |

- Custo total mensal estimado.
- Custo anual estimado.
- Compare com o custo atual (servidor físico + energia + "TI" do sócio + risco de perda de dados).
- Proponha **2 otimizações** (instâncias reservadas, autoscaling, spot instances, etc.).

### E6. Plano de migração

Proponha um plano em **3 fases** (máximo 1 parágrafo por fase):

1. **Fase 1 — Backup e emergência** (semana 1).
2. **Fase 2 — Migração do banco e API** (semanas 2–4).
3. **Fase 3 — Cutover e monitoramento** (semana 5).

Para cada fase: o que fazer, o que pode dar errado, plano de rollback.

---

## Critérios de Excelência

| Critério | Peso |
|----------|------|
| Diagnóstico técnico com conceitos de SO | 15% |
| Cálculos de dados e IEEE 754 | 15% |
| Qualidade da arquitetura cloud | 25% |
| Segurança e responsabilidade compartilhada | 15% |
| Estimativa de custo realista | 15% |
| Plano de migração e comunicação técnica | 15% |

---

## Formato de entrega

- Repositório Git com README.
- Documento principal em markdown com todos os itens.
- Diagrama de arquitetura como imagem ou Mermaid.
- Planilha de custo (markdown table ou CSV).
- Seção final: **"O que pode dar ruim"** — liste 3 riscos do projeto e planos de contingência.

> Engenharia boa nasce de otimismo com paranoia saudável.
