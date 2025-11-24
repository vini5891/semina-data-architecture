# 10 - Qualidade de Dados

Documentação das regras, indicadores e processos de Qualidade de Dados na arquitetura da Semina.

## 1. Objetivo

Garantir que os dados usados em análises, BI e tomada de decisão:

- sejam consistentes;
- tenham origem rastreável;
- cheguem no tempo certo;
- tenham nível de completude mínimo aceitável.

## 2. Dimensões de qualidade

Sugestão de dimensões a serem monitoradas:

- **Completude**: campos obrigatórios preenchidos?
- **Consistência**: valores coerentes entre sistemas/tabelas?
- **Acurácia**: os dados representam corretamente a realidade?
- **Pontualidade/Frescor**: o dado está atualizado conforme o SLA?
- **Unicidade**: não há duplicidades indevidas?

## 3. Regras de validação

Liste aqui as regras principais, por domínio/tabela. Exemplos:

- Vendas:
  - `Data_Venda` não pode ser futura.
  - `Valor_Venda` ≥ 0.
  - Cada `ID_Pedido` deve ser único por sistema origem.

- Produtos:
  - Todo SKU deve ter família, marca e categoria.
  - Produtos descontinuados devem estar marcados corretamente.

## 4. Controles automatizados

Descreva (mesmo que conceitualmente):

- checagens automáticas em pipelines (ex.: contagem de linhas esperadas);
- alertas quando um limite é ultrapassado (ex.: % de nulos > 5%);
- tratamento de falhas (reprocesso, quarentena, correção na origem).

## 5. Processo de tratamento de erros

Explique o fluxo:

1. Detecção do problema (alerta, usuário, monitoração).
2. Registro (ex.: planilha, ferramenta de ticket, backlog).
3. Análise de causa raiz (origem, transformação, consumo).
4. Correção.
5. Acompanhamento e prevenção.

## 6. Papéis e responsabilidades

- **Time de Dados**: implementar validações e alertas.
- **Donos de Domínio/Área**: validar regras de negócio e priorizar correções.
- **TI/Sistemas origem**: corrigir dados na fonte quando necessário.

## 7. Indicadores de qualidade

Conecte esta seção com a pasta `11-metricas-kpis`, indicando quais KPIs serão monitorados para qualidade (ex.: % de registros válidos, tempo médio de correção).
