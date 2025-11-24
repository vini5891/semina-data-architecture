# 11 - Métricas e KPIs da Plataforma de Dados

Documentação dos indicadores usados para acompanhar saúde, eficiência e impacto da Arquitetura de Dados da Semina.

## 1. Objetivo

Definir quais métricas serão usadas para:

- monitorar a operação dos pipelines;
- acompanhar qualidade de dados;
- avaliar o valor gerado para o negócio.

## 2. KPIs técnicos (plataforma)

Alguns exemplos que você pode adaptar:

- **Latência de carga**: tempo entre dado gerado no sistema origem e disponível na camada Gold.
- **Taxa de sucesso dos pipelines**: % de execuções concluídas sem erro por período.
- **Tempo médio de reprocesso**: quanto tempo se leva para corrigir uma falha.
- **Custo estimado de processamento** (se houver dados de custo de cloud/Fabric).

Descreva aqui:
- nome do KPI,
- fórmula,
- fonte de dados,
- frequência de acompanhamento,
- responsáveis.

## 3. KPIs de qualidade de dados

Conectados à pasta `10-qualidade-dados`, por exemplo:

- % de registros com campos obrigatórios preenchidos;
- nº de inconsistências detectadas por mês;
- tempo médio para correção de inconsistências;
- % de tabelas críticas com monitoria ativa.

## 4. KPIs de negócio

Aqui você pode colocar indicadores que mostram o impacto do projeto:

- nº de usuários ativos consumindo relatórios;
- nº de áreas atendidas (Comercial, Marketing, Financeiro, etc.);
- redução estimada de tempo em atividades manuais (antes x depois);
- indicadores específicos do projeto (ex.: aumento de visibilidade de sell-out, giro, ruptura, etc.).

## 5. Visualização e acompanhamento

Explique:

- onde esses KPIs serão visualizados (ex.: painel interno em Power BI);
- qual a frequência de revisão (semanal, mensal, trimestral);
- quem participa das reuniões de acompanhamento.

## 6. Metas e evolução

Registre aqui, com o tempo:

- metas de cada KPI;
- marcos importantes (ex.: “a partir de 2026, 100% dos domínios críticos com monitoria de qualidade ativa”).

Isso ajuda a contar a história de evolução da plataforma.
