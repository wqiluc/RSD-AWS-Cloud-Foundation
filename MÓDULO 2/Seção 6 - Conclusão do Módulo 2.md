<h1 align="center">🏁 Seção 6 – Conclusão do Módulo 2</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Módulo_2-Economia_e_faturamento_da_nuvem-111827?style=for-the-badge&labelColor=FF9900" alt="Módulo 2"/>
  <img src="https://img.shields.io/badge/Seção-6_de_6-111827?style=for-the-badge&labelColor=232F3E" alt="Seção 6 de 6"/>
  <br>
  <img src="https://img.shields.io/badge/-Questão_de_exame-111827?style=flat-square&logo=instructure&logoColor=FF9900" alt="Questão de exame"/>
  <img src="https://img.shields.io/badge/-Cloud_Practitioner-111827?style=flat-square&logo=amazonwebservices&logoColor=FF9900" alt="Cloud Practitioner"/>
  <img src="https://img.shields.io/badge/Módulo_2-concluído-111827?style=flat-square&labelColor=2EA043" alt="Módulo 2 concluído"/>
</p>

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%205%20-%20Suporte%20Técnico.md">⬅️ Anterior: Suporte técnico</a> &nbsp;•&nbsp;
  <a href="./Seção%20Bônus%20-%20Atividade:%20Calculadora%20Mensal.md">Bônus: Calculadora Mensal ➡️</a>
</p>

![Módulo 2, Seção 6: Conclusão do módulo](../img/m2-secao6-capa.png)

## 📑 Sumário

| # | Tópico |
|:---:|---|
| 1 | [🗂️ Resumo do módulo](#resumo) |
| 2 | [📝 Exemplo de pergunta do exame](#pergunta) |
| 🎯 | [Principais conclusões](#conclusoes) |

---

<a id="resumo"></a>
## 1. 🗂️ Resumo do módulo

![Resumo do módulo](../img/m2-secao6-resumo-do-modulo.png)

Neste módulo, aprendemos a:

| Verbo | Objetivo | Onde estudar |
|---|---|---|
| 🧭 **Explorar** | Os **fundamentos da definição de preço** da AWS (computação, armazenamento e transferência de dados) | [💲 Seção 1](./Seção%201%20-%20Fundamentos%20da%20definição%20de%20preço.md) |
| 🔁 **Revisar** | Os conceitos de **custo total de propriedade (TCO)** | [🧾 Seção 2](./Seção%202%20-%20Custo%20total%20de%20propriedade.md) |
| 🧮 **Conhecer** | A **Calculadora Mensal da AWS** e a **Calculadora de TCO** | [🧾 Seção 2](./Seção%202%20-%20Custo%20total%20de%20propriedade.md) e [🧪 Atividade: Calculadora Mensal](./Seção%20Bônus%20-%20Atividade:%20Calculadora%20Mensal.md) |
| 📊 **Revisar** | O **painel de faturamento** e as ferramentas do AWS Billing and Cost Management | [💰 Seção 4](./Seção%204%20-%20AWS%20Billing%20and%20Cost%20Management.md) e [🎬 Demonstração: Painel de cobrança](./Seção%20Bônus2%20-%20Demonstração%20-%20Painel%20de%20cobrança.md) |
| 🛟 **Revisar** | As **opções e os custos do suporte técnico** | [🛟 Seção 5](./Seção%205%20-%20Suporte%20Técnico.md) |

```mermaid
flowchart LR
    S1["💲 Seção 1<br/>Como a AWS cobra"] --> S2["🧾 Seção 2<br/>Quanto custa no total"] --> S3["🏛️ Seção 3<br/>Organizar contas"] --> S4["💰 Seção 4<br/>Acompanhar a fatura"] --> S5["🛟 Seção 5<br/>Obter suporte"] --> S6["🏁 Seção 6<br/>Revisão"]
    style S6 fill:#FF9900,color:#111827,stroke:#111827
```

<a id="pergunta"></a>
## 2. 📝 Exemplo de pergunta do exame

![Exemplo de pergunta do exame](../img/m2-secao6-pergunta-exame.png)

> [!NOTE]
> **Qual serviço da AWS fornece recomendações de otimização de segurança de infraestrutura?**

| | Alternativa |
|:---:|---|
| **A** | Interface de programação de aplicativos (API) do AWS Price List |
| **B** | Instâncias reservadas |
| **C** | AWS Trusted Advisor |
| **D** | Frota spot do Amazon Elastic Compute Cloud (Amazon EC2) |

<details>
<summary>💡 <strong>Clique para ver a resposta</strong></summary>

<br>

![Resposta da pergunta do exame](../img/m2-secao6-pergunta-exame-resposta.png)

🔑 As palavras-chave da pergunta são **"recomendações de otimização de segurança de infraestrutura"**.

> [!TIP]
> ✅ **Resposta correta: C.** O **AWS Trusted Advisor** é um recurso *online* que verifica o ambiente e recomenda melhorias com base nas **melhores práticas da AWS**, ajudando a reduzir custos, aumentar o desempenho e **melhorar a segurança**.

Por que as outras estão erradas:

| Alternativa | Por que não é a resposta |
|:---:|---|
| ❌ **A** | A **API do AWS Price List** serve para **consultar preços** dos serviços, não para recomendar melhorias de segurança. |
| ❌ **B** | **Instâncias reservadas** são um **modelo de compra** com desconto em troca de compromisso de uso; tratam de custo, não de segurança. |
| ❌ **D** | A **frota spot do EC2** é uma forma de executar instâncias usando **capacidade ociosa** a preço reduzido; também é uma questão de custo. |

Isso retoma a [Seção 5](./Seção%205%20-%20Suporte%20Técnico.md), em que o **Trusted Advisor** aparece como o recurso de **melhores práticas** do AWS Support, cobrindo **custo**, **desempenho**, **segurança**, **tolerância a falhas** e **limites de serviço**.

</details>

---

<a id="conclusoes"></a>
## 🎯 Principais conclusões

- ✅ O preço da AWS se baseia em três fatores: **computação**, **armazenamento** e **transferência de dados** (saída), com **pagamento conforme o uso**.
- ✅ O **TCO** compara o custo total de manter a infraestrutura **local** versus **na nuvem**, considerando também custos indiretos.
- ✅ A **Calculadora Mensal da AWS** estima o custo dos serviços; a **Calculadora de TCO** compara o ambiente local com a AWS.
- ✅ O **painel de faturamento**, o **Cost Explorer**, o **AWS Budgets** e os **relatórios de uso e custo** ajudam a acompanhar e controlar os gastos.
- ✅ O **AWS Support** oferece quatro planos (**Básico**, **Desenvolvedor**, **Business** e **Enterprise**), e o **Trusted Advisor** recomenda melhorias, inclusive de **segurança**.

---

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%205%20-%20Suporte%20Técnico.md">⬅️ Anterior: Suporte técnico</a> &nbsp;•&nbsp;
  <a href="./Seção%20Bônus%20-%20Atividade:%20Calculadora%20Mensal.md">Bônus: Calculadora Mensal ➡️</a>
</p>
