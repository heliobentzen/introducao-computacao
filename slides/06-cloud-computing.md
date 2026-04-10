---
marp: true
theme: default
paginate: true
style: |
  section { font-family: 'Segoe UI', system-ui, sans-serif; background: linear-gradient(135deg,#0c0c1d,#1a1a3e); color: #e8e8f0; }
  h1 { color: #ff6b6b; font-size: 2.2em; }
  h2 { background: linear-gradient(90deg,#e94560,#c23152); color: #fff; padding: 6px 20px; border-radius: 8px; display: inline-block; }
  strong { color: #00d4ff; } em { color: #ffd166; font-style: normal; }
  table { font-size: 0.72em; } th { background: rgba(233,69,96,0.85); color: #fff; }
  td { background: rgba(255,255,255,0.04); }
  code { background: rgba(0,212,255,0.12); color: #ff6b6b; padding: 2px 6px; border-radius: 4px; }
  pre { background: #12122a !important; border-radius: 10px; border: 1px solid rgba(233,69,96,0.3); }
  pre code { color: #e8e8f0; background: none; }
  blockquote { border-left: 4px solid #e94560; background: rgba(233,69,96,0.08); padding: 8px 16px; border-radius: 0 8px 8px 0; }
  a { color: #00d4ff; } img { border-radius: 10px; }
  section::after { color: rgba(255,255,255,0.3); font-size: 0.7em; }
---

<!-- _class: lead -->

# ☁️ Cloud Computing

**Introdução à Computação · ADS**

*Computação sob demanda: da sala do servidor ao mundo*

![bg right:40% brightness:0.5](https://images.unsplash.com/photo-1544197150-b99a580bb7a8?w=600&h=400&fit=crop)

---

## 📖 Definição NIST

> Acesso **sob demanda** a um pool compartilhado de recursos computacionais. — Mell & Grance, 2011

| # | Característica |
|:-:|---------------|
| 1️⃣ | Self-service sob demanda |
| 2️⃣ | Acesso amplo pela rede |
| 3️⃣ | Pool de recursos compartilhado |
| 4️⃣ | Elasticidade rápida |
| 5️⃣ | Pay-as-you-go |

---

## 🧱 Modelos de Serviço

| Modelo | Você gerencia | Exemplo |
|--------|:------------:|---------|
| **IaaS** | App + SO + runtime | EC2, Azure VM |
| **PaaS** | App + dados | Heroku, App Service |
| **SaaS** | Apenas usa | Gmail, Office 365 |
| **FaaS** | Só a função | Lambda, Functions |

> Quanto mais *"aaS"*, menos controle — e menos responsabilidade infra.

---

## 🌐 Modelos de Implantação

| Modelo | Quem usa | Exemplo |
|--------|---------|---------|
| ☁️ **Pública** | Qualquer org. | AWS, Azure, GCP |
| 🏢 **Privada** | Apenas uma org. | OpenStack |
| 🔀 **Híbrida** | Pública + Privada | Maioria enterprise |
| 🌈 **Multi-cloud** | Vários provedores | Netflix |

---

## 🛡️ Responsabilidade Compartilhada

| Camada | IaaS | PaaS | SaaS |
|--------|:----:|:----:|:----:|
| Hardware / Rede | ☁️ | ☁️ | ☁️ |
| SO / Runtime | **🔑 Você** | ☁️ | ☁️ |
| Aplicação | **🔑 Você** | **🔑 Você** | ☁️ |
| Dados + Identidade | **🔑 Você** | **🔑 Você** | **🔑 Você** |

> 🔒 Seus dados e identidades são **sempre** sua responsabilidade.

---

## 📈 SLA — Disponibilidade

| SLA | Downtime / ano | Downtime / mês |
|:---:|:--------------:|:--------------:|
| 99% | 3.65 dias | 7.3 h |
| 99.9% | 8.76 h | 43.8 min |
| 99.99% | 52.6 min | 4.4 min |
| 99.999% | 5.26 min | 26.3 s |

**2 zonas 99.95% cada:**
$$A = 1 - (1 - 0{,}9995)^2 = 99{,}9999\%$$

---

## 🔺 Teorema CAP

> Em sistema distribuído, escolha **2 de 3** — Brewer, 2000

| Letra | Propriedade |
|:-----:|------------|
| **C** | Consistência — leitura mais recente |
| **A** | Disponibilidade — sempre responde |
| **P** | Tolerância a partição — funciona com falha de rede |

🗃️ Bancos NoSQL: geralmente sacrificam **C** para ganhar **A + P**.

---

## 💰 FinOps — Custo na Nuvem

| Modelo de preço | Economia | Risco |
|----------------|:--------:|-------|
| On-demand | 0% | Nenhum |
| Reserved 1 ano | ~35% | Compromisso |
| Reserved 3 anos | ~55% | Longo prazo |
| Spot | ~70-90% | Interrupção |

> ⚠️ Cloud *parece* barata, mas sem controle os custos **explodem**.

---

## 🏆 Big Three

| | AWS | Azure | GCP |
|:-:|:---:|:-----:|:---:|
| 📊 Share | ~31% | ~25% | ~11% |
| 💪 Forte | Amplitude | Enterprise | Data / ML |
| 🆓 Free | 12 meses | US$ 200 (estudante) | US$ 300 |

![bg right:25% opacity:0.15](https://images.unsplash.com/photo-1451187580459-43490279c0fa?w=400&fit=crop)

---

## 📚 Referências

- Mell & Grance (2011). *NIST Definition of Cloud Computing*
- Brewer (2000). *Towards Robust Distributed Systems*
- Marinescu (2022). *Cloud Computing*, 4ª ed.

**→ Checkpoint 03** · com módulo 05
