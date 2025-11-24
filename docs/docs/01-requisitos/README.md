# 01 - Requisitos do Projeto

Este documento registra os requisitos funcionais, não funcionais e estratégicos que orientam a implementação do Data Lakehouse da Semina.

## 1. Requisitos Funcionais
- Centralizar dados oriundos de TOTVS/Protheus, planilhas e sistemas externos.
- Criar um repositório único para KPIs comerciais, marketing, logística e financeiro.
- Permitir automação parcial ou total dos fluxos de ingestão.
- Disponibilizar camadas organizadas (Bronze, Silver, Gold).
- Criar base consolidada para os painéis de BI.
- Registrar regras de negócio de forma documentada.

## 2. Requisitos Não Funcionais
- Arquitetura escalável e de baixo custo operacional.
- Governança clara: acesso, segurança, versionamento e trilha de auditoria.
- Padronização de nomenclaturas, tabelas e schemas.
- Monitoramento e logs para identificar falhas.
- Redução de dependência de processos manuais (Excel).

## 3. Requisitos de Negócio
- Melhorar a confiabilidade dos números corporativos.
- Reduzir retrabalho das áreas.
- Permitir integração futura com IA e automações.
- Entregar indicadores estáveis para todas as áreas da empresa.
- Criar visibilidade sobre Sell-in, Sell-out e performance de marcas.

## 4. Critérios de Sucesso
- Diminuição do uso de planilhas descentralizadas.
- Criação de pipeline estável no Fabric.
- BI único e governado para diversas áreas.
- Tempo de extração/análise reduzido.
- Adoção da plataforma pelas equipes internas.

## 5. Objetivo deste documento
Ser referência para toda decisão técnica futura.
