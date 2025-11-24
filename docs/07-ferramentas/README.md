# 07 - Ferramentas, Tecnologias e Serviços Utilizados

Este documento apresenta todas as ferramentas utilizadas na Arquitetura de Dados da Semina. São listados os componentes essenciais para ingestão, armazenamento, transformação, governança e visualização de dados.

# 1. Microsoft Fabric
Plataforma principal escolhida pela facilidade de adoção, integração nativa com Power BI e baixo custo operacional para um time pequeno.

Componentes principais:
- OneLake
- Data Factory (pipelines de ingestão)
- Lakehouse (Bronze, Silver, Gold)
- SQL Endpoint
- Notebooks
- Power BI Workspace integrado

Benefícios:
- arquitetura unificada
- governança centralizada
- baixo código para ingestão
- escalabilidade
- integração com AD (segurança)
- fácil capacitação do time

# 2. OneLake
Armazena todos os dados do projeto. É o “data lake corporativo” dentro do Fabric.

Características:
- estrutura em camadas
- suporte a tabelas Delta
- versionamento
- compartilhamento seguro
- armazenamento unificado para Bronze, Silver e Gold

# 3. Data Factory (Fabric)
Camada responsável pela ingestão das fontes.
Funções:
- extrair dados de TOTVS, planilhas e sistemas externos
- montar pipelines diários ou semanais
- aplicar lógicas de controle de ingestão
- monitorar execuções e falhas

Elementos usados:
- Dataflows Gen2
- Pipelines
- Schedule triggers

# 4. Lakehouse (Fabric)
Onde os dados são realmente armazenados e transformados.

Papel de cada camada:
- Bronze: dados brutos
- Silver: dados tratados e padronizados
- Gold: modelos de negócio

Ferramentas internas:
- Notebooks
- SQL Endpoint
- Tabelas Delta
- Versionamento por camadas

# 5. SQL Endpoint
Usado para:
- consultas rápidas
- validações
- testes de modelo
- criação de tabelas Gold
- otimizações de leitura para o BI

Benefícios:
- alto desempenho
- compatível com T-SQL
- acesso seguro e governado

# 6. Power BI
Ferramenta oficial de visualização da Semina.

Usos:
- criação de dashboards gerenciais
- relatórios por área
- controle de KPIs
- análises por domínio: Comercial, Marketing, Logística, Financeiro

Integração com Fabric:
- acesso direto ao Lakehouse Gold
- refresh automático
- segurança por workspace
- governança centralizada

# 7. TOTVS / Protheus
Fonte principal de dados operacionais.

Dados extraídos:
- pedidos
- faturamento
- estoque
- produtos
- clientes
- movimentações logísticas

Mecanismos possíveis:
- exportações automáticas
- integrações via API (quando liberadas)
- ingestão de arquivos padronizados

# 8. Planilhas Operacionais
Usadas temporariamente até a automação total.

Exemplos:
- sell-out
- metas
- campanhas
- evidências comerciais

Processo:
- padronização de layout
- ingestão Bronze
- validação na Silver

# 9. IQVIA
Base externa com dados de mercado e concorrência.

Usos:
- análise de consumo
- sell-out de mercado
- comparações KY x concorrentes
- projeções de mercado

Ingestão:
- semanal ou mensal (dependendo da disponibilidade)
- tratamento Silver para padronização

# 10. Outras Ferramentas de Apoio
- GitHub (versionamento e documentação)
- Excel (validações rápidas)
- Draw.io ou Whimsical (diagramas)
- ChatGPT/IA (apoio técnico e documentação)
- VS Code (edição de queries e scripts opcionais)

# 11. Próximos Passos
- Definir ferramentas futuras para CI/CD
- Padronizar criação de notebooks no Fabric
- Criar templates de tabelas Bronze/Silver/Gold
- Documentar APIs e conectores adicionais
