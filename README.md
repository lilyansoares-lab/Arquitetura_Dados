### Arquitetura e Modelagem de Dados Ponta a Ponta: Ecossistema de Adquirência (Fintech)

### 📌 Sobre o Projeto

Este repositório apresenta o desenho de uma arquitetura de dados robusta e moderna para uma empresa adquirente (credenciadora de cartões de crédito). O objetivo principal é transformar dados brutos transacionais em informações analíticas auditáveis, escaláveis e de alta governança, respondendo a perguntas críticas de negócio sobre faturamento (TPV), antecipações de recebíveis e custos operacionais.

O projeto foi estruturado em três camadas de modelagem utilizando conceitos do **Modern Data Stack**:

1.  **Modelagem Transacional (OLTP):** Normalização em Terceira Forma Normal (3FN) para garantir integridade e consistência na origem.
2.  **Enterprise Data Warehouse (EDW):** Implementação da metodologia **Data Vault 2.0** (Hubs, Links e Satélites) para garantir rastreabilidade, histórico completo e auditoria.
3.  **Modelagem Dimensional (OLAP):** Camada de entrega (*Information Delivery*) em Esquema Estrela para consumo ágil por ferramentas de BI e dashboards.

* * *

### 🏗️ Arquitetura de Referência

O ecossistema foi projetado seguindo os padrões modernos de engenharia de dados, prevendo a ingestão de dados via arquivos, bancos de dados relacionais e eventos em tempo real (*Streams*).

* * *

### 🧩 1. Camada Transacional (3FN)

Projetada para suportar a operação e persistência correta das regras de negócio de adquirência.

### Regras de Negócio Implementadas:

*   **Taxa de Desconto (MDR):** Cobrança automática de 1% de taxa sobre o valor total de cada transação (seja crédito ou débito).
*   **Parcelamento Dinâmico:** Divisão do valor bruto entre as parcelas na tabela `Parcela_Transacao`. Transações parceladas acima de 3 vezes sofrem um acréscimo de 10% no valor total.
*   **Antecipação de Recebíveis (RAV):** Permissão de antecipação exclusiva para transações de crédito, aplicando desconto de 1% fixo + 1% cumulativo para cada mês antecipado (sensível a variações da taxa SELIC).
*   **Segurança e LGPD:** Mascaramento e tokenização de dados sensíveis de cartões, armazenando estritamente os 4 últimos dígitos do BIN.

### Modelo Entidade-Relacionamento (DER)

* * *

### 🔒 2. Camada Core EDW (Data Vault 2.0)

Para garantir a modularidade e evitar reengenharia diante de novos sistemas, a camada de armazenamento central utiliza o padrão Data Vault 2.0.

*   **Hubs (Chaves de Negócio):** Isolação das entidades principais como `H_Estabelecimento`, `H_Transacao`, `H_Maquininha` e `H_Cartao`.
*   **Links (Relacionamentos):** Associações n:n flexíveis e históricas, permitindo rastrear o ciclo completo da venda e mudanças fiscais (`L_Estabelecimento_Tipo_Fiscal`, `L_Transacao_Parcela`, etc.).
*   **Satélites (Contexto e Histórico):** Tabelas que armazenam os atributos e metadados de carga (`Load_Date` e `Record_Source`), viabilizando auditoria completa (*SCD Type 2* nativo).

* * *

### 📊 3. Camada Dimensional (Information Delivery)

Derivado do Business Vault, esta camada expõe tabelas analíticas em **Esquema Estrela (Star Schema)** otimizadas para consultas SQL de alta performance e dashboards corporativos.

### ❓ Perguntas Respondidas pelo Modelo:

1.  **Qual é o volume total transacionado (TPV) por dia, por estabelecimento e por categoria de negócio?**
    *   *Solução:* Cruzamento da tabela `Fato_Transacao` com as dimensões `Dim_Tempo`, `Dim_Estabelecimento` e `Dim_Categoria`.
2.  **Quanto os estabelecimentos estão gerando de receita de aluguel de maquininhas (POS)?**
    *   *Solução:* Métrica calculada baseada na regra de isenção por atingimento de TPV mínimo (isento se > R$ 100k/mês) ou cobrança fixa de R$ 100,00 combinando `Fato_Transacao` e `Dim_Maquina_Pagamento`.
3.  **Qual é o volume de antecipações (RAV) realizadas e a projection do lucro futuro da adquirente?**
    *   *Solução:* Métrica calculada pela diferença entre o valor líquido original e o valor antecipado com desconto (`SUM(Valor_Antecipado - Valor_Liquido)`).
