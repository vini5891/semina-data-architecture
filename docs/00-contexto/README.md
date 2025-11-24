# 00 - Contexto do Projeto

Este documento apresenta o contexto inicial do projeto de Arquitetura de Dados da Semina.

## Situação atual
A empresa opera com múltiplas fontes de dados (TOTVS/Protheus, planilhas, relatórios manuais e plataformas externas), sem uma arquitetura centralizada que ofereça qualidade, governança e escalabilidade.

Atualmente:
- a maior parte das análises depende de planilhas Excel;
- não há estrutura formal de Data Lake ou Data Warehouse;
- não existe um catálogo de dados;
- cada área trata dados de forma independente;
- não há automação para ingestão ou limpeza de dados.

## Necessidade
Diante do crescimento da empresa e da demanda por inteligência operacional e estratégica, torna-se essencial implementar uma arquitetura moderna, escalável e unificada (Data Lakehouse).

## Motivadores principais
- Centralizar dados dispersos.
- Padronizar regras de negócio.
- Criar governança e segurança de acesso.
- Reduzir trabalho manual.
- Aumentar confiabilidade dos indicadores.
- Preparar a empresa para automações, IA e análises avançadas.

## Objetivo deste documento
Descrever o cenário inicial que justifica o projeto e servir como base para as decisões arquiteturais futuras.
