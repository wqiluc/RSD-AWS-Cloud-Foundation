<h1 align="center">🔒 Seção 5 – Proteção de dados na AWS</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Módulo_4-Segurança_na_Nuvem_AWS-111827?style=for-the-badge&labelColor=FF9900" alt="Módulo 4"/>
  <img src="https://img.shields.io/badge/Seção-5-111827?style=for-the-badge&labelColor=232F3E" alt="Seção 5"/>
  <br>
  <img src="https://img.shields.io/badge/-Dados_em_repouso_·_em_trânsito-111827?style=flat-square&logo=letsencrypt&logoColor=FF9900" alt="Dados em repouso · em trânsito"/>
  <img src="https://img.shields.io/badge/-TLS_·_HTTPS_·_KMS-111827?style=flat-square&logo=amazonwebservices&logoColor=FF9900" alt="TLS · HTTPS · KMS"/>
  <img src="https://img.shields.io/badge/-Buckets_S3-111827?style=flat-square&logo=amazons3&logoColor=FF9900" alt="Buckets S3"/>
</p>

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%204%20-%20Proteção%20de%20contas.md">⬅️ Anterior: Proteção de contas</a> &nbsp;•&nbsp;
  <a href="./Seção%206%20-%20Trabalhar%20para%20garantir%20a%20conformidade.md">Próxima: Conformidade ➡️</a>
</p>

![Módulo 4, Seção 5: Proteção de dados na AWS](../img/m4-secao5-capa.png)

## 📑 Sumário

| # | Tópico |
|:---:|---|
| 1 | [💾 Criptografia de dados em repouso](#repouso) |
| 2 | [🚚 Criptografia de dados em trânsito](#transito) |
| 3 | [🪣 Proteção de buckets e objetos do Amazon S3](#s3) |
| 🎯 | [Principais conclusões](#conclusoes) |

| | 💾 **Dados em repouso** | 🚚 **Dados em trânsito** |
|---|---|---|
| **O que são** | Dados **armazenados fisicamente** (disco ou fita) | Dados **em movimentação** por uma rede |
| **Como proteger** | Criptografia com chaves gerenciadas pelo **AWS KMS** | **TLS/SSL** e **HTTPS**, com certificados do **AWS Certificate Manager** |

---

<a id="repouso"></a>
## 1. 💾 Criptografia de dados *em repouso*

![Criptografia de dados em repouso](../img/m4-secao5-dados-em-repouso.png)

A **criptografia** codifica dados com uma **chave secreta**, o que os torna **ilegíveis**.

- 🔑 Somente **quem tem a chave secreta** pode decodificar os dados.
- 🗝️ O **AWS KMS** pode gerenciar suas chaves secretas (ver [Seção 4](./Seção%204%20-%20Proteção%20de%20contas.md#kms)).

A AWS oferece suporte à criptografia de **dados em repouso**, ou seja, dados **armazenados fisicamente** (em disco ou fita). Você pode criptografar dados armazenados em **qualquer serviço compatível com o AWS KMS**, incluindo:

| Serviço | Tipo de armazenamento |
|---|---|
| 🪣 **Amazon S3** | Objetos |
| 💽 **Amazon EBS** | Volumes de blocos (discos das instâncias EC2) |
| 📁 **Amazon Elastic File System (Amazon EFS)** | Sistema de arquivos |
| 🗄️ **Amazon RDS** | Bancos de dados gerenciados |

```mermaid
flowchart LR
    A["📄 Dados legíveis"] -->|"🔑 chave secreta (KMS)"| B["🔒 Dados criptografados<br/>ilegíveis"]
    B -->|"🔑 mesma chave"| A
    style B fill:#FF9900,color:#111827,stroke:#111827
```

<a id="transito"></a>
## 2. 🚚 Criptografia de dados *em trânsito*

![Criptografia de dados em trânsito](../img/m4-secao5-dados-em-transito.png)

Os **dados em trânsito** são os dados **em movimentação por uma rede**.

| Tecnologia | O que faz |
|---|---|
| 🔐 **Transport Layer Security (TLS)** | Antes chamado de **SSL**, é um **protocolo de padrão aberto** para criptografar a comunicação. |
| 📜 **AWS Certificate Manager** | Oferece uma maneira de **gerenciar, implantar e renovar** certificados **TLS ou SSL**. |
| 🌐 **HTTP seguro (HTTPS)** | Cria um **túnel seguro**, usando **TLS ou SSL** para a troca **bidirecional** de dados. |

Os **serviços da AWS oferecem suporte** à criptografia de dados em trânsito. Dois exemplos:

```mermaid
flowchart LR
    subgraph N1["☁️ Nuvem AWS"]
        EC2["🖥️ Amazon EC2"] <-->|"tráfego criptografado com TLS"| EFS["📁 Amazon EFS"]
    end
    subgraph DC["🏢 Datacenter corporativo"]
        SG["🔁 AWS Storage Gateway"]
    end
    subgraph N2["☁️ Nuvem AWS"]
        S3["🪣 Amazon S3"]
    end
    SG <-->|"TLS ou SSL criptografados"| S3
    style N1 fill:#2E5A88,color:#FFFFFF,stroke:#111827
    style N2 fill:#2E5A88,color:#FFFFFF,stroke:#111827
    style DC fill:#6B7280,color:#FFFFFF,stroke:#111827
```

1. ☁️ Uma instância **Amazon EC2** e o **Amazon EFS** trocam dados criptografados com **TLS**.
2. 🏢 O **AWS Storage Gateway**, no datacenter corporativo, envia dados ao **Amazon S3** usando **TLS ou SSL**.

<a id="s3"></a>
## 3. 🪣 Proteção de buckets e objetos do Amazon S3

![Proteção de buckets e objetos do Amazon S3](../img/m4-secao5-buckets-s3.png)

> [!NOTE]
> Os buckets e objetos do S3 **recém-criados** são **privados e protegidos por padrão**.

Quando os casos de uso exigem **compartilhar** objetos no Amazon S3:

- 🎛️ É essencial **gerenciar e controlar o acesso** aos dados.
- 🎯 Siga permissões que respeitem o **princípio do privilégio mínimo** e considere usar a **criptografia do Amazon S3**.

**Ferramentas e opções para controlar o acesso aos dados do S3:**

| Ferramenta | Observação |
|---|---|
| 🚫 **Amazon S3 Block Public Access** | **Simples de usar**; bloqueia o acesso público aos buckets. |
| 🔐 **Políticas do IAM** | Boa opção quando o usuário **pode se autenticar usando o IAM**. |
| 📄 **Políticas de buckets** | Definem o acesso **no próprio bucket**. |
| 📋 **Listas de controle de acesso (ACLs)** | Mecanismo de controle de acesso **herdado** (*legacy*). |
| ✅ **Verificação de permissão de bucket do AWS Trusted Advisor** | Recurso **gratuito**. |

> [!WARNING]
> A maior parte dos vazamentos de dados no S3 acontece por **buckets configurados como públicos por engano**, e não por falha da AWS. Pelo [modelo de responsabilidade compartilhada](./Seção%201%20-%20Modelo%20de%20responsabilidade%20compartilhada%20da%20AWS.md), essa configuração é **do cliente**.

---

<a id="conclusoes"></a>
## 🎯 Principais conclusões

- ✅ A **criptografia** torna os dados ilegíveis para quem não tem a **chave secreta**; o **AWS KMS** gerencia essas chaves.
- ✅ **Dados em repouso** (disco ou fita) podem ser criptografados em serviços compatíveis com o KMS: **S3**, **EBS**, **EFS** e **RDS**.
- ✅ **Dados em trânsito** são protegidos com **TLS** (antigo SSL) e **HTTPS**; o **AWS Certificate Manager** gerencia os certificados.
- ✅ Buckets e objetos do **S3** são **privados por padrão**.
- ✅ Para controlar o acesso ao S3, use **Block Public Access**, **políticas do IAM**, **políticas de bucket**, **ACLs** e a verificação gratuita do **Trusted Advisor**, sempre com **privilégio mínimo**.

---

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%204%20-%20Proteção%20de%20contas.md">⬅️ Anterior: Proteção de contas</a> &nbsp;•&nbsp;
  <a href="./Seção%206%20-%20Trabalhar%20para%20garantir%20a%20conformidade.md">Próxima: Conformidade ➡️</a>
</p>
