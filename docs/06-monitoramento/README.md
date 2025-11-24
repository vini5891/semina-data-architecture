# 06 - Monitoramento, Logs e Observabilidade

Este documento descreve a estratégia de monitoramento, logs, alertas e observabilidade dos pipelines de dados da Semina. O objetivo é garantir confiabilidade, transparência, rastreabilidade e rápida identificação de falhas.

# 1. Visão Geral
O monitoramento acompanha todas as etapas da arquitetura:
- ingestão (Bronze)
- transformação (Silver)
- consolidação (Gold)
- qualidade dos dados
- performance dos pipelines
- consumo no BI

O objetivo é detectar falhas cedo, garantir estabilidade e manter indicadores confiáveis.

# 2. Tipos de Monitoramento
O processo é dividido em quatro frentes principais:

## 2.1 Monitoramento de Execução
Acompanha:
- início e fim de cada pipeline
- tempo de execução
- status: sucesso, falha, parcial
- volume processado por tabela
- origem e data do lote

## 2.2 Monitoramento de Qualidade (Data Quality)
Valida:
- duplicidade de registros
- linhas nulas ou incompletas
- formatos inválidos
- inconsistências comerciais
- divergências com histórico
- volumes anormais

## 2.3 Monitoramento de Performance
Avalia:
- tempo médio de ingestão
- tempo médio de transformação
- consultas frequentes e pesadas
- consumo excessivo de recursos

## 2.4 Monitoramento de Consumo (BI)
Acompanha:
- dashboards atualizados
- acessos
- falhas de refresh
- tabelas Gold desatualizadas

---

# 3. Logs e Tabelas de Auditoria
Todos os pipelines devem gerar logs padronizados.

## 3.1 Tabela auditoria_ingestao
Campos recomendados:
- id_lote
- fonte
- data_ingestao
- volume_registros
- status
- arquivo_origem
- mensagem_log

## 3.2 Tabela auditoria_transformacao
Campos:
- id_execucao
- tabela_origem
- tabela_destino
- registros_lidos
- registros_gravados
- tempo_execucao
- mensagem

## 3.3 Tabela auditoria_qualidade
Campos:
- id_validacao
- tabela
- regra_validada
- resultado
- percentual_erro
- detalhes

---

# 4. Alertas e Notificações
Os alertas podem ser enviados por e-mail, Teams ou sistema de monitoramento.

Situações que devem gerar alerta:
- falha total do pipeline
- volume menor que 70% do normal
- duplicidade acima do limite
- schema inesperado
- Gold desatualizada
- falha no refresh do BI

Categorias:
- Alerta Crítico (pipeline quebrado)
- Alerta Moderado (qualidade ruim)
- Alerta Informativo (atualização concluída)

---

# 5. Recomendações Operacionais
- registrar todos os pipelines no repositório
- nunca suprimir erros silenciosamente
- manter histórico mínimo de 90 dias
- validar dados críticos antes de publicar na Gold
- garantir que BI sempre consuma a Gold, não Silver
- priorizar automação total do monitoramento

---

# 6. Próximos Passos
- Criar tabelas de auditoria na Silver
- Definir limites de qualidade por tabela
- Configurar alertas automáticos
- Criar relatório interno de falhas
- Integrar monitoramento com área responsável

