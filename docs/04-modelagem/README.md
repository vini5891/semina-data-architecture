# 04 - Modelagem de Dados (Bronze, Silver e Gold)
Este documento apresenta o padrão de modelagem de dados adotado no projeto de Arquitetura de Dados da Semina, incluindo definições de tabelas, camadas, regras de negócio e estruturas relacionais. A modelagem serve como base para garantir consistência, escalabilidade e governança em todos os domínios de dados.

# 1. Visão Geral da Modelagem
A modelagem segue o padrão Data Lakehouse, estruturado em três camadas: Bronze (dados brutos), Silver (dados tratados e padronizados) e Gold (dados consolidados para consumo). Cada camada tem um papel claro dentro do fluxo de transformação.

# 2. Camada Bronze — Dados Brutos
A Bronze armazena dados como vieram da fonte, com mínimo tratamento.
**Características:** estrutura fiel ao ERP, planilha ou sistema externo; tipos de dados originais; possibilidade de nulos e duplicidades; usada para auditoria.  
**Exemplos:** bronze_protheus_pedidos, bronze_planilhas_estoque, bronze_iqvia_vendas  
**Regras:** nunca alterar dados manualmente; registrar data/hora da ingestão; identificar origem do arquivo/lote.

# 3. Camada Silver — Dados Tratados e Padronizados
A Silver engloba padronização, limpeza, deduplicação, criação de chaves, validações e enriquecimentos.
**Exemplos:** silver_pedidos, silver_clientes, silver_produtos, silver_calendario  
**Regras comuns:** datas em formato ISO (YYYY-MM-DD); remoção de nulos; padronização de códigos; criação de colunas calculadas como ano_mes, cliente_normalizado, produto_familia.

# 4. Camada Gold — Modelos de Negócio
Tabelas 100% confiáveis, otimizadas para BI e decisões oficiais.
**Exemplos:** gold_vendas_mensal, gold_rentabilidade_produto, gold_estoque_kpi, gold_performance_marcas  
**Regras:** tabelas agregadas, KPIs revisados, fórmulas documentadas, performance otimizada.

# 5. Domínios de Dados
Domínios previstos:  
**Comercial:** pedidos, faturamento, clientes, metas, marcas (KY, Amamente, Della, Nuaa).  
**Marketing:** sell-in/sell-out, IQVIA, campanhas, produtos.  
**Logística:** estoque, movimentações, transferências.  
**Financeiro:** custos, DRE, centros de custo.

# 6. Padrões de Nomenclatura
Padrão: camada_dominio_tabela  
**Exemplos:** silver_comercial_pedidos, gold_marketing_sellout_kpi, bronze_financeiro_dre_raw  
**Colunas:** snake_case, sem acentos e sem espaços (ex.: data_pedido, valor_total, codigo_cliente).

# 7. Relacionamentos (Modelo Lógico)
Modelo estrela (Star Schema) na Gold.  
**Fatos:** fato_vendas, fato_estoque, fato_sellout, fato_transferencias  
**Dimensões:** dim_cliente, dim_produto, dim_calendario, dim_marca, dim_regiao  
Fatos se relacionam com dimensões via chaves substitutas. Dimensões Silver → Dimensões Gold.

# 8. Calendário (Dimensão de Tempo)
A dimensão calendário contém campos padrão como data, ano, mes, ano_mes, trimestre, dia_da_semana, nome_mes. Criada na Silver e usada em toda a Gold.

# 9. Regras de Negócio
Exemplos:  
**Regra 1:** valor_liquido = valor_bruto - descontos - impostos  
**Regra 2:** produto_familia deriva de silver_produtos.codigo_familia  
**Regra 3:** vendas válidas = pedidos com status Faturado e data >= 2023  
Todas as regras devem ser ampliadas conforme o projeto evolui.

# 10. Próximos Passos
Criar tabelas Silver de Clientes, Produtos e Pedidos; definir tabelas Gold prioritárias (Vendas e Sell-out); construir diagrama lógico na pasta /design/diagramas; documentar calendário; criar catálogo das tabelas dentro desta mesma pasta.
