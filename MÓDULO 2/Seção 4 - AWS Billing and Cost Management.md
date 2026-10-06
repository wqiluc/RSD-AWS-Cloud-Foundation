<h1 align="center">💰 Seção 4 – AWS Billing and Cost Management</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Módulo_2-Economia_e_faturamento_da_nuvem-111827?style=for-the-badge&labelColor=FF9900" alt="Módulo 2"/>
  <img src="https://img.shields.io/badge/Seção-4_de_6-111827?style=for-the-badge&labelColor=232F3E" alt="Seção 4 de 6"/>
  <br>
  <img src="https://img.shields.io/badge/-Cost_Explorer_·_Budgets-111827?style=flat-square&logo=instructure&logoColor=FF9900" alt="Cost Explorer · Budgets"/>
  <img src="https://img.shields.io/badge/-Cost_and_Usage_Report-111827?style=flat-square&logo=googlesheets&logoColor=FF9900" alt="Cost and Usage Report"/>
</p>

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%203%20-%20AWS%20Organizations.md">⬅️ Anterior: AWS Organizations</a> &nbsp;•&nbsp;
  <a href="./Seção%205%20-%20Suporte%20Técnico.md">Próxima: Suporte técnico ➡️</a>
</p>

![Módulo 2, Seção 4: AWS Billing and Cost Management](../img/m2-secao4-capa.png)

## 📑 Sumário

| # | Tópico |
|:---:|---|
| 1 | [📊 Painel de faturamento da AWS](#painel) |
| 2 | [🧰 Ferramentas](#ferramentas) |
| 3 | [🧾 Faturas mensais](#faturas) |
| 4 | [📈 Cost Explorer](#cost-explorer) |
| 5 | [🎯 Preveja e rastreie custos](#budgets) |
| 6 | [📋 Relatórios de uso e de custo](#relatorios) |
| 🎯 | [Principais conclusões](#conclusoes) |

> [!TIP]
> Quer ver tudo isso no console? Confira a [🎬 Demonstração: Painel de cobrança](./Seção%20Bônus2%20-%20Demonstração%20-%20Painel%20de%20cobrança.md).

---

<a id="painel"></a>
## 1. 📊 Painel de faturamento da AWS

![Painel de faturamento da AWS](../img/m2-secao4-painel-faturamento.png)

O **AWS Billing and Cost Management** é o serviço usado para **pagar a fatura da AWS**, **monitorar o uso** e **analisar e controlar os custos**. Sua página inicial é o **painel de faturamento** (*Billing & Cost Management Dashboard*), que reúne:

| Elemento | O que mostra |
|---|---|
| 💵 **Resumo de gastos** (*Spend Summary*) | Compara o custo do **mês passado**, o custo **acumulado no mês atual** (*month-to-date*) e a **previsão** de gasto até o fim do mês (*forecast*). |
| 🥧 **Gastos do mês por serviço** (*Month-to-Date Spend by Service*) | Gráfico com a proporção do custo de cada serviço usado (no exemplo, **EC2**, **RDS**, **ElastiCache**, **DynamoDB** e outros). |
| 🔗 **Atalhos** | Para o **Cost Explorer** e para os **detalhes da fatura** (*Bill Details*). |

<a id="ferramentas"></a>
## 2. 🧰 Ferramentas

![Ferramentas](../img/m2-secao4-ferramentas.png)

Além do painel, o serviço oferece ferramentas para **estimar, planejar e acompanhar** os custos da AWS:

```mermaid
flowchart TD
    B["💰 AWS Billing and Cost Management"] --> D["📊 Painel de faturamento"]
    B --> BU["🎯 AWS Budgets<br/>orçamentos e alertas"]
    B --> CUR["📋 Cost and Usage Report<br/>dados mais detalhados"]
    B --> CE["📈 Cost Explorer<br/>visualização e análise"]
    style B fill:#FF9900,color:#111827,stroke:#111827
```

| Ferramenta | Para que serve |
|---|---|
| 🎯 **Orçamentos da AWS (AWS Budgets)** | Definir orçamentos personalizados e receber **alertas** quando os custos ou o uso ultrapassarem (ou houver previsão de ultrapassar) o valor definido. |
| 📋 **Relatórios de custos e uso da AWS (AWS Cost and Usage Report)** | Gerar o conjunto **mais detalhado** de dados de custo e uso disponível. |
| 📈 **AWS Cost Explorer** | **Visualizar e analisar** custos e uso ao longo do tempo, com gráficos e filtros. |

O console é organizado nas abas **Bills**, **Cost Explorer**, **Budgets** e **Reports**, detalhadas a seguir.

<a id="faturas"></a>
## 3. 🧾 Faturas mensais

![Faturas mensais](../img/m2-secao4-faturas-mensais.png)

A página **AWS Bills** lista os custos gerados no **último mês** e no mês atual, detalhados por **serviço** e por **região**.

- 🗂️ Os valores aparecem agrupados por tipo de cobrança, por exemplo **AWS Marketplace Charges** e **AWS Service Charges**.
- 🧾 Cada grupo mostra as **cobranças de uso e taxas recorrentes** (*Usage Charges and Recurring Fees*), com o número da **fatura** (*invoice*), a data e o valor.
- 🔍 É o lugar para conferir **quanto foi cobrado** e **de onde veio** cada cobrança.

<a id="cost-explorer"></a>
## 4. 📈 Cost Explorer

![Cost Explorer](../img/m2-secao4-cost-explorer.png)

O **AWS Cost Explorer** mostra os custos em **gráficos**, permitindo visualizar, entender e gerenciar os gastos ao longo do tempo.

| | Recurso |
|:---:|---|
| 📅 | Relatório padrão de **custos mensais por serviço** (*Monthly costs by service*) dos **últimos meses**. |
| 🔎 | Dados **filtrados e agrupados** (por serviço, por período, mensal ou diário, etc.). |
| 📊 | Identifica **tendências** e **quais serviços mais pesam** na conta (no exemplo, **instâncias EC2** são a maior parte do custo). |
| 🔮 | Faz **previsões** do gasto futuro com base no histórico. |

<a id="budgets"></a>
## 5. 🎯 Preveja e rastreie custos

![Preveja e rastreie custos](../img/m2-secao4-orcamentos.png)

O **AWS Budgets** permite criar **orçamentos personalizados** e acompanhar o gasto real em relação a eles.

- 💵 O orçamento pode ser de **custo** (em dólares) ou de **uso** (por exemplo, número de **requisições** a um bucket do **S3**).
- ⚖️ Para cada orçamento, a tabela compara o valor **atual** (*Current*), o **previsto** (*Forecasted*) e o **orçado** (*Budgeted*).
- 📆 Os orçamentos podem ser acompanhados em nível **mensal**, **trimestral** ou **anual**, com datas de início e fim personalizáveis.

```mermaid
flowchart LR
    G["💸 Custo ou uso<br/>real ou previsto"] --> L{"Ultrapassou<br/>o limite?"}
    L -- "Sim" --> A["🔔 Alerta por e-mail<br/>ou Amazon SNS"]
    L -- "Não" --> OK["✅ Dentro do orçamento"]
```

<a id="relatorios"></a>
## 6. 📋 Relatórios de uso e de custo

![Relatórios de uso e de custo](../img/m2-secao4-relatorios-uso-custo.png)

O **AWS Cost and Usage Report** é a fonte de dados de faturamento **mais completa** da AWS.

- 🧩 Lista o uso de **cada categoria de serviço** usada pela conta (e pelos usuários do IAM), em itens de linha **por hora ou por dia**.
- 🏷️ Cada linha traz informações como **código do produto**, **tipo de uso**, **operação**, **zona de disponibilidade**, **quantidade usada**, **moeda** e **descrição** do item.
- 🪣 Os relatórios podem ser entregues em um **bucket do Amazon S3** e analisados em ferramentas externas ou em planilhas.

---

<a id="conclusoes"></a>
## 🎯 Principais conclusões

- ✅ O **AWS Billing and Cost Management** serve para **pagar a fatura**, **monitorar o uso** e **controlar os custos** da AWS.
- ✅ O **painel de faturamento** resume o gasto do mês passado, do mês atual e a previsão, além do custo por serviço.
- ✅ As principais ferramentas são **AWS Budgets** (orçamentos e alertas), **AWS Cost and Usage Report** (dados detalhados) e **AWS Cost Explorer** (visualização e análise).
- ✅ A página **Bills** detalha as **faturas mensais** por serviço e região.
- ✅ O **Budgets** compara gasto **atual**, **previsto** e **orçado** e envia **alertas** quando o limite é ultrapassado.
- ✅ O **Cost and Usage Report** lista o uso item a item, sendo o relatório **mais granular** disponível.

---

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%203%20-%20AWS%20Organizations.md">⬅️ Anterior: AWS Organizations</a> &nbsp;•&nbsp;
  <a href="./Seção%205%20-%20Suporte%20Técnico.md">Próxima: Suporte técnico ➡️</a>
</p>
