# 09 - Segurança

Documentação da camada de segurança da arquitetura de dados da Semina.  
Aqui ficam as diretrizes para proteger dados, acessos, ambientes e artefatos do Data Lakehouse.

## 1. Objetivo

Definir como a segurança é tratada no projeto de dados da Semina, cobrindo:

- controle de acesso a dados e relatórios;
- segregação por área (Comercial, Marketing, Financeiro, etc.);
- proteção de dados sensíveis;
- rastreabilidade e auditoria de ações.

## 2. Escopo

Esta documentação se aplica a:

- Lakehouse (camadas Bronze, Silver, Gold);
- Microsoft Fabric / OneLake;
- Power BI e demais ferramentas de consumo;
- integrações com sistemas fonte (TOTVS, IQVIA, etc.).

## 3. Princípios de segurança

- **Menor privilégio possível**: cada usuário vê apenas o que precisa.
- **Segregação de funções**: quem desenvolve não é o mesmo que aprova acesso.
- **Auditoria e rastreabilidade**: ações relevantes devem gerar log.
- **Dados sensíveis protegidos**: dados pessoais, financeiros e estratégicos têm tratamento especial.

## 4. Controles de acesso

Descreva aqui:

- grupos de acesso (ex.: `BI_Comercial`, `BI_Marketing`, `BI_Diretoria`);
- níveis de permissão (leitura, escrita, administração);
- uso de RLS (Row-Level Security) nos relatórios;
- como é feito o pedido, aprovação e revisão de acessos.

## 5. Classificação de dados

Sugestão de classificação:

- **Público**: pode ser compartilhado externamente.
- **Interno**: uso somente dentro da Semina.
- **Confidencial**: restrito a áreas específicas.
- **Restrito**: acesso altamente controlado (ex.: folha, metas individuais).

Explique aqui exemplos de cada classe e como isso impacta acesso nos relatórios.

## 6. Responsabilidades

- **Time de Dados**: implementar regras de segurança nas camadas de dados e BI.
- **Gestores das áreas**: aprovar ou negar pedidos de acesso.
- **TI/Infra**: garantir segurança em nível de tenant, rede, identidade.
- **Usuários finais**: uso responsável dos dados e sigilo quando necessário.

## 7. Referências

- Políticas internas de segurança da informação (quando existirem).
- Documentação de segurança do Microsoft Fabric e Power BI.
