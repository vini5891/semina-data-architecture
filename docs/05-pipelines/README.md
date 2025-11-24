# 05 - Pipelines de Dados (Ingestão, Tratamento e Publicação)

Este documento descreve os pipelines de dados utilizados na Arquitetura de Dados da Semina, incluindo ingestão das fontes, processamento (Bronze → Silver → Gold), validações, agendamentos e padrões operacionais.

---

# 1. Visão Geral dos Pipelines
Os pipelines definem como os dados fluem desde o ERP e demais sistemas até chegarem às tabelas finais consumidas pelo BI.  
Incluem: ingestão, limpeza, padronização, enriquecimento, agregação, auditoria e governança.

Fluxo padrão:
**Fonte → Ingestão (Bronze) → Transformação (Silver) → Modelos (Gold) → BI**

---

# 2. Fontes de Dados Consideradas
**TOTVS/Protheus**  
Pedidos, itens, clientes, produtos, estoque, movimentações, custos.

**Planilhas Operacionais**  
Sell-out, campanhas, metas, evidências comerciais.

**IQVIA**  
Bases de mercado (Consumo, SellOut, DDD).

**Sistemas de Logística**  
Transferências, entradas e saídas.

**Outras fontes futuras**  
Google Drive, SharePoint, APIs e bancos externos.

---

# 3. Pipeline Bronze – Ingestão de Dados Brutos
A ingestão captura os dados exatamente como vieram da origem.

Processos envolvidos:
- conexão com o ERP ou upload estruturado de planilhas  
- identificação do lote  
- registro de data/hora de ingestão  
- persistência sem tratamento  
- logs de auditoria

Padrão de tabelas:
`bronze_<dominio>_<origem>_<nome>`

Exemplos:
- bronze_comercial_protheus_pedidos
- bronze_marketing_iqvia_sellout

---

# 4. Pipeline Silver – Padronização e Limpeza
A Silver aplica transformações que tornam os dados utilizáveis e confiáveis.

Processos principais:
- padronização de tipos  
- remoção de valores inconsistentes  
- unificação de nomes/códigos  
- deduplicação  
- criação de chaves substitutas  
- junções entre fontes  
- preenchimento de colunas derivadas (ano_mes, familia, marca, etc.)

Padrão:
`silver_<dominio>_<tabela>`

Exemplos:
- silver_comercial_pedidos
- silver_marketing_produtos
- silver_logistica_estoque

---

# 5. Pipeline Gold – Modelos de Negócio (BI)
A Gold gera tabelas agregadas e modelos otimizados para BI.

Processos:
- cálculos de KPIs oficiais  
- agregações mensais e semanais  
- métricas comerciais (volume, faturamento, giro, rentabilidade)  
- integração com calendário  
- validações finais de qualidade

Padrão:
`gold_<dominio>_<kpi/tabela>`

Exemplos:
- gold_comercial_vendas_mensal
- gold_marketing_kpi_sellout
- gold_logistica_estoque_kpi

---

# 6. Auditoria e Monitoramento
Toda execução de ETL/ELT inclui:
- logging detalhado (inicio/fim, volume, erros)  
- tabelas de controle  
- validação de schema  
- comparações de volume entre etapas  
- alertas para falhas de ingestão ou transformação  

Tabelas recomendadas:
- auditoria_ingestao
- auditoria_transformacao
- auditoria_qualidade

---

# 7. Agendamentos e Frequência
Sugestão de periodicidade para a Semina:

**Diário (07h/08h)**
- Pedidos, Clientes, Produtos, Estoque  
- Sell-out e metas operacionais  

**Semanal**
- IQVIA  
- Campanhas e ações de marketing  

**Mensal**
- Consolidações financeiras  
- KPIs estratégicos  

---

# 8. Padrões Operacionais
- pipelines devem ser versionados  
- nenhuma transformação ocorre na Bronze  
- Silver deve sempre gerar dados consistentes e padronizados  
- Gold deve ser “confiável para tomar decisão oficial”  
- todos os pipelines seguem nomenclatura padronizada  
- nenhum dado deve ser alterado manualmente em qualquer camada

---

# 9. Próximos Passos
- Documentar fluxos TOTVS → Bronze  
- Criar dicionário técnico Silver  
- Listar KPIs oficiais da Gold  
- Definir SLAs de ingestão e atualização  
- Adicionar diagramas na pasta `/design/diagramas/`  

