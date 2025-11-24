# 03 - Governança de Dados

Este documento apresenta os princípios, políticas e práticas de governança adotadas no projeto de Arquitetura de Dados da Semina.

A governança garante que os dados sejam seguros, confiáveis, documentados e utilizados de forma correta em todas as áreas da empresa.

---

## 1. Princípios de Governança

A governança se baseia em quatro pilares principais:

### • Qualidade
Os dados precisam ser:
- consistentes  
- completos  
- atualizados  
- sem duplicidades  
- padronizados  

### • Segurança
Garantir que somente pessoas autorizadas tenham acesso aos dados, conforme:
- função  
- área  
- necessidade de negócio  

### • Confiabilidade
Indicadores e relatórios precisam refletir a verdade operacional da empresa.

### • Documentação
Todo fluxo, regra, estrutura de tabela e tratamento deve estar documentado no repositório.

---

## 2. Papéis e Responsabilidades

### **Data Owner**
- Responsável estratégico pelo dado  
- Normalmente uma área de negócio (ex.: Comercial, Financeiro)  
- Define regras e valida indicadores  

### **Data Steward**
- Responsável pela qualidade dos dados  
- Acompanha validações, atualizações e consistência  
- Mantém documentação de regras e tabelas  

### **Data Engineering (Você / Time Técnico)**
- Implementa pipelines e transformações  
- Garante versionamento e governança técnica  
- Documenta todos os fluxos e regras  
- Mantém arquitetura organizada  

### **Consumidores de Dados**
- Usuários de BI  
- Operações  
- Gestores  
- Diretoria  

---

## 3. Políticas de Acesso e Segurança

A governança define níveis de acesso por camada:

### **Nível 1 – Bronze (Restrito)**
- Acesso apenas para Engenharia de Dados  
- Dados brutos, possivelmente sensíveis  
- Estruturas próximas às fontes  

### **Nível 2 – Silver (Acesso Controlado)**
- Acesso concedido conforme necessidade da área  
- Dados tratados, limpos e padronizados  
- Base para análises internas  

### **Nível 3 – Gold (Acesso Gerencial)**
- Indicadores consolidados  
- Usuários de BI, gestores e áreas estratégicas  
- Dados prontos para consumo  

#### Regras Gerais:
- Proibido extrair tabelas Gold para manipulação manual que gere “números paralelos”  
- Sem envio de arquivos fora da plataforma  
- Sem alteração de dados direto nas camadas  
- Tudo deve passar pelo pipeline e estar documentado  

---

## 4. Catálogo de Dados

O catálogo deve registrar:

- Nome da tabela  
- Nome de cada coluna  
- Descrição  
- Tipo de dado  
- Origem do dado  
- Regras aplicadas  
- Destino (Silver, Gold)  
- Periodicidade de atualização  

O catálogo será armazenado na pasta:  
`docs/04-modelagem/`

---

## 5. Linhagem dos Dados (Data Lineage)

A linhagem rastreia o caminho completo dos dados:

**Fonte → Bronze → Silver → Gold → BI**

Para cada tabela, a documentação de lineage deve registrar:

- Origem exata  
- Transformações aplicadas  
- Regras de negócio envolvidas  
- Campos criados, alterados ou removidos  
- Destino final nas camadas  

Diagramas de lineage serão armazenados em:  
`docs/02-arquitetura/desenhos`

---

## 6. Qualidade dos Dados (Data Quality)

Regras de validação recomendadas:

- Duplicidade  
- Campos obrigatórios  
- Formato válido (datas, números, chaves)  
- Validação de regras comerciais  
- Volume mínimo esperado  
- Diferença versus histórico  
- Conformidade com tabelas auxiliares  

Falhas e validações serão registradas em:  
`docs/06-monitoramento/`

---

## 7. Versionamento e Auditoria

### **Versionamento**
- Todos os pipelines, regras e modelos devem ser versionados neste repositório  
- Alterações só podem ocorrer via commit/pull request  
- Histórico sempre disponível  

### **Auditoria**
- Logs de ingestão  
- Histórico de execuções  
- Data e hora  
- Erros registrados  
- Status completo de pipelines  

---

## 8. Próximos Passos

- Criar catálogo de dados inicial  
- Mapear acessos por área e nível  
- Criar diagramas de lineage dos fluxos principais  
- Definir políticas formais de retenção e arquivamento  
- Revisar o documento com áreas-chave (Comercial, Marketing, Financeiro, Logística)  

---

Este documento será atualizado continuamente conforme a maturidade de governança evolui.
