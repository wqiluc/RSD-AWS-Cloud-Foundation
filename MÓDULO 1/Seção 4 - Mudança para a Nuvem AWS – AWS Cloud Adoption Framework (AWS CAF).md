<h1 align="center">🧭 Seção 4 – Mudança para a Nuvem AWS – AWS Cloud Adoption Framework (AWS CAF)</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Módulo_1-Visão_geral_dos_conceitos_de_nuvem-111827?style=for-the-badge&labelColor=FF9900" alt="Módulo 1"/>
  <img src="https://img.shields.io/badge/Seção-4_de_5-111827?style=for-the-badge&labelColor=232F3E" alt="Seção 4 de 5"/>
  <br>
  <img src="https://img.shields.io/badge/-6_perspectivas_do_CAF-111827?style=flat-square&logo=instructure&logoColor=FF9900" alt="6 perspectivas do CAF"/>
  <img src="https://img.shields.io/badge/-Empresarial_·_Técnico-111827?style=flat-square&logo=databricks&logoColor=FF9900" alt="Empresarial · Técnico"/>
</p>

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%203%20-%20Introdução%20à%20Amazon%20Web%20Services%20(AWS).md">⬅️ Anterior: Introdução à AWS</a> &nbsp;•&nbsp;
  <a href="./Seção%205%20-%20Conclusão%20do%20Módulo%201.md">Próxima: Conclusão do Módulo 1 ➡️</a>
</p>

![Módulo 1, Seção 4: Mudança para a Nuvem AWS – AWS Cloud Adoption Framework (AWS CAF)](../img/m1-secao4-capa.png)

## 📑 Sumário

| # | Tópico |
|:---:|---|
| 1 | [❓ O que é o AWS CAF?](#o-que-e) |
| 2 | [🧩 Seis perspectivas principais](#seis-perspectivas) |
| 3 | [💼 Perspectiva empresarial (Negócios)](#negocios) |
| 4 | [👥 Perspectiva das pessoas](#pessoas) |
| 5 | [⚖️ Perspectiva da governança](#governanca) |
| 6 | [🏗️ Perspectiva da plataforma](#plataforma) |
| 7 | [🔒 Perspectiva de segurança](#seguranca) |
| 8 | [⚙️ Perspectiva de operações](#operacoes) |
| 📋 | [Resumo das perspectivas](#resumo) |
| 🎯 | [Principais conclusões](#conclusoes) |

---

<a id="o-que-e"></a>
## 1. ❓ O que é o AWS CAF?

![AWS Cloud Adoption Framework (AWS CAF)](../img/m1-secao4-aws-caf.png)

Migrar para a nuvem não é só uma questão técnica: envolve pessoas, processos, orçamento e estratégia. O **AWS Cloud Adoption Framework (AWS CAF)** existe para organizar essa mudança.

> [!NOTE]
> O AWS CAF oferece **orientação e melhores práticas** para ajudar as organizações a criar uma **abordagem abrangente** para a computação em nuvem, **em toda a organização** e **durante todo o ciclo de vida de TI**, para **acelerar a adoção bem-sucedida da nuvem**.

- 🧩 O AWS CAF está organizado em **seis perspectivas**.
- 🛠️ Cada perspectiva consiste em um conjunto de **recursos** (capacidades), que indicam quem é responsável pelo quê e o que precisa ser preparado.

<a id="seis-perspectivas"></a>
## 2. 🧩 Seis perspectivas principais

![Seis perspectivas principais](../img/m1-secao4-seis-perspectivas.png)

As seis perspectivas se dividem em dois grupos:

```mermaid
mindmap
  root((🧭 AWS CAF))
    💼 Foco empresarial
      💼 Negócios
      👥 Pessoas
      ⚖️ Governança
    🛠️ Foco técnico
      🏗️ Plataforma
      🔒 Segurança
      ⚙️ Operações
```

| 💼 Foco nos recursos **empresariais** | 🛠️ Foco nos recursos **técnicos** |
|---|---|
| 💼 Negócios | 🏗️ Plataforma |
| 👥 Pessoas | 🔒 Segurança |
| ⚖️ Governança | ⚙️ Operações |

Cada perspectiva tem uma **pergunta central** e um **público** (as partes interessadas), detalhados a seguir.

<a id="negocios"></a>
## 3. 💼 Perspectiva empresarial (Negócios)

![Perspectiva empresarial](../img/m1-secao4-perspectiva-empresarial.png)

> [!IMPORTANT]
> É necessário garantir que a **TI esteja alinhada com as necessidades empresariais** e que os investimentos em TI possam ser relacionados a **resultados comerciais demonstráveis**.

| 👤 Partes interessadas | 🛠️ Recursos |
|---|---|
| Gerentes de negócios<br>Gerentes financeiros<br>Proprietários de orçamento<br>Partes interessadas da estratégia | Finanças de TI<br>Estratégia de TI<br>Realização de benefícios<br>Gerenciamento de riscos empresariais |

Com essa perspectiva, a organização consegue montar um **caso de negócios** sólido para justificar a adoção da nuvem.

<a id="pessoas"></a>
## 4. 👥 Perspectiva das pessoas

![Perspectiva das pessoas](../img/m1-secao4-perspectiva-pessoas.png)

> [!IMPORTANT]
> É necessário priorizar o **treinamento, a equipe e as mudanças organizacionais** para criar uma **organização ágil**.

| 👤 Partes interessadas | 🛠️ Recursos |
|---|---|
| Recursos humanos (RH)<br>Equipe<br>Gerentes de pessoas | Gerenciamento de recursos<br>Gerenciamento de incentivos<br>Gerenciamento de carreiras<br>Gerenciamento de treinamento<br>Gerenciamento de mudança organizacional |

A ideia é preparar as pessoas para novas funções e habilidades que a nuvem exige.

<a id="governanca"></a>
## 5. ⚖️ Perspectiva da governança

![Perspectiva da governança](../img/m1-secao4-perspectiva-governanca.png)

> [!IMPORTANT]
> É necessário garantir que **as habilidades e os processos alinhem a estratégia e as metas de TI com a estratégia e as metas empresariais**, para que a organização possa **maximizar o valor empresarial** do investimento em TI e **minimizar os riscos empresariais**.

| 👤 Partes interessadas | 🛠️ Recursos |
|---|---|
| CIO<br>Gerentes de programas<br>Arquitetos empresariais<br>Analistas de negócios<br>Gerentes de portfólio | Gerenciamento de portfólio<br>Gerenciamento de programas e projetos<br>Medição de desempenho empresarial<br>Gerenciamento de licenças |

<a id="plataforma"></a>
## 6. 🏗️ Perspectiva da plataforma

![Perspectiva da plataforma](../img/m1-secao4-perspectiva-plataforma.png)

> [!IMPORTANT]
> É necessário **compreender e comunicar a natureza dos sistemas de TI e seus relacionamentos**. Devemos ter a capacidade de **descrever a arquitetura do ambiente de estado de destino** em detalhes.

| 👤 Partes interessadas | 🛠️ Recursos |
|---|---|
| CTO<br>Gerentes de TI<br>Arquitetos de soluções | Provisionamento de computação<br>Provisionamento de rede<br>Provisionamento de armazenamento<br>Provisionamento de banco de dados<br>Arquitetura de sistemas e soluções<br>Desenvolvimento de aplicativos |

Em resumo: definir **como** será a infraestrutura na nuvem, usando padrões arquitetônicos e modelos.

<a id="seguranca"></a>
## 7. 🔒 Perspectiva de segurança

![Perspectiva de segurança](../img/m1-secao4-perspectiva-seguranca.png)

> [!IMPORTANT]
> É necessário garantir que a organização **atenda aos seus objetivos de segurança**.

| 👤 Partes interessadas | 🛠️ Recursos |
|---|---|
| CISO<br>Gerentes de segurança de TI<br>Analistas de segurança de TI | Gerenciamento de identidade e acesso<br>Controle detectivo<br>Segurança de infraestrutura<br>Proteção de dados<br>Resposta a incidentes |

Esses recursos cobrem visibilidade, auditabilidade, controle e agilidade na segurança do ambiente em nuvem.

<a id="operacoes"></a>
## 8. ⚙️ Perspectiva de operações

![Perspectiva de operações](../img/m1-secao4-perspectiva-operacoes.png)

> [!IMPORTANT]
> Alinhamos e apoiamos as operações da empresa e **definimos como os negócios serão conduzidos a cada dia, trimestre e ano**.

| 👤 Partes interessadas | 🛠️ Recursos |
|---|---|
| Gerentes de operações de TI<br>Gerentes de suporte de TI | Monitoramento de serviços<br>Monitoramento da performance do aplicativo<br>Gerenciamento do inventário de recursos<br>Gerenciamento de versões / gerenciamento de alterações<br>Relatórios e análises<br>Continuidade dos negócios / Recuperação de desastres<br>Catálogo de serviços de TI |

---

<a id="resumo"></a>
## 📋 Resumo das perspectivas

| Grupo | Perspectiva | Foco | Partes interessadas |
|:---:|---|---|---|
| 💼 | **Negócios** | TI alinhada às necessidades e resultados do negócio | Gerentes de negócios e financeiros, donos de orçamento, estratégia |
| 💼 | **Pessoas** | Treinamento, equipe e mudança organizacional | RH, equipe, gerentes de pessoas |
| 💼 | **Governança** | Alinhar metas de TI às metas do negócio, maximizando valor e reduzindo riscos | CIO, gerentes de programas, arquitetos empresariais, analistas de negócios, gerentes de portfólio |
| 🛠️ | **Plataforma** | Arquitetura e implementação da infraestrutura na nuvem | CTO, gerentes de TI, arquitetos de soluções |
| 🛠️ | **Segurança** | Cumprir os objetivos de segurança | CISO, gerentes e analistas de segurança de TI |
| 🛠️ | **Operações** | Executar, operar e recuperar as cargas de trabalho no dia a dia | Gerentes de operações e de suporte de TI |

> 💼 = foco empresarial &nbsp;•&nbsp; 🛠️ = foco técnico

---

<a id="conclusoes"></a>
## 🎯 Principais conclusões

- ✅ A adoção da nuvem exige mudanças **em toda a organização**, não apenas na tecnologia.
- ✅ O **AWS CAF** fornece **orientação e melhores práticas** para planejar e acelerar essa adoção.
- ✅ O AWS CAF é organizado em **seis perspectivas**: **Negócios, Pessoas e Governança** (foco empresarial) e **Plataforma, Segurança e Operações** (foco técnico).
- ✅ Cada perspectiva é formada por um conjunto de **recursos** e envolve **partes interessadas** específicas.

---

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%203%20-%20Introdução%20à%20Amazon%20Web%20Services%20(AWS).md">⬅️ Anterior: Introdução à AWS</a> &nbsp;•&nbsp;
  <a href="./Seção%205%20-%20Conclusão%20do%20Módulo%201.md">Próxima: Conclusão do Módulo 1 ➡️</a>
</p>
