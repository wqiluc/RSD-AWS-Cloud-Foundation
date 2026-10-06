<h1 align="center">🏁 Seção 5 – Conclusão do Módulo 1</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Módulo_1-Visão_geral_dos_conceitos_de_nuvem-111827?style=for-the-badge&labelColor=FF9900" alt="Módulo 1"/>
  <img src="https://img.shields.io/badge/Seção-5_de_5-111827?style=for-the-badge&labelColor=232F3E" alt="Seção 5 de 5"/>
  <br>
  <img src="https://img.shields.io/badge/-Questão_de_exame-111827?style=flat-square&logo=instructure&logoColor=FF9900" alt="Questão de exame"/>
  <img src="https://img.shields.io/badge/-Cloud_Practitioner-111827?style=flat-square&logo=amazonwebservices&logoColor=FF9900" alt="Cloud Practitioner"/>
  <img src="https://img.shields.io/badge/Módulo_1-concluído-111827?style=flat-square&labelColor=2EA043" alt="Módulo 1 concluído"/>
</p>

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%204%20-%20Mudança%20para%20a%20Nuvem%20AWS%20–%20AWS%20Cloud%20Adoption%20Framework%20(AWS%20CAF).md">⬅️ Anterior: AWS CAF</a> &nbsp;•&nbsp;
  <a href="../MÓDULO%202/Seção%201%20-%20Fundamentos%20da%20definição%20de%20preço.md">Próximo módulo: Fundamentos de preço ➡️</a>
</p>

## 📑 Sumário

| # | Tópico |
|:---:|---|
| 1 | [🗂️ Resumo do módulo](#resumo) |
| 2 | [📝 Exemplo de pergunta do exame](#pergunta) |
| 🎯 | [Principais conclusões](#conclusoes) |

---

<a id="resumo"></a>
## 1. 🗂️ Resumo do módulo

![Resumo do módulo](../img/m1-secao5-resumo-do-modulo.png)

Neste módulo, aprendemos a:

| Verbo | Objetivo | Seção |
|---|---|:---:|
| 📖 **Definir** | Os diferentes tipos de **modelos de computação em nuvem** (modelos de serviço IaaS, PaaS e SaaS e modelos de implantação: nuvem, híbrido e local) | [☁️ Seção 1](./Seção%201%20-%20%20Introdução%20à%20computação%20em%20nuvem.md) |
| 🗣️ **Descrever** | As **seis vantagens** da computação em nuvem | [🚀 Seção 2](./Seção%202%20-%20Vantagens%20da%20Computação%20em%20Nuvem.md) |
| 🔍 **Reconhecer** | As principais **categorias de serviços da AWS** e os principais serviços | [🟧 Seção 3](./Seção%203%20-%20Introdução%20à%20Amazon%20Web%20Services%20(AWS).md) |
| 🔁 **Revisar** | O conteúdo do **AWS Cloud Adoption Framework (AWS CAF)** e suas seis perspectivas | [🧭 Seção 4](./Seção%204%20-%20Mudança%20para%20a%20Nuvem%20AWS%20–%20AWS%20Cloud%20Adoption%20Framework%20(AWS%20CAF).md) |

```mermaid
flowchart LR
    S1["☁️ Seção 1<br/>O que é a nuvem"] --> S2["🚀 Seção 2<br/>Por que usar"] --> S3["🟧 Seção 3<br/>O que a AWS oferece"] --> S4["🧭 Seção 4<br/>Como adotar"] --> S5["🏁 Seção 5<br/>Revisão"]
    style S5 fill:#FF9900,color:#111827,stroke:#111827
```

<a id="pergunta"></a>
## 2. 📝 Exemplo de pergunta do exame

![Exemplo de pergunta do exame](../img/m1-secao5-pergunta-exame.png)

> [!NOTE]
> **Por que a AWS é mais econômica do que datacenters tradicionais para aplicativos com cargas de trabalho de computação variáveis?**

| | Alternativa |
|:---:|---|
| **A** | Os custos do Amazon Elastic Compute Cloud (Amazon EC2) são cobrados mensalmente. |
| **B** | Os clientes mantêm o acesso administrativo completo às suas instâncias do Amazon EC2. |
| **C** | As instâncias do Amazon EC2 podem ser executadas sob demanda quando necessário. |
| **D** | Os clientes podem executar permanentemente instâncias suficientes para lidar com picos de carga de trabalho. |

<details>
<summary>💡 <strong>Clique para ver a resposta</strong></summary>

<br>

![Resposta da pergunta do exame](../img/m1-secao5-pergunta-exame-resposta.png)

🔑 As palavras-chave da pergunta são **"AWS é mais econômica do que datacenters tradicionais"** e **"variáveis"**.

> [!TIP]
> ✅ **Resposta correta: C.** As instâncias do Amazon EC2 podem ser executadas **sob demanda** quando necessário.

Por que as outras estão erradas:

| Alternativa | Por que não é a resposta |
|:---:|---|
| ❌ **A** | A forma de cobrança (mensal) não torna a AWS mais econômica; o que importa é pagar **só pelo que se usa**. |
| ❌ **B** | Acesso administrativo é uma questão de **controle**, não de custo. |
| ❌ **D** | Manter instâncias ligadas o tempo todo para o pico é justamente o problema do modelo tradicional: **capacidade superestimada** e recursos ociosos. |

Isso retoma duas vantagens da [Seção 2](./Seção%202%20-%20Vantagens%20da%20Computação%20em%20Nuvem.md): **trocar despesas de capital por despesas variáveis** e **parar de tentar adivinhar a capacidade**, escalando conforme a demanda.

</details>

---

<a id="conclusoes"></a>
## 🎯 Principais conclusões

- ✅ A computação em nuvem é a **entrega sob demanda** de recursos de TI pela internet, com **pagamento conforme o uso**.
- ✅ Ela traz **seis vantagens** em relação ao modelo tradicional, entre elas custo variável, economia de escala e escalabilidade sob demanda.
- ✅ A **AWS** oferece uma ampla gama de serviços, organizados em **categorias**, acessíveis pelo console, pela CLI ou pelos SDKs.
- ✅ O **AWS CAF** orienta a adoção da nuvem em **toda a organização**, por meio de **seis perspectivas**.
- ✅ Para cargas de trabalho **variáveis**, a nuvem é mais econômica porque os recursos podem ser **executados sob demanda**, só quando necessário.

---

<p align="center">
  <a href="../README.md">🏠 Início</a> &nbsp;•&nbsp;
  <a href="./Seção%204%20-%20Mudança%20para%20a%20Nuvem%20AWS%20–%20AWS%20Cloud%20Adoption%20Framework%20(AWS%20CAF).md">⬅️ Anterior: AWS CAF</a> &nbsp;•&nbsp;
  <a href="../MÓDULO%202/Seção%201%20-%20Fundamentos%20da%20definição%20de%20preço.md">Próximo módulo: Fundamentos de preço ➡️</a>
</p>
