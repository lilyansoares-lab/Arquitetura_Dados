🛠️ SUMÁRIO PROJETOS

🏥 1. [SEGURADORA] Arquitetura Plaforma de Dados: Score de Risco e Detecção de Fraudes: Databricks x Snowflake
Tipo de Projeto: Seguradora Digital de Alta Escala

Arquitera: Big Data Architecture, MLOps, Visão Computacional e Ingestão em Streaming.

Resumo: Planejamento estratégico e comparativo entre duas das maiores plataformas de dados do mercado (Databricks e Snowflake) aplicadas ao setor de seguros. O projeto aborda a ingestão em fluxo contínuo de dados estruturados (apólices), semiestruturados (telemetria IoT de veículos) e não estruturados (fotos de vistorias de sinistros e vídeos de acidentes) para alimentar modelos preditivos de Score de Risco e Detecção de Fraudes em tempo real, atendendo rigorosamente à LGPD.

🔗 Detalhes do Projeto: Acesse o PDF do Comparativo Databricks x Snowflake

🏥 2. [SEGURADORA] Arquitetuta Data Lakehouse - Databrics: Análise Preventiva de Sinistros e Telemetria
Tipo de Projeto: Seguradora / Modern Data Stack

Arquitetura: Data Lakehouse, AWS Serverless (S3, Kinesis, Glue), Delta Lake, Databrics Analytics unificado.

Resumo: Desenvolvimento de uma solução moderna de Data Lakehouse agnóstica a provedor, mas implementada com serviços gerenciados nativos da AWS em conjunto com o Databricks. Focado nas necessidades de personalização analítica (Score de Risco individual por perfil de direção via telemetria) e redução de fraudes em sinistros climáticos. Demonstra o uso de Amazon Kinesis para ingestão em tempo real e S3 com formato aberto Delta Lake para garantir transações ACID, versionamento e alta performance analítica sobre imagens e tabelas SQL.

🔗 Detalhes do Projeto: Acesse o PDF da Arquitetura AWS Lakehouse

🏥 3. [SEGURADORA] Arquitetura Cloud Híbrida: Governança e FinOps para Core de Apólices
Tipo de Projeto: Seguradora / Infraestrutura Corporativa

Foco Técnico: Governança Multi-Cloud, Interoperabilidade, FinOps (OpEx/CapEx) e Integração Híbrida.

Resumo: Planejamento e distribuição de um ecossistema de dados distribuído estrategicamente entre os principais provedores de nuvem (AWS, GCP, Azure) e ambiente On-Premises. A arquitetura mantém os sistemas transacionais legados (core de apólices e faturamento) operando localmente por compliance; utiliza a AWS como repositório central de armazenamento (Data Lake nas camadas Bronze, Silver e Gold); centraliza o processamento analítico e Machine Learning via Databricks na GCP; e delega a camada de consumo (BI com Power BI) e segurança de identidades para a Azure.

🔗 Detalhes do Projeto: Acesse o PDF da Estratégia Multi-Cloud

💳 4. [FINTECH] Arquiteura e Modelagem de Dados de Adquirência: Conciliação, MDR e Parcelamentos
Tipo de Projeto: Fintech

Arquitera: Modelagem Relacional (3FN), Data Vault 2.0, Star Schema e Business Intelligence.

Resumo: Desenho de uma infraestrutura analítica completa para uma empresa credenciadora de cartões de crédito[cite: 1]. Soluciona o desafio de transformar dados transacionais brutos em informações auditáveis, tratando regras de negócio complexas como taxas de desconto (MDR)[cite: 4], parcelamentos dinâmicos e antecipações de recebíveis (RAV) influenciadas pela taxa SELIC. O ecossistema garante rastreabilidade total sem necessidade de reengenharia diante de novos sistemas.

🔗 Detalhes do Projeto: Acesse o PDF do Projeto de Modelagem Fintech
