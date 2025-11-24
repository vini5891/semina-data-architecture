Este documento apresenta todas as integrações de dados utilizadas no projeto de Arquitetura de Dados da Semina. Inclui sistemas internos, parceiros externos, APIs, arquivos e quaisquer mecanismos que alimentam o Data Lakehouse.

1. Fontes internas
TOTVS Protheus

ERP principal da empresa.

Contém dados de vendas, estoque, financeiro, produção, logística e cadastro de produtos.

Integração via exportações automáticas, consultas SQL ou conectores específicos.

Bancos de Dados Internos

Bases relacionais utilizadas pelos sistemas internos.

Fonte de dados transacionais e operacionais.

Extração feita por consultas SQL ou conectores certificados.

2. Fontes externas
IQVIA

Fonte de informações do mercado Farma.

Dados utilizados para análises de consumo, participação de mercado e performance por região.

Entregue via arquivos estruturados (Excel/CSV).

Fornecedores e parceiros

Envio de relatórios periódicos.

Sell-out, NF-es, campanhas, tabelas de preços e evidências.

APIs externas

Comunicação com plataformas de automação, marketing e integrações específicas.

Utiliza autenticação baseada em token ou OAuth.

3. Processos de ingestão

As integrações seguem o padrão Bronze → Silver → Gold:

Bronze

Recebe os dados exatamente como chegam.

Mantém histórico e rastreabilidade.

Nenhuma transformação aplicada.

Silver

Padronização e limpeza dos dados.

Correção de tipos, normalização de tabelas e enriquecimentos.

Gold

Tabelas finais otimizadas para consumo analítico.

Alimenta Power BI e análises avançadas.

4. Periodicidade das integrações

Diária: vendas, estoque, pedidos, cadastros.

Semanal: dados IQVIA.

Mensal: fechamentos financeiros.

Sob demanda: campanhas, eventos, atualizações extraordinárias.

5. Segurança e autenticação

Uso obrigatório de cofre de segredos (Key Vault ou equivalente).

Nenhuma credencial no código ou repositório.

Preferência por autenticação via token ou OAuth.

Controle de acesso baseado em papéis (RBAC).

6. Padrão de rastreabilidade (Data Lineage)

A linhagem documenta o caminho completo de cada dado:

Origem → Bronze → Silver → Gold → BI


Permite auditoria, monitoramento e reconstrução lógica do fluxo.

7. Melhorias futuras

Redução de ingestões manuais.

Padronização das APIs internas.

Catálogo de dados completo.

Automação de falhas com alertas em tempo real.

Sincronização incremental sempre que possível.
