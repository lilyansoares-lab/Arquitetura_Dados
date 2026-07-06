# 🛠️ SUMÁRIO PROJETOS

---

## 🏥 1. [SEGURADORA] Arquitetura Plataforma de Dados: [Score] de Risco e Detecção de Fraudes
**Databricks x Snowflake**

- **Tipo de Projeto:** Seguradora Digital de Alta Escala  
- **Arquitetura:** Big Data, MLOps, Visão Computacional e Ingestão em Streaming.

**Resumo:** Planejamento estratégico e comparativo entre duas das maiores plataformas de dados do mercado (Databricks e Snowflake) aplicadas ao setor de seguros. O projeto aborda a administração em fluxo contínuo de dados estruturados (apólices), semiestruturados (telemetria IoT de veículos) e não estruturados (fotos de vistorias de sinistros e vídeos de acidentes) para modelos preditivos de Score de Risco e Detecção de Fraudes em tempo real, atendendo rigorosamente à LGPD.

🔗 **Detalhes do Projeto:** [Acesse o PDF do Comparativo Databricks x Snowflake](./docs/comparativo_databricks_snowflake.pdf)

---

## 🏥 2. [SEGURADORA] Arquitetura Data Lakehouse e Databricks: Análise Preventiva de Sinistros e Telemetria

- **Tipo de Projeto:** Seguradora / Modern Data Stack  
- **Arquitetura:** Data Lakehouse, AWS Serverless (S3, Kinesis, Glue), Delta Lake e Databricks Analytics unificado.

**Resumo:** Desenvolvimento de uma solução moderna de Data Lakehouse agnóstica a provedor, mas inovadora com serviços gerenciados nativos da AWS em conjunto com o Databricks. Focado nas necessidades de personalização analítica (Pontuação de Risco individual por perfil de direção via telemetria) e redução de fraudes em sinistros climáticos. Demonstra o uso do Amazon Kinesis para consumo em tempo real e S3 com formato aberto Delta Lake para garantir transações ACID, versionamento e alta performance analítica sobre imagens e tabelas SQL.

🔗 **Detalhes do Projeto:** [Acesse o PDF da Arquitetura AWS Lakehouse](./docs/arquitetura_aws_lakehouse.pdf)

---

## 🏥 3. [SEGURADORA] Arquitetura Cloud Híbrida: Governança e FinOps para Núcleo de Apólices

- **Tipo de Projeto:** Seguradora / Infraestrutura Corporativa  
- **Arquitetura:** Governança Multi-Cloud, Interoperabilidade, FinOps (OpEx/CapEx) e Integração Híbrida.

**Resumo:** Planejamento e distribuição de um ecossistema de dados distribuído estrategicamente entre os principais provedores de nuvem (AWS, GCP, Azure) e ambiente On-Premises. A arquitetura mantém os sistemas transacionais legados (núcleo de apólices e faturamento) operando localmente por compliance; utiliza a AWS como repositório central de armazenamento (Data Lake nas camadas Bronze, Silver e Gold); centralização do processamento analítico e Machine Learning via Databricks na GCP; e delega a camada de consumo (BI com Power BI) e segurança de identidades para o Azure.

🔗 **Detalhes do Projeto:** [Acesse o PDF da Estratégia Multi-Cloud](./docs/estrategia_multicloud.pdf)

---

## 💳 4. [FINTECH] Arquitetura e Modelagem de Dados de Adquirência: Conciliação, MDR e Parcelamentos

- **Tipo de Projeto:** Fintech  
- **Arquitetura:** Modelagem Relacional (3FN), Data Vault 2.0, Star Schema e Business Intelligence.

**Resumo:** Desenho de uma infraestrutura analítica completa para uma empresa credenciadora de cartões de crédito. Soluciona o desafio de transformar dados transacionais brutos em informações auditáveis, tratando regras de negócio complexas como taxas de desconto (MDR), parcelamentos dinâmicos e antecipações de recebíveis (RAV) influenciadas pela taxa SELIC. O ecossistema garante rastreabilidade total sem necessidade de reengenharia diante de novos sistemas.

🔗 **Detalhes do Projeto:** [Acesse o PDF do Projeto de Modelagem Fintech](./docs/projeto_modelagem_fintech.pdf)
