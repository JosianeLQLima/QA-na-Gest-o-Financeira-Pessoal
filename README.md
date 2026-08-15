# QA na Gestão Financeira Pessoal — Orçamento Pessoal

## Análise dos Requisitos REQ_01 e REQ_02

Este documento apresenta a primeira etapa do projeto de QA aplicado à aplicação web **Orçamento Pessoal**.

Nesta fase, o trabalho está concentrado na análise de dois requisitos:

* **REQ_01 — Cadastro e Acesso**
* **REQ_02 — Visão Geral**

A ideia é começar pelos fluxos de acesso e pela primeira tela apresentada ao utilizador após a autenticação, antes de avançar para as funcionalidades financeiras mais complexas.

---

## Sobre o Projeto

Este projeto faz parte do meu portfólio de **QA / Testes de Software** e tem como objetivo aplicar técnicas de testes manuais em uma aplicação web real.

Escolhi o **Orçamento Pessoal** por ser uma aplicação relacionada à gestão financeira pessoal, área que permite trabalhar com diferentes regras de negócio e que possui relação direta entre suas funcionalidades.

Nesta primeira etapa, o foco está em entender como o utilizador entra no sistema e quais informações são apresentadas depois do acesso.

A partir dessa análise serão levantados os requisitos, cenários de teste e posteriormente os casos de teste correspondentes.

---

## Sistema Analisado

| Item                                  | Descrição                         |
| ------------------------------------- | --------------------------------- |
| **Sistema**                           | Orçamento Pessoal                 |
| **Website**                           | https://www.orcamentopessoal.net/ |
| **Tipo de aplicação**                 | Gestão financeira pessoal         |
| **Plataforma**                        | Web                               |
| **Tipo de teste**                     | Testes manuais                    |
| **Abordagem**                         | Testes funcionais e exploratórios |
| **Requisitos analisados nesta etapa** | 2                                 |
| **Requisitos totais planejados**      | 8                                 |
| **Status**                            | Em desenvolvimento                |

---

# Objetivo desta Etapa

O objetivo desta primeira etapa é analisar os comportamentos relacionados ao **acesso à aplicação** e à **visão geral apresentada ao utilizador**.

A análise será utilizada como base para:

* entender o comportamento real da aplicação;
* identificar os campos e elementos envolvidos;
* levantar regras de negócio;
* identificar possíveis riscos;
* definir cenários de teste;
* elaborar casos de teste;
* registrar evidências durante a execução;
* identificar possíveis defeitos.

---

# Requisitos Analisados

Nesta etapa foram selecionados os dois primeiros requisitos do projeto.

| ID         | Categoria         | Prioridade | Status     |
| ---------- | ----------------- | ---------- | ---------- |
| **REQ_01** | Cadastro e Acesso | Alta       | Em análise |
| **REQ_02** | Visão Geral       | Alta       | Em análise |

Os demais requisitos serão analisados posteriormente.

---

# REQ_01 — Cadastro e Acesso

### Descrição

O sistema deve permitir que o utilizador realize seu cadastro e posteriormente acesse a aplicação utilizando suas credenciais.

### Objetivo do teste

Verificar se o utilizador consegue realizar o processo de cadastro e autenticação de acordo com o comportamento esperado pela aplicação.

### Pontos que serão analisados

* Acesso à tela de cadastro;
* Campos disponíveis no cadastro;
* Campos obrigatórios;
* Preenchimento dos dados;
* Validação dos dados informados;
* Criação da conta;
* Acesso com credenciais válidas;
* Tentativa de acesso com credenciais inválidas;
* Campos vazios;
* Mensagens apresentadas ao utilizador;
* Comportamento após o login;
* Redirecionamento para a área autenticada.

### Principais riscos

Uma falha neste requisito pode impedir o utilizador de criar uma conta ou acessar suas informações financeiras.

Também serão observados comportamentos que possam permitir o acesso incorreto à aplicação ou apresentar mensagens de validação inadequadas.

### Fluxo analisado

```text
Página Inicial
      │
      ▼
Cadastro / Login
      │
      ├──────────────► Criar Conta
      │                     │
      │                     ▼
      │                Preencher Dados
      │                     │
      │                     ▼
      │                 Finalizar
      │                     │
      │                     ▼
      │              Conta Criada
      │
      ▼
Informar Credenciais
      │
      ▼
Validar Acesso
      │
      ▼
Área Autenticada
```

---

# REQ_02 — Visão Geral

### Descrição

Após o acesso, o sistema deve apresentar uma visão geral das informações financeiras do utilizador.

Essa tela será analisada considerando as informações disponíveis e a consistência dos dados apresentados.

### Objetivo do teste

Verificar se a visão geral apresenta corretamente as informações disponíveis para o utilizador após o login.

### Pontos que serão analisados

* Acesso à visão geral;
* Elementos apresentados na tela;
* Resumo financeiro;
* Saldos;
* Receitas;
* Despesas;
* Contas próximas do vencimento;
* Informações financeiras apresentadas;
* Navegação a partir da visão geral;
* Atualização das informações após alterações;
* Consistência entre os dados apresentados e os registros realizados.

### Principais riscos

Como a visão geral concentra informações importantes para o acompanhamento financeiro, valores incorretos ou informações desatualizadas podem levar o utilizador a interpretar sua situação financeira de maneira equivocada.

### Fluxo analisado

```text
Login realizado
      │
      ▼
Área autenticada
      │
      ▼
Visão Geral
      │
      ├──► Saldo
      │
      ├──► Receitas
      │
      ├──► Despesas
      │
      ├──► Contas
      │
      └──► Outras informações financeiras
```

---

# Estratégia de Testes

Para os requisitos REQ_01 e REQ_02 serão utilizados principalmente **testes manuais funcionais**.

A análise também contará com testes exploratórios para identificar comportamentos que não estejam inicialmente descritos nos cenários planejados.

### Técnicas utilizadas

#### Particionamento de Equivalência

Será utilizado principalmente na validação dos campos de cadastro e acesso.

Exemplos:

* Dados válidos;
* Dados inválidos;
* Campos vazios;
* Formatos incorretos;
* Credenciais válidas;
* Credenciais inválidas.

#### Análise de Valor Limite — BVA

Será aplicada quando forem identificados campos com limites de caracteres, tamanho ou outras restrições.

#### Testes Exploratórios

Serão utilizados para investigar comportamentos inesperados durante a navegação pelas telas de cadastro, login e visão geral.

---

# Cenários que serão considerados

Para o **REQ_01**, serão analisados cenários como:

* Acessar a tela de cadastro;
* Realizar cadastro com dados válidos;
* Tentar cadastrar com campos obrigatórios vazios;
* Utilizar dados em formato inválido;
* Realizar login com credenciais válidas;
* Realizar login com credenciais inválidas;
* Tentar acessar sem preencher os campos;
* Verificar mensagens apresentadas;
* Verificar o redirecionamento após o login.

Para o **REQ_02**, serão analisados cenários como:

* Acessar a visão geral após login;
* Verificar os elementos apresentados;
* Verificar os valores exibidos;
* Verificar informações de receitas e despesas;
* Verificar o saldo apresentado;
* Verificar informações relacionadas às contas;
* Realizar uma alteração e verificar a atualização da visão geral;
* Verificar a consistência das informações apresentadas.

A quantidade final de casos de teste será definida após a análise detalhada das telas e aplicação das técnicas de projeto de testes.

---

# Artefatos desta Etapa

Os documentos relacionados aos requisitos REQ_01 e REQ_02 serão organizados da seguinte forma:

```text
01-Requisitos/
│
├── Engenharia_de_Requisitos.xlsx
├── Requisitos_Funcionais.md
└── Regras_de_Negocio.md
│
03-Casos-de-Teste/
└── Casos-de-Teste.xlsx
│
06-Evidencias/
├── REQ_01-Cadastro-e-Acesso/
└── REQ_02-Visao-Geral/
```

Conforme o projeto avançar, novos artefatos serão adicionados ao repositório.

---

# Critérios de Análise

Durante a execução dos testes serão observados principalmente:

* Comportamento esperado versus comportamento real;
* Validação dos dados;
* Mensagens apresentadas;
* Navegação;
* Persistência das informações;
* Consistência dos dados;
* Facilidade de utilização;
* Comportamentos inesperados;
* Impacto de possíveis falhas.

Quando um comportamento diferente do esperado for identificado, ele será analisado para determinar se caracteriza um defeito e, caso necessário, será registrado posteriormente na pasta de bugs.

---

# Status do Projeto

🟡 **Em desenvolvimento**

### Requisitos

* [x] Definição do REQ_01 — Cadastro e Acesso
* [x] Definição do REQ_02 — Visão Geral
* [ ] Análise detalhada do REQ_01
* [ ] Análise detalhada do REQ_02
* [ ] Levantamento dos cenários
* [ ] Criação dos casos de teste
* [ ] Execução dos testes
* [ ] Registro das evidências
* [ ] Registro dos bugs
* [ ] Matriz de rastreabilidade

### Próximas etapas

Após concluir a análise dos REQ_01 e REQ_02, os próximos requisitos serão incorporados gradualmente ao projeto:

* REQ_03 — Gestão de Contas
* REQ_04 — Movimentações
* REQ_05 — Contas a Pagar e Receber
* REQ_06 — Baixa de Contas
* REQ_07 — Categorias e Consultas
* REQ_08 — Relatórios e Previsão Financeira

---

# Ferramentas

| Ferramenta          | Utilização                             |
| ------------------- | -------------------------------------- |
| **Microsoft Excel** | Requisitos e casos de teste            |
| **GitHub**          | Versionamento e documentação           |
| **DevTools**        | Apoio à análise da aplicação           |
| **Navegador Web**   | Execução dos testes                    |
| **Jira**            | Registro de defeitos, quando aplicável |

---

# Competências Trabalhadas

Nesta etapa serão trabalhadas principalmente:

* Engenharia de Requisitos;
* Análise de Regras de Negócio;
* Testes Funcionais;
* Testes Manuais;
* Particionamento de Equivalência;
* Análise de Valor Limite;
* Testes Exploratórios;
* Escrita de Casos de Teste;
* Registro de Evidências;
* Análise de Defeitos;
* Documentação Técnica.

---

## Considerações

Este projeto está sendo desenvolvido de forma incremental. A cada requisito analisado, os cenários, casos de teste, evidências e resultados serão acrescentados ao repositório.

A intenção é manter uma documentação fiel ao que foi realmente analisado e executado na aplicação, evitando apresentar como resultado algo que ainda não foi testado.

**Projeto de portfólio — QA / Testes Manuais**

**Domínio:** Gestão Financeira Pessoal
**Plataforma:** Web
**Requisitos atuais:** REQ_01 e REQ_02

