<h1 align="center">📋 Seção 6 – Trabalhar para garantir a conformidade</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Módulo_4-Segurança_na_Nuvem_AWS-111827?style=for-the-badge&labelColor=FF9900" alt="Módulo 4"/>
  <img src="https://img.shields.io/badge/Seção-6-111827?style=for-the-badge&labelColor=232F3E" alt="Seção 6"/>
  <br>
  <img src="https://img.shields.io/badge/-Programas_de_conformidade-111827?style=flat-square&logo=instructure&logoColor=FF9900" alt="Programas de conformidade"/>
  <img src="https://img.shields.io/badge/-AWS_Config_·_AWS_Artifact-111827?style=flat-square&logo=amazonwebservices&logoColor=FF9900" alt="AWS Config · AWS Artifact"/>
</p>

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%205%20-%20Proteção%20de%20dados%20na%20AWS.md">⬅️ Anterior: Proteção de dados na AWS</a> &nbsp;•&nbsp;
  <a href="./Seção%207%20-%20Conclusão%20do%20Módulo%204.md">Próxima: Conclusão do Módulo 4 ➡️</a>
</p>

![Módulo 4, Seção 6: Trabalhar para garantir a conformidade](../img/m4-secao6-capa.png)

## 📑 Sumário

| # | Tópico |
|:---:|---|
| 1 | [📜 Programas de conformidade da AWS](#programas) |
| 2 | [⚙️ AWS Config](#config) |
| 3 | [📁 AWS Artifact](#artifact) |
| 🎯 | [Principais conclusões](#conclusoes) |

| Serviço | Pergunta que responde |
|---|---|
| ⚙️ **AWS Config** | "Os **meus recursos** estão configurados como deveriam?" |
| 📁 **AWS Artifact** | "Onde estão os **relatórios de conformidade da AWS** para mostrar ao auditor?" |

---

<a id="programas"></a>
## 1. 📜 Programas de conformidade da AWS

![Programas de conformidade da AWS](../img/m4-secao6-programas-conformidade.png)

- ⚖️ Os clientes estão sujeitos a **muitos regulamentos e requisitos** diferentes de segurança e conformidade.
- 🔎 A AWS **contrata órgãos de certificação e auditores independentes** para fornecer aos clientes informações detalhadas sobre as **políticas, os processos e os controles** estabelecidos e operados pela AWS.

Os programas de conformidade podem ser **categorizados amplamente** em:

| Categoria | Descrição | Exemplos |
|---|---|---|
| 🏅 **Certificações e declarações** | Avaliadas por um **auditor externo independente** | **ISO 27001**, **27017**, **27018** e **ISO/IEC 9001** |
| ⚖️ **Leis, regulamentos e privacidade** | A AWS fornece **recursos de segurança e contratos legais** para apoiar a conformidade | **GDPR** (Regulamento Geral de Proteção de Dados) da UE, **HIPAA** |
| 🎯 **Alinhamentos e estruturas** | Requisitos de segurança ou conformidade **específicos do setor ou da função** | **Center for Internet Security (CIS)**, certificado **Privacy Shield entre UE e EUA** |

> [!NOTE]
> As certificações da AWS cobrem a **infraestrutura** (segurança **DA** nuvem). Elas não tornam automaticamente a **sua aplicação** conforme: isso continua sendo responsabilidade do cliente, como no [modelo de responsabilidade compartilhada](./Seção%201%20-%20Modelo%20de%20responsabilidade%20compartilhada%20da%20AWS.md).

<a id="config"></a>
## 2. ⚙️ AWS Config

![AWS Config](../img/m4-secao6-aws-config.png)

O **AWS Config** é usado para **avaliar, auditar e analisar** as configurações dos recursos da AWS.

- 🔍 **Avalie e audite** as configurações dos recursos da AWS.
- 🔄 Use para **monitoramento contínuo** de configurações.
- ⚖️ **Avalie automaticamente** as configurações **registradas** em comparação com as configurações **desejadas**.
- 📝 **Analise as alterações** de configuração.
- 🕓 Visualize **históricos de configuração** detalhados.
- ✅ **Simplifique a auditoria de conformidade** e a análise de segurança.

**No exemplo do painel do AWS Config** (*Config Dashboard*):

| Indicador | Valor |
|---|---:|
| 📦 **Recursos** registrados (*Total resource count*) | 48 |
| 📏 **Regras não conformes** (*Noncompliant rules*) | 1 (`required-tags`) |
| ⚠️ **Recursos não conformes** (*Noncompliant resources*) | 35 |

```mermaid
flowchart LR
    R["📦 Configuração<br/>registrada"] --> C{"⚖️ Regra do<br/>AWS Config"}
    D["🎯 Configuração<br/>desejada"] --> C
    C -->|igual| OK["✅ Conforme"]
    C -->|diferente| NOK["⚠️ Não conforme"]
    style OK fill:#1F7A4D,color:#FFFFFF,stroke:#111827
    style NOK fill:#B91C1C,color:#FFFFFF,stroke:#111827
```

<a id="artifact"></a>
## 3. 📁 AWS Artifact

![AWS Artifact](../img/m4-secao6-aws-artifact.png)

O **AWS Artifact** é um **recurso para informações relacionadas à conformidade**: fornece **downloads sob demanda** de documentos de segurança e conformidade.

- 📄 Forneça acesso a **relatórios de segurança e conformidade** e selecione **contratos on-line**.
- ⬇️ Exemplos de downloads:
  - 🏅 **Certificações ISO** da AWS.
  - 💳 Relatórios do **Payment Card Industry (PCI)** e do **Service Organization Control (SOC)**.

**Como acessar:** no **Console de Gerenciamento da AWS**, em **Security, Identity & Compliance** (*Segurança, Identificação e Conformidade*), clique em **Artifact** (*Artefato*).

> [!TIP]
> **Config vs. Artifact:** o **Config** verifica a conformidade dos **seus** recursos; o **Artifact** entrega os relatórios que comprovam a conformidade **da própria AWS**.

---

<a id="conclusoes"></a>
## 🎯 Principais conclusões

- ✅ A AWS contrata **auditores independentes** e mantém **programas de conformidade** para ajudar os clientes a atender regulamentos.
- ✅ Os programas se dividem em **certificações e declarações** (ISO), **leis, regulamentos e privacidade** (GDPR, HIPAA) e **alinhamentos e estruturas** (CIS).
- ✅ O **AWS Config** monitora continuamente as configurações dos recursos, compara o **registrado** com o **desejado** e mantém o **histórico** de alterações.
- ✅ O **AWS Artifact** oferece **download sob demanda** de relatórios de conformidade da AWS (ISO, PCI, SOC) e contratos on-line.

---

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%205%20-%20Proteção%20de%20dados%20na%20AWS.md">⬅️ Anterior: Proteção de dados na AWS</a> &nbsp;•&nbsp;
  <a href="./Seção%207%20-%20Conclusão%20do%20Módulo%204.md">Próxima: Conclusão do Módulo 4 ➡️</a>
</p>
