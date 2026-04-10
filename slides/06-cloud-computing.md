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

## Módulo 06 · Cloud Computing

**Prof. Hélio Bentzen**
IFPE · Análise e Desenvolvimento de Sistemas

---

# ☁️ Cloud Computing

---

## Definição NIST

> Acesso **sob demanda** a um pool compartilhado de recursos computacionais. — Mell & Grance, 2011

| # | Característica |
|:-:|---------------|
| 1 | Self-service sob demanda |
| 2 | Acesso amplo pela rede |
| 3 | Pool de recursos compartilhado |
| 4 | Elasticidade rápida |
| 5 | Pay-as-you-go |

---

## Modelos de Serviço

| Modelo | Você gerencia | Exemplo |
|--------|:------------:|---------|
| **IaaS** | App + SO + runtime | EC2, Azure VM |
| **PaaS** | App + dados | Heroku, App Service |
| **SaaS** | Apenas usa | Gmail, Office 365 |
| **FaaS** | Só a função | Lambda, Functions |

> Quanto mais *"aaS"*, menos controle — e menos responsabilidade infra.

---

## Modelos de Implantação

| Modelo | Quem usa | Exemplo |
|--------|---------|---------|
| ☁️ **Pública** | Qualquer org. | AWS, Azure, GCP |
| 🏢 **Privada** | Apenas uma org. | OpenStack |
| 🔀 **Híbrida** | Pública + Privada | Maioria enterprise |
| 🌐 **Multi-cloud** | Vários provedores | Netflix |

---

## Responsabilidade Compartilhada

| Camada | IaaS | PaaS | SaaS |
|--------|:----:|:----:|:----:|
| Hardware / Rede | ☁️ | ☁️ | ☁️ |
| SO / Runtime | **Você** | ☁️ | ☁️ |
| Aplicação | **Você** | **Você** | ☁️ |
| Dados + Identidade | **Você** | **Você** | **Você** |

> Seus dados e identidades são **sempre** sua responsabilidade.

---

## SLA — Disponibilidade

| SLA | Downtime / ano | Downtime / mês |
|:---:|:--------------:|:--------------:|
| 99% | 3.65 dias | 7.3 h |
| 99.9% | 8.76 h | 43.8 min |
| 99.99% | 52.6 min | 4.4 min |
| 99.999% | 5.26 min | 26.3 s |

2 zonas 99.95% cada:
$$A = 1 - (1 - 0{,}9995)^2 = 99{,}9999\%$$

---

## Teorema CAP

> Em sistema distribuído, escolha **2 de 3** — Brewer, 2000

| Letra | Propriedade |
|:-----:|------------|
| **C** | Consistência — leitura mais recente |
| **A** | Disponibilidade — sempre responde |
| **P** | Tolerância a partição — funciona com falha de rede |

Bancos NoSQL: geralmente sacrificam **C** para ganhar A + P.

---

## FinOps — Custo na Nuvem

| Modelo de preço | Economia | Risco |
|----------------|:--------:|-------|
| On-demand | 0% | Nenhum |
| Reserved 1 ano | ~35% | Compromisso |
| Reserved 3 anos | ~55% | Longo prazo |
| Spot | ~70-90% | Interrupção |

> Cloud *parece* barata, mas sem controle os custos **explodem**.

---

## Big Three

| | AWS | Azure | GCP |
|:-:|:---:|:-----:|:---:|
| Share | ~31% | ~25% | ~11% |
| Forte | Amplitude | Enterprise | Data / ML |
| Free | 12 meses | US$ 200 (estudante) | US$ 300 |

---

## Referências

- Mell & Grance (2011). *NIST Definition of Cloud Computing*
- Brewer (2000). *Towards Robust Distributed Systems*
- Marinescu (2022). *Cloud Computing*, 4ª ed.

**→ Checkpoint 03** · com módulo 05
