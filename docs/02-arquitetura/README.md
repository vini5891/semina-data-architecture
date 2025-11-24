# 02 - Arquitetura de Dados (Data Lakehouse)

Este documento descreve a visão de arquitetura de dados proposta para a Semina, com foco em um modelo de Data Lakehouse moderno, escalável e governado.

---

# 📌 Visão geral da arquitetura

A arquitetura segue o conceito de **Data Lakehouse**, combinando:

- a flexibilidade de um Data Lake;  
- a organização e performance de um Data Warehouse;  
- governança centralizada em todas as camadas.

O objetivo é construir um ambiente único onde os dados são ingeridos, tratados, organizados e disponibilizados para análises, BI e futuras iniciativas de Inteligência Artificial.

---

# 🧩 Diagrama geral da arquitetura (visão textual)

```text
                        ┌────────────────────┐
                        │   Sistemas Fonte    │
                        │────────────────────│
                        │  TOTVS (Protheus)   │
                        │  IQVIA Sell-Out     │
                        │  Excel / CSV        │
                        │  APIs externas      │
                        └─────────┬──────────┘
                                  │
                                  ▼
                    ┌────────────────────────────┐
                    │     Ingestão (Fabric)       │
                    │ Pipelines / Dataflows / API │
                    └─────────┬──────────────────┘
                                  │
                                  ▼
                 ┌─────────────────────────────────────┐
                 │         OneLake / Lakehouse          │
                 │──────────────────────────────────────│
                 │ Bronze – Raw/Histórico               │
                 │ Silver – Tratado/Padronizado         │
                 │ Gold   – Analítico/Consolidado       │
                 └──────────────────┬───────────────────┘
                                    │
                                    ▼
                   ┌────────────────────────────────┐
                   │  Camada Semântica (Power BI)   │
                   │ Modelos / Métricas / RLS       │
                   └─────────────────┬──────────────┘
                                     │
                                     ▼
                     ┌────────────────────────────────┐
                     │   Consumo por Área de Negócio   │
                     │ Comercial • Marketing • Finance │
                     │ Logística • Diretoria          │
                     └────────────────────────────────┘
