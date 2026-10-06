<h1 align="center">🏛️ Seção 3 – AWS Organizations</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Módulo_2-Economia_e_faturamento_da_nuvem-111827?style=for-the-badge&labelColor=FF9900" alt="Módulo 2"/>
  <img src="https://img.shields.io/badge/Seção-3_de_6-111827?style=for-the-badge&labelColor=232F3E" alt="Seção 3 de 6"/>
  <br>
  <img src="https://img.shields.io/badge/-Contas_·_OUs_·_SCPs-111827?style=flat-square&logo=instructure&logoColor=FF9900" alt="Contas · OUs · SCPs"/>
  <img src="https://img.shields.io/badge/-IAM-111827?style=flat-square&logo=amazoniam&logoColor=DD344C" alt="IAM"/>
  <img src="https://img.shields.io/badge/-Faturamento_consolidado-111827?style=flat-square&logo=cashapp&logoColor=FF9900" alt="Faturamento consolidado"/>
</p>

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%202%20-%20Custo%20total%20de%20propriedade.md">⬅️ Anterior: Custo total de propriedade</a> &nbsp;•&nbsp;
  <a href="./Seção%204%20-%20AWS%20Billing%20and%20Cost%20Management.md">Próxima: Billing and Cost Management ➡️</a>
</p>

![Módulo 2, Seção 3: AWS Organizations](../img/m2-secao3-capa.png)

## 📑 Sumário

| # | Tópico |
|:---:|---|
| 1 | [🏛️ Introdução ao AWS Organizations](#introducao) |
| 2 | [🌳 Terminologia do AWS Organizations](#terminologia) |
| 3 | [⭐ Principais recursos e benefícios](#recursos) |
| 4 | [🔒 Segurança com o AWS Organizations](#seguranca) |
| 5 | [🛠️ Configuração do Organizations](#configuracao) |
| 6 | [🖱️ Acessar o AWS Organizations](#acessar) |
| 🎯 | [Principais conclusões](#conclusoes) |

---

<a id="introducao"></a>
## 1. 🏛️ Introdução ao AWS Organizations

![Introdução ao AWS Organizations](../img/m2-secao3-introducao-organizations.png)

> [!NOTE]
> O **AWS Organizations** é um serviço de **gerenciamento de contas** que permite **consolidar várias contas da AWS em uma organização** que você cria e gerencia de forma centralizada.

- 🌳 As contas ficam agrupadas em uma **árvore organizacional** (hierarquia).
- 📜 Com ele é possível aplicar **políticas** a grupos de contas e centralizar o **faturamento**.
- 🏢 É útil quando a empresa tem **várias contas** (por exemplo, uma por time, projeto ou ambiente) e precisa de **governança** sobre todas elas.

<a id="terminologia"></a>
## 2. 🌳 Terminologia do AWS Organizations

![Terminologia do AWS Organizations](../img/m2-secao3-terminologia.png)

O diagrama mostra uma organização básica, formada por **sete contas** distribuídas em **quatro unidades organizacionais (UOs)** abaixo da **raiz**. Uma estrutura desse tipo pode ser representada assim:

```mermaid
flowchart TD
    R["🌳 Raiz"] --> OU1["📁 UO"]
    R --> OU2["📁 UO"]
    OU1 --> OU3["📁 UO"]
    OU2 --> OU4["📁 UO"]
    OU1 --> A1["👤 Conta"]
    OU3 --> A2["👤 Conta"]
    OU3 --> A3["👤 Conta"]
    OU2 --> A4["👤 Conta"]
    OU4 --> A5["👤 Conta"]
    OU4 --> A6["👤 Conta"]
    OU4 --> A7["👤 Conta"]
    P["📜 Política"] -. "anexada à UO:<br/>herdada por tudo abaixo" .-> OU2
    style R fill:#FF9900,color:#111827,stroke:#111827
    style P fill:#232F3E,color:#FFFFFF,stroke:#FF9900
```

| Termo | O que é |
|---|---|
| 🏢 **Organização (Empresa)** | Conjunto de contas da AWS gerenciadas de forma centralizada. |
| 🌳 **Raiz** | Contêiner do topo da hierarquia; todas as contas e UOs ficam abaixo dela. |
| 📁 **Unidade organizacional (UO / OU)** | Grupo de contas dentro da raiz. Uma UO pode conter **contas** e **outras UOs**, formando uma estrutura de árvore. |
| 👤 **Conta da AWS** | Contêiner dos recursos da AWS. Cada conta pertence a **uma única UO** (ou diretamente à raiz). |
| 📜 **Política** | Regra anexada à **raiz**, a uma **UO** ou a uma **conta individual**. |

> [!IMPORTANT]
> - Uma política anexada a uma **UO** se aplica a **todas as contas e UOs abaixo dela** (herança).
> - Uma política anexada à **raiz** afeta **a organização inteira**.

<a id="recursos"></a>
## 3. ⭐ Principais recursos e benefícios

![Principais recursos e benefícios](../img/m2-secao3-recursos-beneficios.png)

| Recurso | O que oferece |
|---|---|
| 📜 **Gerenciamento de contas baseado em políticas** | Criar políticas de controle de serviço (SCPs) que definem o que as contas podem ou não fazer. |
| 📁 **Gerenciamento de contas baseado em grupos** | Agrupar contas em UOs e aplicar políticas ao grupo inteiro, em vez de conta por conta. |
| 🤖 **APIs que automatizam o gerenciamento de contas** | Criar e gerenciar contas novas de forma programática, adicionando-as aos grupos certos. |
| 💳 **Faturamento consolidado** | Uma **única forma de pagamento** para todas as contas, com visão combinada dos custos e acesso a **descontos por volume** somando o uso de todas elas. |

O Organizations também permite aplicar **controles de segurança** a uma ou mais contas ao mesmo tempo.

<a id="seguranca"></a>
## 4. 🔒 Segurança com o AWS Organizations

![Segurança com o AWS Organizations](../img/m2-secao3-seguranca.png)

O controle de acesso combina dois tipos de política:

| | 🔑 Políticas do IAM | 🛡️ Políticas de controle de serviço (SCPs) |
|---|---|---|
| **Serviço** | AWS Identity and Access Management (IAM) | AWS Organizations |
| **Aplicadas a** | **Usuários, grupos e funções** (roles) | **Contas individuais** ou **grupos de contas em uma UO** |
| **Função** | Permitir ou negar acesso aos serviços da AWS | Permitir ou negar acesso aos serviços da AWS |

```mermaid
flowchart LR
    SCP["🛡️ SCP<br/>limite máximo da conta"] --> E{"✅ Acesso efetivo<br/>interseção SCP ∩ IAM"}
    IAM["🔑 Política do IAM<br/>permissões do usuário"] --> E
    style E fill:#FF9900,color:#111827,stroke:#111827
```

> [!WARNING]
> A SCP define o **limite máximo** do que uma conta pode fazer. Se um serviço for bloqueado por uma SCP, **nenhum usuário daquela conta consegue usá-lo**, nem o usuário raiz da conta, mesmo que uma política do IAM permita.

Na prática, o acesso efetivo é a **interseção** entre o que a SCP permite e o que a política do IAM concede.

<a id="configuracao"></a>
## 5. 🛠️ Configuração do Organizations

![Configuração do Organizations](../img/m2-secao3-configuracao.png)

A configuração segue **quatro etapas**:

```mermaid
flowchart LR
    A["1️⃣ Criar a<br/>organização"] --> B["2️⃣ Criar<br/>UOs"] --> C["3️⃣ Criar<br/>SCPs"] --> D["4️⃣ Testar as<br/>restrições"]
```

| Etapa | O que fazer |
|:---:|---|
| 1️⃣ **Criar a organização** | A partir da conta que será a **conta de gerenciamento** (antes chamada de conta mestre), convidando ou criando as demais contas. |
| 2️⃣ **Criar unidades organizacionais** | Montar a hierarquia de UOs e mover as contas para dentro delas. |
| 3️⃣ **Criar políticas de controle de serviço** | Definir as SCPs e anexá-las à raiz, às UOs ou às contas. |
| 4️⃣ **Testar as restrições** | Entrar nas contas afetadas e verificar se as permissões e bloqueios funcionam como esperado. |

<a id="acessar"></a>
## 6. 🖱️ Acessar o AWS Organizations

![Acessar o AWS Organizations](../img/m2-secao3-acessar-organizations.png)

Como os outros serviços da AWS (vistos na [Seção 3 do Módulo 1](../MÓDULO%201/Seção%203%20-%20Introdução%20à%20Amazon%20Web%20Services%20(AWS).md)), o AWS Organizations pode ser gerenciado por:

| 🖱️ Console | ⌨️ AWS CLI | 🧑‍💻 SDKs | 🔗 APIs de consulta HTTPS |
|---|---|---|---|
| Interface gráfica no navegador. | Comandos no terminal (ILC da AWS). | Bibliotecas para usar o serviço dentro do código de aplicações. | Chamadas diretas à API do serviço. |

---

<a id="conclusoes"></a>
## 🎯 Principais conclusões

- ✅ O **AWS Organizations** consolida **várias contas da AWS** em uma **organização** com gerenciamento centralizado.
- ✅ A hierarquia é formada por **raiz**, **unidades organizacionais (UOs)** e **contas**; políticas aplicadas a uma UO são **herdadas** por tudo abaixo dela.
- ✅ Os principais benefícios são o gerenciamento **baseado em políticas** e **em grupos**, a **automação via APIs** e o **faturamento consolidado**.
- ✅ **Políticas do IAM** controlam o acesso de **usuários, grupos e funções**; **SCPs** controlam o que **contas e UOs inteiras** podem fazer.
- ✅ A configuração segue quatro etapas: **criar a organização**, **criar UOs**, **criar SCPs** e **testar as restrições**.
- ✅ O serviço pode ser acessado pelo **console**, pela **CLI**, pelos **SDKs** e pelas **APIs HTTPS**.

---

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%202%20-%20Custo%20total%20de%20propriedade.md">⬅️ Anterior: Custo total de propriedade</a> &nbsp;•&nbsp;
  <a href="./Seção%204%20-%20AWS%20Billing%20and%20Cost%20Management.md">Próxima: Billing and Cost Management ➡️</a>
</p>
