# Requisitos Funcionais --- Orçamento Pessoal

## 1. Objetivo

Este documento apresenta os requisitos funcionais identificados durante
a análise inicial da aplicação web **Orçamento Pessoal**.

Nesta primeira etapa do projeto de QA, o escopo está concentrado em dois
requisitos:

-   **REQ_01 --- Cadastro e Acesso**
-   **REQ_02 --- Visão Geral**

Os requisitos serão utilizados como base para a definição dos cenários,
casos de teste e matriz de rastreabilidade.

------------------------------------------------------------------------

## 2. REQ_01 --- Cadastro e Acesso

### Descrição

O sistema deve permitir que o utilizador realize o cadastro de uma nova
conta informando os dados necessários e, posteriormente, permita o
acesso à aplicação por meio de suas credenciais.

Após o cadastro ou autenticação realizada com sucesso, o utilizador deve
ser direcionado para a área principal da aplicação.

### Objetivo

Garantir que um novo utilizador consiga criar uma conta e que um
utilizador cadastrado consiga autenticar-se e acessar o sistema.

### Funcionalidades relacionadas

-   Acesso à tela de cadastro;
-   Preenchimento dos dados de cadastro;
-   Criação da conta;
-   Acesso à tela de login;
-   Preenchimento das credenciais;
-   Autenticação;
-   Tratamento de credenciais inválidas;
-   Redirecionamento após autenticação.

### Dados identificados para cadastro

De acordo com a documentação disponível da aplicação, o cadastro
utiliza:

-   E-mail;
-   Nome;
-   Senha.

### Critérios funcionais

O sistema deve:

1.  Permitir iniciar o processo de cadastro.
2.  Disponibilizar os campos necessários para criação da conta.
3.  Permitir concluir o cadastro quando os dados informados forem
    aceitos pelo sistema.
4.  Permitir que um utilizador cadastrado realize o login.
5.  Validar as informações fornecidas durante o acesso.
6.  Impedir o acesso quando as credenciais não forem aceitas.
7.  Direcionar o utilizador para a área principal após uma autenticação
    bem-sucedida.

### Validações a serem investigadas

Durante a execução dos testes serão verificadas as regras específicas de
validação da aplicação, incluindo:

-   Campos obrigatórios;
-   Formato do e-mail;
-   Tamanho e critérios da senha;
-   Dados inválidos;
-   Credenciais incorretas;
-   Tentativa de cadastro com dados já existentes;
-   Mensagens apresentadas ao utilizador.

> **Observação:** os critérios específicos que ainda não foram
> confirmados na aplicação não são considerados regras definitivas neste
> documento. Eles serão validados durante os testes.

### Riscos

-   Impedir o cadastro de novos utilizadores;
-   Impedir o acesso de utilizadores cadastrados;
-   Permitir autenticação com dados incorretos;
-   Apresentar mensagens de validação inadequadas;
-   Direcionar o utilizador para uma área incorreta após o login.

### Prioridade

**Alta**

------------------------------------------------------------------------

## 3. REQ_02 --- Visão Geral

### Descrição

Após o acesso, o sistema deve apresentar uma visão geral das informações
financeiras disponíveis para o utilizador.

A funcionalidade será analisada considerando a apresentação e a
consistência das informações exibidas na área inicial da aplicação.

### Objetivo

Verificar se o utilizador consegue visualizar de forma correta as
principais informações financeiras disponibilizadas pelo sistema após
realizar o acesso.

### Funcionalidades relacionadas

-   Acesso à visão geral;
-   Exibição das informações financeiras;
-   Consulta do saldo;
-   Visualização de receitas;
-   Visualização de despesas;
-   Visualização das contas;
-   Informações relacionadas a vencimentos;
-   Atualização das informações após alterações.

### Critérios funcionais

O sistema deve:

1.  Apresentar a visão geral após o acesso do utilizador.
2.  Exibir as informações financeiras disponíveis na área inicial.
3.  Apresentar os valores de acordo com os dados registrados no sistema.
4.  Permitir que o utilizador consulte as informações apresentadas.
5.  Atualizar as informações quando houver alterações que impactem os
    dados exibidos.
6.  Manter consistência entre os valores apresentados na visão geral e
    os registros financeiros existentes.

### Informações a serem verificadas

Durante os testes serão analisados, conforme disponíveis na aplicação:

-   Saldo;
-   Receitas;
-   Despesas;
-   Contas;
-   Vencimentos;
-   Outros indicadores ou informações financeiras apresentados na tela.

### Riscos

-   Apresentação de valores incorretos;
-   Informações desatualizadas;
-   Divergência entre a visão geral e os lançamentos realizados;
-   Falha na atualização dos valores;
-   Informações importantes não serem apresentadas corretamente.

### Prioridade

**Alta**

------------------------------------------------------------------------

## 4. Relação entre os Requisitos

Os dois requisitos possuem uma relação direta dentro do fluxo inicial da
aplicação.

``` text
REQ_01 — Cadastro e Acesso
              │
              ▼
       Utilizador autenticado
              │
              ▼
REQ_02 — Visão Geral
              │
              ▼
    Informações financeiras
```

O **REQ_01** permite que o utilizador entre na aplicação, enquanto o
**REQ_02** representa a primeira área de consulta das informações
financeiras após a autenticação.

Por isso, uma falha no REQ_01 pode impedir a validação do REQ_02.

------------------------------------------------------------------------

## 5. Critérios de Aceitação

### REQ_01

-   [ ] O utilizador consegue acessar o cadastro.
-   [ ] Os campos necessários para o cadastro estão disponíveis.
-   [ ] Um cadastro válido pode ser concluído.
-   [ ] Um utilizador cadastrado consegue realizar login.
-   [ ] Credenciais inválidas não permitem acesso.
-   [ ] As mensagens de validação são apresentadas adequadamente.
-   [ ] O utilizador é direcionado para a área principal após o acesso.

### REQ_02

-   [ ] A visão geral é apresentada após o login.
-   [ ] As principais informações financeiras são exibidas.
-   [ ] Os valores apresentados são consistentes com os dados
    registrados.
-   [ ] As informações são atualizadas quando necessário.
-   [ ] Não são identificadas divergências entre os dados apresentados e
    os registros financeiros.

------------------------------------------------------------------------

## 6. Técnicas de Teste Aplicáveis

Para a validação destes requisitos serão utilizadas, quando aplicáveis:

### Particionamento de Equivalência

Será utilizado para dividir entradas em grupos de dados com
comportamento esperado semelhante.

Exemplos:

-   E-mail válido;
-   E-mail inválido;
-   Campo vazio;
-   Credenciais válidas;
-   Credenciais inválidas.

### Análise de Valor Limite --- BVA

Será aplicada aos campos que apresentarem limites definidos durante a
análise da aplicação.

### Testes Exploratórios

Serão utilizados para investigar comportamentos que não estejam
previstos inicialmente nos casos de teste.

### Análise de Risco

Os cenários serão priorizados de acordo com o impacto que uma falha pode
causar ao acesso do utilizador ou à confiabilidade das informações
financeiras.

------------------------------------------------------------------------

## 7. Rastreabilidade

Os requisitos deste documento serão utilizados como referência para os
próximos artefatos do projeto.

  Requisito   Casos de Teste   Evidências    Bugs
  ----------- ---------------- ------------- ---------------
  REQ_01      A definir        A registrar   A identificar
  REQ_02      A definir        A registrar   A identificar

A matriz será atualizada conforme os casos de teste forem criados e
executados.

------------------------------------------------------------------------

## 8. Status

  Requisito                      Status
  ------------------------------ ------------
  REQ_01 --- Cadastro e Acesso   Em análise
  REQ_02 --- Visão Geral         Em análise

Os requisitos serão considerados concluídos após a análise prática,
criação dos casos de teste e execução dos cenários correspondentes.

------------------------------------------------------------------------

## 9. Fonte

**Sistema analisado:** Orçamento Pessoal\
**Plataforma:** Web\
**Tipo de análise:** Testes Manuais\
**Fonte principal:** Aplicação Orçamento Pessoal e documentação oficial
disponível.

**Website:** https://www.orcamentopessoal.net/
