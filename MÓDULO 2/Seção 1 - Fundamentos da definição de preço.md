<h1 align="center">💲 Seção 1 – Fundamentos da definição de preço</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Módulo_2-Economia_e_faturamento_da_nuvem-111827?style=for-the-badge&labelColor=FF9900" alt="Módulo 2"/>
  <img src="https://img.shields.io/badge/Seção-1_de_6-111827?style=for-the-badge&labelColor=232F3E" alt="Seção 1 de 6"/>
  <br>
  <img src="https://img.shields.io/badge/-Computação_·_Armazenamento_·_Dados-111827?style=flat-square&logo=instructure&logoColor=FF9900" alt="Computação · Armazenamento · Dados"/>
  <img src="https://img.shields.io/badge/-AURI_·_PURI_·_NURI-111827?style=flat-square&logo=cashapp&logoColor=FF9900" alt="AURI · PURI · NURI"/>
  <img src="https://img.shields.io/badge/-Free_Tier-111827?style=flat-square&logo=amazonwebservices&logoColor=FF9900" alt="Free Tier"/>
</p>

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="../MÓDULO%201/Seção%205%20-%20Conclusão%20do%20Módulo%201.md">⬅️ Módulo anterior: Conclusão do Módulo 1</a> &nbsp;•&nbsp;
  <a href="./Seção%202%20-%20Custo%20total%20de%20propriedade.md">Próxima: Custo total de propriedade ➡️</a>
</p>

![Módulo 2, Seção 1: Fundamentos da definição de preço](../img/m2-secao1-capa.png)

## 📑 Sumário

| # | Tópico |
|:---:|---|
| 1 | [🧮 Modelo de definição de preço da AWS](#modelo) |
| 2 | [💳 Como você paga pela AWS?](#como-paga) |
| 3 | [📊 Pague pelo que usar](#pague-uso) |
| 4 | [📅 Pague menos ao fazer reserva](#reserva) |
| 5 | [📦 Pague menos usando mais](#usando-mais) |
| 6 | [📈 Pague ainda menos com o crescimento da AWS](#crescimento) |
| 7 | [🤝 Definição de preço personalizada](#personalizado) |
| 8 | [🎁 Nível gratuito da AWS](#gratuito) |
| 9 | [🆓 Serviços sem custo](#sem-custo) |
| 🎯 | [Principais conclusões](#conclusoes) |

---

<a id="modelo"></a>
## 1. 🧮 Modelo de definição de preço da AWS

![Modelo de definição de preço da AWS](../img/m2-secao1-modelo-definicao-preco.png)

Na AWS, há **três fatores fundamentais de custo**:

| 🖥️ Computação | 💾 Armazenamento | 🔄 Transferência de dados |
|---|---|---|
| Cobrada **por hora ou por segundo** (por segundo somente para Linux) | Cobrado normalmente **por GB** | ⬆️ A **saída** (dados que saem da AWS) é agregada e cobrada |
| O preço **varia por tipo de instância** | | ⬇️ A **entrada** (dados que entram na AWS) **não tem cobrança**, com algumas exceções |
| | | Cobrada normalmente **por GB** |

```mermaid
flowchart LR
    U["🌍 Internet"] -- "⬇️ Entrada: sem cobrança" --> AWS["🟧 AWS"]
    AWS -- "⬆️ Saída: cobrada por GB" --> U
    style AWS fill:#FF9900,color:#111827,stroke:#111827
```

<a id="como-paga"></a>
## 2. 💳 Como você paga pela AWS?

![Como você paga pela AWS?](../img/m2-secao1-como-voce-paga.png)

Embora o número de serviços tenha crescido muito, a filosofia de preço da AWS continua apoiada em **três pilares**:

```mermaid
mindmap
  root((💳 Como você paga))
    📊 Pague pelo que usar
      Sem despesas iniciais
    📅 Pague menos ao reservar
      Instâncias Reservadas
    📦 Pague menos usando mais
      Descontos por volume
      Conforme a AWS cresce
```

<a id="pague-uso"></a>
## 3. 📊 Pague pelo que usar

![Pague pelo que usar](../img/m2-secao1-pague-pelo-que-usar.png)

Pague **apenas pelos serviços que consumir**, **sem grandes despesas iniciais**.

| 🏢 No local (on-premises) | ☁️ AWS |
|---|---|
| O custo sobe em **degraus**. A empresa compra capacidade antecipadamente e paga por ela mesmo quando não a usa (a área vermelha do gráfico é dinheiro gasto em capacidade ociosa). | O custo **acompanha a demanda**, subindo nos picos e caindo quando o uso diminui. |

> [!TIP]
> Isso retoma a vantagem de **trocar despesas de capital por despesas variáveis**, vista na [Seção 2 do Módulo 1](../MÓDULO%201/Seção%202%20-%20Vantagens%20da%20Computação%20em%20Nuvem.md).

<a id="reserva"></a>
## 4. 📅 Pague menos ao fazer reserva

Para serviços como o **Amazon EC2** e o **Amazon RDS**, é possível **reservar capacidade** (por exemplo, com **Instâncias Reservadas**) em troca de um **desconto** em relação ao preço sob demanda. Quanto maior o pagamento antecipado, maior o desconto:

| Sigla | Significado | Pagamento adiantado | Desconto |
|:---:|---|---|---|
| **AURI** | All Upfront Reserved Instance | 💰💰💰 **Total** | 🟩🟩🟩 **Maior** |
| **PURI** | Partial Upfront Reserved Instance | 💰💰 **Parcial** | 🟩🟩⬜ **Intermediário** |
| **NURI** | No Upfront Reserved Instance | ➖ **Nenhum** | 🟩⬜⬜ **Menor** |

<a id="usando-mais"></a>
## 5. 📦 Pague menos usando mais

![Pague menos usando mais](../img/m2-secao1-pague-menos-usando-mais.png)

A AWS oferece **descontos baseados em volume**:

- 📉 As **economias aumentam à medida que o uso aumenta**.
- 🪜 Serviços como **Amazon S3**, **Amazon EBS** e **Amazon EFS** têm **definição de preço em camadas**: quanto mais você usa, **menos paga por GB**.
- 💾 Vários serviços de armazenamento oferecem **custos mais baixos** de acordo com as necessidades de cada carga de trabalho.

<a id="crescimento"></a>
## 6. 📈 Pague ainda menos com o crescimento da AWS

![Pague ainda menos com o crescimento da AWS](../img/m2-secao1-crescimento-aws.png)

À medida que a AWS cresce:

| | O que acontece |
|:---:|---|
| 🎯 | A AWS se concentra em **reduzir o custo de fazer negócios**. |
| 🔁 | Com isso, ela **repassa as economias de escala** para os clientes. |
| 📉 | Desde 2006, a AWS **baixou seus preços 75 vezes** (dado de setembro de 2019). |
| 🚀 | **Recursos futuros com maior desempenho** substituem os atuais **sem custo adicional**. |

<a id="personalizado"></a>
## 7. 🤝 Definição de preço personalizada

![Definição de preço personalizada](../img/m2-secao1-preco-personalizado.png)

Cada cliente tem necessidades diferentes, por isso a AWS oferece **definição de preço personalizada**:

- 🎯 Atende **necessidades variáveis** com preços sob medida.
- 🏭 Disponível para **projetos de alto volume** com **requisitos exclusivos**.

<a id="gratuito"></a>
## 8. 🎁 Nível gratuito da AWS

![Nível gratuito da AWS](../img/m2-secao1-nivel-gratuito.png)

O **nível gratuito da AWS** (AWS Free Tier) permite obter **experiência prática gratuita** com produtos e serviços da AWS. Ele é **gratuito por 1 ano para novos clientes**. Um exemplo é poder executar uma **microinstância T2** do Amazon EC2 sem custo dentro dos limites do nível gratuito.

Para começar:

```mermaid
flowchart LR
    A["1️⃣ Cadastre-se<br/>para obter uma conta"] --> B["2️⃣ Aprenda<br/>com tutoriais de 10 min"] --> C["3️⃣ Comece a desenvolver<br/>com a AWS"]
```

<a id="sem-custo"></a>
## 9. 🆓 Serviços sem custo

![Serviços sem custo](../img/m2-secao1-servicos-sem-custo.png)

Alguns serviços da AWS **não têm custo próprio**:

| Serviço | Sem custo próprio |
|---|:---:|
| 🌐 **Amazon VPC** | ✅ |
| 🌱 **AWS Elastic Beanstalk\*** | ✅ |
| 📈 **Auto Scaling\*** | ✅ |
| 📜 **AWS CloudFormation\*** | ✅ |
| 🔑 **AWS Identity and Access Management (IAM)** | ✅ |

> [!WARNING]
> \* Pode haver cobranças pelos **outros serviços da AWS** usados junto com esses serviços. Por exemplo, o Elastic Beanstalk é gratuito, mas as instâncias do EC2 que ele cria são cobradas normalmente.

---

<a id="conclusoes"></a>
## 🎯 Principais conclusões

- ✅ Os **três fatores fundamentais de custo** da AWS são **computação**, **armazenamento** e **transferência de dados de saída**.
- ✅ A transferência de dados de **entrada** normalmente **não é cobrada**.
- ✅ **Pague pelo que usar**, sem grandes despesas iniciais.
- ✅ **Pague menos ao reservar** capacidade (AURI > PURI > NURI em desconto).
- ✅ **Pague menos usando mais**, com descontos por volume e preços em camadas.
- ✅ **Pague ainda menos conforme a AWS cresce**, já que ela repassa as economias de escala.
- ✅ Há **preço personalizado** para projetos de alto volume, um **nível gratuito** de 1 ano para novos clientes e **serviços sem custo** próprio, como VPC e IAM.

---

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="../MÓDULO%201/Seção%205%20-%20Conclusão%20do%20Módulo%201.md">⬅️ Módulo anterior: Conclusão do Módulo 1</a> &nbsp;•&nbsp;
  <a href="./Seção%202%20-%20Custo%20total%20de%20propriedade.md">Próxima: Custo total de propriedade ➡️</a>
</p>
