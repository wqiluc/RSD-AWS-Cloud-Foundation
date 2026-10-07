<h1 align="center">🏢 Seção 4 – Proteção de contas</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Módulo_4-Segurança_na_Nuvem_AWS-111827?style=for-the-badge&labelColor=FF9900" alt="Módulo 4"/>
  <img src="https://img.shields.io/badge/Seção-4-111827?style=for-the-badge&labelColor=232F3E" alt="Seção 4"/>
  <br>
  <img src="https://img.shields.io/badge/-Organizations_·_SCPs-111827?style=flat-square&logo=amazonwebservices&logoColor=FF9900" alt="Organizations · SCPs"/>
  <img src="https://img.shields.io/badge/-KMS_·_Cognito-111827?style=flat-square&logo=letsencrypt&logoColor=FF9900" alt="KMS · Cognito"/>
  <img src="https://img.shields.io/badge/-Shield_(DDoS)-111827?style=flat-square&logo=instructure&logoColor=FF9900" alt="Shield (DDoS)"/>
</p>

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%203%20-%20Proteção%20de%20uma%20nova%20conta%20da%20AWS.md">⬅️ Anterior: Proteção de uma nova conta</a> &nbsp;•&nbsp;
  <a href="./Seção%205%20-%20Proteção%20de%20dados%20na%20AWS.md">Próxima: Proteção de dados ➡️</a>
</p>

![Módulo 4, Seção 4: Proteção de contas](../img/m4-secao4-capa.png)

## 📑 Sumário

| # | Tópico |
|:---:|---|
| 1 | [🏢 AWS Organizations](#organizations) |
| 2 | [🚧 Políticas de controle de serviço (SCPs)](#scps) |
| 3 | [🔑 AWS Key Management Service (AWS KMS)](#kms) |
| 4 | [👤 Amazon Cognito](#cognito) |
| 5 | [🛡️ AWS Shield](#shield) |
| 🎯 | [Principais conclusões](#conclusoes) |

| Serviço | Em uma frase |
|---|---|
| 🏢 **AWS Organizations** | Gerencia **várias contas** de forma centralizada. |
| 🚧 **SCPs** | Definem as **permissões máximas** das contas de uma organização. |
| 🔑 **AWS KMS** | Cria e gerencia **chaves de criptografia**. |
| 👤 **Amazon Cognito** | **Login e controle de acesso** para aplicativos Web e móveis. |
| 🛡️ **AWS Shield** | Proteção gerenciada contra ataques **DDoS**. |

---

<a id="organizations"></a>
## 1. 🏢 AWS Organizations

![AWS Organizations](../img/m4-secao4-organizations.png)

O **AWS Organizations** permite **consolidar várias contas** da AWS para que você as **gerencie de maneira centralizada**. (O lado de faturamento consolidado foi visto no [Módulo 2 – AWS Organizations](../MÓDULO%202/Seção%203%20-%20AWS%20Organizations.md).)

**Recursos de segurança do AWS Organizations:**

| Recurso | Detalhe |
|---|---|
| 🗂️ **Unidades organizacionais (OUs)** | Agrupe contas da AWS em **OUs** e anexe **políticas de acesso diferentes** a cada OU. |
| 🔐 **Integração e suporte para o IAM** | As permissões de um usuário são a **interseção** do que é permitido pelo **AWS Organizations** e do que é concedido pelo **IAM** naquela conta. |
| 🚧 **Políticas de controle de serviço (SCPs)** | Estabelecem controle sobre os **serviços** da AWS e as **ações de API** que cada conta pode acessar. |

```mermaid
flowchart LR
    O["🚧 Permitido pelo<br/>Organizations (SCP)"] --- X(("✅ Permissão<br/>efetiva"))
    I["🔐 Concedido<br/>pelo IAM"] --- X
    style O fill:#FF9900,color:#111827,stroke:#111827
    style I fill:#2E5A88,color:#FFFFFF,stroke:#111827
    style X fill:#1F7A4D,color:#FFFFFF,stroke:#111827
```

> [!TIP]
> Pense em **interseção**: o usuário só consegue fazer algo se **as duas** camadas permitirem. Se o IAM concede `s3:*` mas a SCP da conta bloqueia o S3, o acesso é **negado**.

<a id="scps"></a>
## 2. 🚧 Políticas de controle de serviço (SCPs)

![AWS Organizations: políticas de controle de serviço](../img/m4-secao4-scps.png)

- 🎛️ As **políticas de controle de serviço (SCPs)** oferecem **controle centralizado sobre contas**: limitam as permissões disponíveis em uma conta que faça parte de uma organização.
- ✅ Garantem que as contas estejam em **conformidade** com as diretrizes de controle de acesso.

| | 🚧 SCP | 📄 Política do IAM |
|---|---|---|
| **Sintaxe** | JSON, **semelhante** | JSON |
| **Concede permissões?** | ❌ **Nunca** | ✅ Sim |
| **Papel** | Especifica as **permissões máximas** para uma organização (um "teto") | Concede permissões a usuários, grupos e funções |

> [!IMPORTANT]
> Uma SCP **nunca concede** permissões. Ela só define o **limite máximo**; quem concede de fato é o **IAM**.

<a id="kms"></a>
## 3. 🔑 AWS Key Management Service (AWS KMS)

![AWS Key Management Service (AWS KMS)](../img/m4-secao4-kms.png)

Recursos do **AWS KMS**:

- 🗝️ Permite **criar e gerenciar chaves de criptografia**.
- 🎛️ Permite **controlar o uso da criptografia** nos serviços da AWS e nos aplicativos.
- 📜 Integra-se ao **AWS CloudTrail** para **registrar todo o uso de chaves** (ver [Seção 3](./Seção%203%20-%20Proteção%20de%20uma%20nova%20conta%20da%20AWS.md#etapa3)).
- 🔒 Usa **módulos de segurança de hardware (HSMs)** validados pelo **Federal Information Processing Standards (FIPS) 140-2** para proteger as chaves.

<a id="cognito"></a>
## 4. 👤 Amazon Cognito

![Amazon Cognito](../img/m4-secao4-cognito.png)

Recursos do **Amazon Cognito**:

- 📝 Adiciona **inscrição, login e controle de acesso** de usuários a **aplicativos Web e móveis**.
- 📈 **Ajusta a escala** até **milhões de usuários**.
- 🌐 Oferece suporte a login com:

| Tipo de provedor | Exemplos |
|---|---|
| 👥 **Identidade social** | **Facebook**, **Google** e **Amazon** |
| 🏢 **Identidade corporativa** | **Microsoft Active Directory**, por meio do **SAML 2.0** (*Security Assertion Markup Language*) |

> [!NOTE]
> **IAM vs. Cognito:** o IAM controla quem acessa **a sua conta da AWS** (funcionários, aplicativos, serviços); o Cognito controla os **usuários finais do seu aplicativo** (clientes que se cadastram no seu site ou app).

<a id="shield"></a>
## 5. 🛡️ AWS Shield

![AWS Shield](../img/m4-secao4-shield.png)

Recursos do **AWS Shield**:

- 🛡️ É um **serviço gerenciado de proteção contra negação de serviço distribuída (DDoS)**.
- ☁️ **Protege aplicativos** executados na AWS.
- ⚡ Fornece **detecção sempre ativada** e **mitigações automáticas em linha**.
- 🎯 Use-o para **minimizar o tempo de inatividade e a latência** do aplicativo.

| Plano | Custo |
|---|---|
| 🟢 **AWS Shield Standard** | Habilitado **sem custo adicional** |
| 🟠 **AWS Shield Advanced** | Serviço **pago opcional** |

---

<a id="conclusoes"></a>
## 🎯 Principais conclusões

- ✅ O **AWS Organizations** gerencia várias contas de forma centralizada, agrupando-as em **OUs** com políticas diferentes.
- ✅ A permissão efetiva de um usuário é a **interseção** do que o **Organizations** permite com o que o **IAM** concede.
- ✅ As **SCPs** definem as **permissões máximas** de uma conta, mas **nunca concedem** permissões.
- ✅ O **AWS KMS** cria e gerencia **chaves de criptografia**, usa **HSMs FIPS 140-2** e registra o uso das chaves no **CloudTrail**.
- ✅ O **Amazon Cognito** adiciona **cadastro e login** a aplicativos Web e móveis, com provedores sociais e corporativos (**SAML 2.0**).
- ✅ O **AWS Shield** protege contra **DDoS**: o **Standard** é gratuito e o **Advanced** é pago.

---

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%203%20-%20Proteção%20de%20uma%20nova%20conta%20da%20AWS.md">⬅️ Anterior: Proteção de uma nova conta</a> &nbsp;•&nbsp;
  <a href="./Seção%205%20-%20Proteção%20de%20dados%20na%20AWS.md">Próxima: Proteção de dados ➡️</a>
</p>
