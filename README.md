# Arquitetura de Dados da Semina

Repositório dedicado à documentação oficial da Arquitetura de Dados da Semina.  
Aqui estão organizados todos os estudos, decisões técnicas, padrões, fluxos de dados, modelagem, governança e processos necessários para implantação e evolução do Data Lakehouse da empresa.

Este projeto tem como objetivo consolidar práticas modernas de Engenharia de Dados utilizando Microsoft Fabric, OneLake, Power BI, governança de dados e integrações com sistemas corporativos (TOTVS, IQVIA, entre outros).

---

# 📘 Índice Oficial da Documentação

A documentação está organizada em capítulos dentro do diretório `docs/`, seguindo a jornada natural de construção de um Data Lakehouse.

### **00 – Contexto**
Visão geral do negócio, dores atuais, motivadores e objetivos estratégicos.  
🔗 [/docs/00-contexto](./docs/00-contexto)

### **01 – Requisitos**
Levantamento de requisitos funcionais, técnicos e operacionais.  
🔗 [/docs/01-requisitos](./docs/01-requisitos)

### **02 – Arquitetura**
Visão macro e detalhada da plataforma de dados, incluindo diagrama conceptual, componentes, camadas e fluxos.  
🔗 [/docs/02-arquitetura](./docs/02-arquitetura)

### **03 – Governança**
Políticas de dados, RLS, LGPD, papéis e responsabilidades.  
🔗 [/docs/03-governanca](./docs/03-governanca)

### **04 – Modelagem**
Modelagem lógica, física, camadas Bronze/Silver/Gold, entidades e domínios.  
🔗 [/docs/04-modelagem](./docs/04-modelagem)

### **05 – Pipelines**
Desenho de pipelines, ingestão, transformações, padrões e boas práticas.  
🔗 [/docs/05-pipelines](./docs/05-pipelines)

### **06 – Monitoramento**
Observabilidade, alertas, logs, falhas e reprocessamentos.  
🔗 [/docs/06-monitoramento](./docs/06-monitoramento)

### **07 – Ferramentas**
Softwares, plataformas e tecnologias utilizadas no ecossistema.  
🔗 [/docs/07-ferramentas](./docs/07-ferramentas)

### **08 – Integrações**
Fontes de dados, especificações de APIs, fluxos TOTVS/IQVIA e conectores.  
🔗 [/docs/08-integracoes](./docs/08-integracoes)

### **09 – Segurança**
Diretrizes de segurança, acesso, segregação de dados e classificação.  
🔗 [/docs/09-seguranca](./docs/09-seguranca)

### **10 – Qualidade de Dados**
Regras, validações, métricas de consistência e processos de correção.  
🔗 [/docs/10-qualidade-dados](./docs/10-qualidade-dados)

### **11 – Métricas & KPIs**
Indicadores técnicos, operacionais e de negócio da plataforma de dados.  
🔗 [/docs/11-metricas-kpis](./docs/11-metricas-kpis)

---

# 🧩 Escopo Geral do Projeto

- Estruturar um Data Lakehouse moderno para suportar análises, BI e previsões.  
- Criar governança eficiente e escalável.  
- Reduzir retrabalho operacional, dependência de planilhas e ETL manual.  
- Automatizar ingestão, qualidade e disponibilização dos dados.  
- Gerar autonomia analítica para Comercial, Marketing, Logística e Financeiro.  

---

# 📌 Tecnologias Principais
- **Microsoft Fabric / OneLake**
- **Power BI**
- **Pipelines (Data Factory)**  
- **Lakehouse / Delta**
- **Python & SQL**
- **Totvs (Protheus / MI / APIs)**
- **IQVIA Sell-Out**
- **GitHub (documentação e versionamento)**

---

# 👤 Autor
Documentação estruturada por **Vinícius Soares**, responsável pela iniciativa de modernização dos dados na Semina.

