<h1 align="center">⚡ Seção 7 – Introdução ao AWS Lambda</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Módulo_6-Computação-111827?style=for-the-badge&labelColor=FF9900" alt="Módulo 6"/>
  <img src="https://img.shields.io/badge/Seção-7_·_AWS_Lambda-111827?style=for-the-badge&labelColor=232F3E" alt="Seção 7 · AWS Lambda"/>
  <br>
  <img src="https://img.shields.io/badge/-Sem_servidor_·_Função_Lambda-111827?style=flat-square&logo=amazonwebservices&logoColor=FF9900" alt="Sem servidor · Função Lambda"/>
  <img src="https://img.shields.io/badge/-Fontes_de_eventos_·_Configuração-111827?style=flat-square&logo=instructure&logoColor=FF9900" alt="Fontes de eventos · Configuração"/>
  <img src="https://img.shields.io/badge/-Programação_·_Limites-111827?style=flat-square&logo=instructure&logoColor=FF9900" alt="Programação · Limites"/>
</p>

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%206%20-%20Serviços%20de%20contêiner.md">⬅️ Anterior: Serviços de contêiner</a> &nbsp;•&nbsp;
  <a href="./Seção%208%20-%20Introdução%20ao%20AWS%20Elastic%20Beanstalk.md">Próxima: Introdução ao AWS Elastic Beanstalk ➡️</a>
</p>

![Módulo 6, Seção 7: Introdução ao AWS Lambda](../img/m6-secao7-capa.png)

> [!NOTE]
> Esta seção detalha o **AWS Lambda**, apresentado na [Seção 1](./Seção%201%20-%20Visão%20geral%20dos%20serviços%20de%20computação.MD#servicos) como a opção **sem servidor** entre os serviços de computação.

## 📑 Sumário

| # | Tópico |
|:---:|---|
| 1 | [⚡ AWS Lambda: execute código sem servidores](#lambda) |
| 2 | [🎁 Benefícios do Lambda](#beneficios) |
| 3 | [🔔 Fontes de eventos do AWS Lambda](#fontes) |
| 4 | [⚙️ Configuração da função do AWS Lambda](#configuracao) |
| 5 | [⏰ Exemplo de função Lambda baseada em programação](#programacao) |
| 6 | [📏 Limites do AWS Lambda](#limites) |
| 🎯 | [Principais conclusões](#conclusoes) |

---

<a id="lambda"></a>
## 1. ⚡ AWS Lambda: execute código sem servidores

![AWS Lambda: execute código sem servidores](../img/m6-secao7-execute-codigo.png)

O **AWS Lambda** é um **serviço de computação sem servidor**.

```mermaid
flowchart LR
    UP["💻 Faça upload<br/>do seu código"] --> FN["⚡ Função Lambda"]
    GAT["🔔 Serviços da AWS · Aplicativos móveis<br/>Endpoints HTTP"] -->|"Programação ou eventos"| FN
    FN --> RUN["▶️ Código executado<br/>somente quando é acionado"]
    RUN --> PAY["💲 Pague somente pelo<br/>tempo de computação usado"]
    style FN fill:#FF9900,color:#111827,stroke:#111827
```

- 📤 Você **faz upload do seu código**. O código que você executa é uma **função Lambda**.
- ⏰ O código é executado em uma **programação** ou **em resposta a eventos** de **serviços da AWS**, **aplicativos móveis** e **endpoints HTTP**.
- ▶️ Seu código é executado **somente quando é acionado**.
- 💲 Você **paga somente pelo tempo de computação** que usar.

<a id="beneficios"></a>
## 2. 🎁 Benefícios do Lambda

![Benefícios do Lambda](../img/m6-secao7-beneficios.png)

- 💻 **Oferece suporte a várias linguagens de programação.**
- ⚙️ **Administração totalmente automatizada:** o Lambda gerencia toda a infraestrutura para executar seu código.
- 🛡️ **Tolerância a falhas integrada.**
- 🎼 **Oferece suporte à orquestração de várias funções**, por exemplo com o AWS Step Functions.
- 💰 **Definição de preço com pagamento por uso** (*pay-per-use*).

> [!NOTE]
> Hoje o Lambda cobra pelas **solicitações** e pela **duração**, medida em incrementos de **1 ms**. O nível gratuito inclui **1 milhão de solicitações** e **400.000 GB-segundos** por mês.

<a id="fontes"></a>
## 3. 🔔 Fontes de eventos do AWS Lambda

![Fontes de eventos do AWS Lambda](../img/m6-secao7-fontes-eventos.png)

Configure **outros serviços da AWS como fontes de eventos** para invocar sua função:

```mermaid
flowchart LR
    F["🔔 Fontes de eventos<br/>Amazon S3 · Amazon DynamoDB<br/>Amazon SNS · Amazon SQS<br/>Amazon API Gateway<br/>Application Load Balancer<br/>Muitos mais"] --> FN["⚡ Função Lambda"]
    FN --> L["AWS Lambda"]
    L --> RUN["▶️ Execução do código<br/>(somente quando acionado)"]
    L --> CW["📊 Amazon CloudWatch<br/>Registro, monitoramento e métricas"]
    style L fill:#FF9900,color:#111827,stroke:#111827
```

Como alternativa, invoque a função no **console do Lambda**, no **SDK da AWS** ou na **CLI da AWS**.

<a id="configuracao"></a>
## 4. ⚙️ Configuração da função do AWS Lambda

![Configuração da função do AWS Lambda](../img/m6-secao7-configuracao-funcao.png)

| Item | O que é |
|---|---|
| 💻 **Código da função** | O código que será executado. |
| 📚 **Dependências** | Bibliotecas de código e outros itens de que o código precisa. |
| 🎩 **Função de execução** | A [**função do IAM**](./Seção%203%20-%20Amazon%20EC2%20Parte%202.md#iam) que dá à função do Lambda permissão para acessar outros serviços e recursos da AWS. |

Segundo a narração, também é preciso especificar o **ambiente** em que o código é executado, como **Python** ou **Node.js**.

Depois de configurada, a função segue o [mesmo fluxo](#fontes): o código é executado **somente quando é acionado**, com registro, monitoramento e métricas no [**Amazon CloudWatch**](./Seção%204%20-%20Amazon%20EC2%20Parte%203.md#cloudwatch).

> [!IMPORTANT]
> Em português, **função** tem dois sentidos nesta seção. A **função do Lambda** (*function*) é o código. A **função do IAM** ou **função de execução** (*role*) é o conjunto de permissões que esse código usa.

<a id="programacao"></a>
## 5. ⏰ Exemplo de função Lambda baseada em programação

![Exemplo de função Lambda baseada em programação: iniciar e interromper instâncias do EC2](../img/m6-secao7-exemplo-programacao.png)

Duas funções do Lambda, acionadas por **eventos do CloudWatch baseados em tempo**, **interrompem** e **iniciam** instâncias do EC2. Cada uma usa uma **função do IAM** com as permissões necessárias:

```mermaid
flowchart LR
    subgraph PARAR["Exemplo de interrupção de instâncias"]
        direction LR
        P1["1️⃣ Evento do CloudWatch<br/>baseado em tempo"] --> P2["2️⃣ Função do Lambda<br/>acionada"] --> P3["3️⃣ Instâncias do EC2<br/>interrompidas"]
    end
    subgraph INICIAR["Exemplo de iniciar instâncias"]
        direction LR
        I1["4️⃣ Evento do CloudWatch<br/>baseado em tempo"] --> I2["5️⃣ Função do Lambda<br/>acionada"] --> I3["6️⃣ Instâncias do EC2<br/>iniciadas"]
    end
    style P3 fill:#B3261E,color:#FFFFFF,stroke:#111827
    style I3 fill:#1F7A4D,color:#FFFFFF,stroke:#111827
```

Segundo a narração, as instâncias podem ser interrompidas em um **horário predefinido**, como à noite, quando ninguém as estiver usando. É uma forma de aplicar o [Pilar 2 da otimização de custos](./Seção%205%20-%20Otimização%20de%20custos%20do%20Amazon%20EC2.md#pilar2).

> [!NOTE]
> O CloudWatch Events hoje faz parte do **Amazon EventBridge**, e as regras baseadas em tempo são regras do EventBridge. Para agendamentos como este, há também o **EventBridge Scheduler**.

<a id="limites"></a>
## 6. 📏 Limites do AWS Lambda

![Limites do AWS Lambda](../img/m6-secao7-limites.png)

Limites **flexíveis** podem ser aumentados, e limites **rígidos**, não.

| Tipo | Limite | No slide (2019) | Hoje |
|---|---|---|---|
| 🟡 **Flexível, por Região** | Execuções simultâneas | 1.000 | 1.000 por padrão, podendo chegar a dezenas de milhares |
| 🟡 **Flexível, por Região** | Função e armazenamento de camadas | 75 GB | ⚠️ **300 GB** descompactados, sem possibilidade de aumento |
| 🔴 **Rígido, por função** | Alocação máxima de memória da função | 3.008 MB | ⚠️ **10.240 MB** |
| 🔴 **Rígido, por função** | Tempo limite da função | 15 minutos | 15 minutos |
| 🔴 **Rígido, por função** | Tamanho do pacote de implantação | 250 MB descompactados, incluindo camadas | 250 MB descompactados, incluindo camadas |

Também existem limites adicionais, descritos na documentação de [limites do AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/gettingstarted-limits.html).

> [!NOTE]
> Contas novas da AWS começam com cotas reduzidas de simultaneidade e de memória, que a AWS aumenta automaticamente conforme o uso. Funções empacotadas como **imagem de contêiner** têm limite próprio, de **10 GB**.

---

<a id="conclusoes"></a>
## 🎯 Principais conclusões

- ✅ O **AWS Lambda** é um serviço de computação **sem servidor**: você faz upload do código, e ele é executado **somente quando é acionado**.
- ✅ O código que você executa é uma **função Lambda**, acionada em uma **programação** ou **em resposta a eventos**.
- ✅ Você **paga somente pelo tempo de computação** que usar.
- ✅ Os benefícios são **várias linguagens**, **administração totalmente automatizada**, **tolerância a falhas integrada**, **orquestração de várias funções** e **pagamento por uso**.
- ✅ As **fontes de eventos** incluem S3, DynamoDB, SNS, SQS, API Gateway e Application Load Balancer. A função também pode ser invocada pelo **console**, pelo **SDK** ou pela **CLI**.
- ✅ Uma função é configurada com **código**, **dependências** e **função de execução**, que é uma função do IAM.
- ✅ Uma função **baseada em programação** pode **iniciar e interromper instâncias do EC2** para reduzir custos.
- ✅ O **tempo limite** é de **15 minutos**, e a memória máxima, de 3.008 MB no slide, hoje é de **10.240 MB**.

---

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%206%20-%20Serviços%20de%20contêiner.md">⬅️ Anterior: Serviços de contêiner</a> &nbsp;•&nbsp;
  <a href="./Seção%208%20-%20Introdução%20ao%20AWS%20Elastic%20Beanstalk.md">Próxima: Introdução ao AWS Elastic Beanstalk ➡️</a>
</p>
