# 02 - Arquitetura de Dados (Data Lakehouse)

Este documento descreve a visão de arquitetura de dados proposta para a Semina, com foco em um modelo de Data Lakehouse moderno, escalável e governado.

## Visão geral da arquitetura

A arquitetura proposta segue o conceito de **Data Lakehouse**, combinando:

- flexibilidade de um Data Lake  
- organização e performance de um Data Warehouse  
- governança centralizada e camadas bem definidas  

A ideia é ter um ambiente único onde os dados são ingeridos, tratados, organizados e disponibilizados para análise, relatórios e iniciativas futuras de inteligência artificial.

## Princípios da arquitetura

- **Centralização** dos dados em uma única plataforma analítica  
- **Separação por camadas** (Bronze, Silver, Gold)  
- **Governança** desde a origem até o consumo  
- **Reprodutibilidade** dos processos (pipelines versionados e documentados)  
- **Escalabilidade** para suportar novos domínios de dados  
- **Baixo acoplamento** entre fontes, tratamentos e camadas de consumo  

## Componentes principais

Os principais blocos da arquitetura são:

- **Camada de ingestão**: responsável por receber dados de sistemas internos e externos  
- **Camada de armazenamento (Data Lakehouse)**: estrutura de tabelas e arquivos em diferentes níveis de qualidade  
- **Camada de transformação**: pipelines de ETL/ELT que aplicam regras de negócio  
- **Camada de consumo**: modelos analíticos, visões para BI e acesso por times de negócio  
- **Camada de governança**: segurança, catálogo de dados, políticas de acesso e trilhas de auditoria  

Os detalhes de cada componente serão refinados conforme o projeto avança.

## Camadas de dados (Bronze, Silver, Gold)

### Camada Bronze
- Recebe dados quase brutos, com o mínimo de tratamento necessário para armazenamento  
- Mantém estrutura próxima à fonte de origem  
- É a base histórica e detalhada para reprocessamentos futuros  

### Camada Silver
- Dados já padronizados, limpos e com regras básicas de qualidade  
- Estruturas mais amigáveis para análise, com chaves e relacionamentos claros  
- Utilizada como base para construção de modelos analíticos e consolidações  

### Camada Gold
- Visões consolidadas, orientadas a negócio e diretamente ligadas aos indicadores de gestão  
- Tabelas otimizadas para consumo em ferramentas de BI  
- Serve de base oficial para relatórios gerenciais e executivos  

## Fontes de dados previstas

Algumas fontes previstas para integração nesta arquitetura:

- **ERP TOTVS / Protheus** (dados de faturamento, pedidos, estoque, clientes, etc.)  
- **Plataformas externas** (por exemplo, dados de mercado e auditorias como IQVIA)  
- **Planilhas e arquivos manuais** usados temporariamente pelas áreas de negócio  
- **Outras bases internas** que venham a ser mapeadas ao longo do projeto  

Cada fonte terá seu fluxo próprio de ingestão, respeitando regras de qualidade e governança.

## Fluxo de dados em alto nível

1. Os dados são extraídos das fontes de origem (ERP, arquivos, sistemas externos).  
2. São carregados na **camada Bronze**, preservando a granularidade original.  
3. Processos de transformação movem os dados para a **camada Silver**, já padronizados.  
4. A partir da Silver, são geradas estruturas consolidadas na **camada Gold**, voltadas para relatórios e análises.  
5. As camadas Gold são então consumidas por ferramentas de BI e por usuários analíticos.

## Decisões técnicas iniciais

- Adoção de uma arquitetura em camadas (Bronze, Silver, Gold) como padrão de organização  
- Separação clara entre dados brutos, tratados e consolidados  
- Documentação das regras de negócio no repositório, junto aos pipelines e modelos  
- Uso de ferramentas de BI conectadas às camadas de consumo, evitando extrações manuais sempre que possível  

Detalhes específicos de tecnologia (ferramentas, serviços, configurações) serão documentados em arquivos complementares deste diretório e na pasta de ferramentas.

## Próximos passos de arquitetura

- Detalhar os fluxos de ingestão por fonte de dados  
- Definir os modelos de tabelas das camadas Silver e Gold  
- Mapear indicadores chave por área (Comercial, Marketing, Logística, Financeiro)  
- Criar diagramas visuais da arquitetura e dos fluxos de dados  
- Revisar as decisões com as áreas envolvidas e ajustar quando necessário  

---

Este documento será atualizado continuamente conforme novas decisões de arquitetura forem tomadas e o projeto evoluir.
