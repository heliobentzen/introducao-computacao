---
marp: true
theme: default
paginate: true
backgroundColor: #1a1a2e
color: #eaeaea
style: |
  section { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
  h1 { color: #e94560; }
  h2 { color: #fff; background: #e94560; padding: 4px 16px; border-radius: 4px; }
  table { font-size: 0.78em; }
  code { background: #16213e; color: #e94560; }
  a { color: #00d2ff; }
  blockquote { border-left: 4px solid #e94560; color: #ccc; }
---

# 06 — Cloud Computing

**Introdução à Computação — ADS**
Computação sob demanda: da sala do servidor ao mundo.

---

## Definição NIST

> Modelo que permite acesso sob demanda a um pool compartilhado de recursos computacionais configuráveis, provisionados e liberados com mínimo esforço de gerenciamento. — Mell & Grance (2011)

**5 características essenciais:**

1. Self-service sob demanda
2. Acesso amplo pela rede
3. Pool de recursos compartilhado
4. Elasticidade rápida
5. Serviço medido (pay-as-you-go)

---

## Modelos de Serviço

| Modelo | Você gerencia | Provedor gerencia | Exemplo |
|--------|-------------|-------------------|---------|
| **IaaS** | App, dados, runtime, SO | Hardware, rede, virtualização | AWS EC2, Azure VM |
| **PaaS** | App e dados | Todo o resto | Heroku, Azure App Service |
| **SaaS** | Apenas usa | Tudo | Gmail, Office 365, Salesforce |
| **FaaS** | Função (código) | Todo o resto | AWS Lambda, Azure Functions |

**Regra:** quanto mais "as a Service", menos você gerencia (e menos controle tem).

---

## Modelos de Implantação

| Modelo | Quem usa | Exemplo |
|--------|---------|---------|
| **Pública** | Qualquer organização | AWS, Azure, GCP |
| **Privada** | Uma organização (próprio datacenter ou dedicado) | OpenStack, VMware |
| **Híbrida** | Combina pública + privada | Maioria das grandes empresas |
| **Multi-cloud** | Vários provedores públicos | Netflix (AWS + GCP) |

---

## Responsabilidade Compartilhada

| Camada | IaaS | PaaS | SaaS |
|--------|------|------|------|
| Hardware / Rede | Provedor | Provedor | Provedor |
| SO | **Cliente** | Provedor | Provedor |
| Runtime | **Cliente** | Provedor | Provedor |
| Aplicação | **Cliente** | **Cliente** | Provedor |
| Dados | **Cliente** | **Cliente** | **Cliente** |
| Acesso / Identidade | **Cliente** | **Cliente** | **Cliente** |

**Regra de ouro:** seus dados e identidades são SEMPRE sua responsabilidade.

---

## SLA — Disponibilidade

| SLA | Downtime/ano | Downtime/mês |
|-----|-------------|-------------|
| 99% | 3.65 dias | 7.3 horas |
| 99.9% | 8.76 horas | 43.8 min |
| 99.95% | 4.38 horas | 21.9 min |
| 99.99% | 52.6 min | 4.4 min |
| 99.999% | 5.26 min | 26.3 seg |

**Combinando 2 zonas (99.95% cada):**
$$A_{total} = 1 - (1 - 0.9995)^2 = 99.9999\%$$

---

## CAP Theorem

> Em sistema distribuído, é impossível garantir simultaneamente (Brewer, 2000):

| Propriedade | Significado |
|------------|-----------|
| **C**onsistência | Toda leitura retorna o dado mais recente |
| **A**vailability | Toda requisição recebe resposta |
| **P**artition tolerance | Sistema funciona mesmo com falha de rede |

**Na prática:** sistemas escolhem 2 de 3. Bancos de dados NoSQL tipicamente sacrificam C para ganhar A+P.

---

## FinOps — Custo na Nuvem

| Modelo de preço | Economia | Compromisso |
|----------------|----------|------------|
| On-demand | 0% (baseline) | Nenhum |
| Reserved (1 ano) | ~30-40% | Pagar adiantado |
| Reserved (3 anos) | ~50-60% | Longo prazo |
| Spot/Preemptive | ~70-90% | Pode ser interrompido |

**Armadilha:** cloud parece barata, mas sem controle os custos explodem.
→ FinOps = disciplina de gestão financeira de cloud.

---

## Provedores — Big Three

| Aspecto | AWS | Azure | GCP |
|---------|-----|-------|-----|
| Market share | ~31% | ~25% | ~11% |
| Forte em | Amplitude de serviços | Enterprise / Microsoft stack | Data analytics, ML |
| Free tier | 12 meses | US$ 200 crédito (estudante) | US$ 300 crédito |

---

## Referências-chave

- Mell & Grance (2011). The NIST Definition of Cloud Computing
- Brewer (2000). Towards Robust Distributed Systems (CAP)
- Marinescu (2022). *Cloud Computing: Theory and Practice* (4ª ed.)
- FinOps Foundation. [finops.org](https://finops.org)

---

## Checkpoint

**→ Checkpoint 03** (com módulo 05)
Modelos de serviço, SLA, responsabilidade compartilhada, cálculo de custo.
