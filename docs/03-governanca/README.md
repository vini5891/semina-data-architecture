# 03 - Governança de Dados

Este documento apresenta os princípios, políticas e práticas de governança adotadas no projeto de Arquitetura de Dados da Semina.

A governança garante que os dados sejam **seguros, confiáveis, documentados e utilizados de forma correta** em todas as áreas da empresa.

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
TODO fluxo, camada, regra e tabela deve ser documentado no repositório.

---

## 2. Papéis e Responsabilidades

### **Data Owner**
- Dono do dado.
- Normalmente uma área de negócio (ex.: Comercial, Financeiro).
- Define regras e valida indicadores.

### **Data Steward**
- Responsável pela qualidade e consistência.
- Faz validações rotineiras.
- Mantém documentação atualizada.

### **Data Engineering (Você / Time Técnico)**
- Implementa pipelines, camadas, tabelas e regras de negócio.
- Garante governança técnica.
- Responsável por versionamento e monitoramento.

### **Consumidores de Dados**
- Usuários de BI.
- Operações.
- Gestores.
- Executivos.

---

## 3. Políticas de Acesso e Segurança

A governança define níveis de acesso:

### **Nível 1 – Bronze (restrito)**
- Acesso apenas para Engenharia de Dados.
- Contém dados brutos, possivelmente sensíveis.

### **Nível 2 – Silver (parcial)**
- Acesso controlado por área ou necessidade.
- Dados tratados, mas ainda detalhados.

### **Nível 3 – Gold (amplo acesso)**
- Indicadores prontos.
- Área Comercial, Marketing, Logística e Financeiro podem consumir via BI.

### Regras gerais:
- Sem envio de arquivos fora da plataforma.
- Sem tabelas manuais fora do repositório.
- Sem alterar dados diretamente nas camadas.

---

## 4. Catálogo de Dados

O catálogo registra:
- nome das tabelas
- coluna por coluna
- descrição
- tipo de dado
- regras de formação
- origem do dado
- destino (Silver → Gold)
- periodicidade

O catálogo será criado posteriormente e armazenado na pasta `docs/04-modelagem/`.

---

## 5. Linhagem dos Dados (Data Lineage)

A linhagem rastreia o caminho completo:

