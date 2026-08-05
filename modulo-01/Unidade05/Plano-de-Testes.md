# Plano de Testes — Sistema Bancário

## 1. Introdução

Este documento apresenta um plano de testes resumido para um sistema bancário. O objetivo é definir como as funcionalidades principais serão testadas antes da entrega do sistema.

O plano considera que:

* As principais funcionalidades já foram definidas;
* Existe um prazo de entrega estabelecido;
* O time responsável pelos testes é reduzido;
* Existe um ambiente de testes disponível;
* O sistema será utilizado por usuários reais;
* O sistema trabalha com informações pessoais e financeiras.

Devido a essas características, serão priorizados os testes relacionados à **segurança, transações financeiras, autenticação, saldo e integridade dos dados**.

---

# 2. Escopo de Testes

O escopo define quais funcionalidades serão testadas.

## Funcionalidades incluídas

### Login e Autenticação

Serão realizados testes para verificar:

* Login com usuário e senha válidos;
* Login com senha incorreta;
* Login com usuário inexistente;
* Campos obrigatórios;
* Bloqueio ou tratamento de tentativas inválidas;
* Logout;
* Controle de sessão.

### Cadastro de Usuário

Serão testados:

* Cadastro com dados válidos;
* Cadastro com dados incompletos;
* Validação dos campos;
* Cadastro de CPF já existente;
* Alteração de dados cadastrais;
* Tratamento de informações inválidas.

### Consulta de Saldo

Serão verificados:

* Exibição correta do saldo;
* Atualização do saldo após uma operação;
* Saldo após transferência;
* Tratamento de conta sem saldo;
* Consistência dos valores apresentados.

### Extrato Bancário

Serão testados:

* Exibição das transações;
* Data das operações;
* Valores de entrada e saída;
* Atualização do extrato;
* Organização das informações;
* Consistência entre extrato e saldo.

### Transferências

Será dada prioridade a essa funcionalidade.

Serão testados:

* Transferência válida;
* Transferência com saldo insuficiente;
* Transferência com valor inválido;
* Transferência para conta inexistente;
* Transferência para a própria conta;
* Transferência com valor zero;
* Transferência duplicada;
* Atualização do saldo após transferência;
* Registro da transferência no extrato.

### Segurança e Controle de Acesso

Serão realizados testes para verificar:

* Usuário não autenticado não consegue acessar a conta;
* Usuário não consegue acessar dados de outro cliente;
* Controle de permissões;
* Encerramento de sessão;
* Proteção das informações financeiras.

---

# 3. Tipos de Teste Aplicados

Considerando o prazo e o time reduzido, os seguintes testes serão priorizados.

| Tipo de Teste            | Prioridade  | Objetivo                                                         |
| ------------------------ | ----------- | ---------------------------------------------------------------- |
| Teste Funcional          | Alta        | Verificar se as funcionalidades funcionam conforme os requisitos |
| Teste de Integração      | Alta        | Verificar comunicação entre as partes do sistema                 |
| Teste de Segurança       | Muito Alta  | Garantir proteção dos dados e contas                             |
| Teste de Regressão       | Alta        | Garantir que alterações não geraram novos erros                  |
| Teste de Usabilidade     | Média       | Verificar facilidade de utilização                               |
| Teste de Performance     | Média       | Verificar comportamento do sistema sob carga                     |
| Teste de Compatibilidade | Baixa/Média | Verificar funcionamento em diferentes navegadores e dispositivos |

## Testes Manuais

Serão utilizados principalmente para:

* Testes exploratórios;
* Testes de usabilidade;
* Fluxos completos;
* Funcionalidades novas;
* Validação de mensagens de erro;
* Verificação de comportamentos inesperados.

## Testes Automatizados

Serão utilizados principalmente para:

* Login;
* Validação de campos;
* Regras de negócio;
* API;
* Transferências;
* Testes de regressão;
* Funcionalidades repetitivas.

---

# 4. Critérios de Entrada

Os testes poderão começar quando as seguintes condições forem atendidas:

* Funcionalidades principais implementadas;
* Requisitos definidos;
* Ambiente de testes disponível;
* Banco de dados de testes configurado;
* Usuários e contas fictícias disponíveis;
* Casos de teste definidos;
* Sistema disponível para execução;
* Principais dependências funcionando.

### Exemplo

Para iniciar os testes de transferência, é necessário possuir:

```text
Usuário A
    ↓
Conta bancária de teste
    ↓
Saldo disponível
    ↓
Usuário B
    ↓
Conta bancária de destino
```

---

# 5. Critérios de Saída

Os testes poderão ser considerados concluídos quando:

* As funcionalidades críticas tiverem sido testadas;
* Os casos de teste prioritários forem executados;
* Os principais problemas encontrados forem corrigidos;
* Os testes de regressão forem realizados;
* Não existirem bugs críticos ou bloqueadores conhecidos;
* As funcionalidades de login, saldo, extrato e transferência estiverem funcionando corretamente;
* Os requisitos principais forem atendidos;
* A equipe responsável aprovar a versão para entrega.

### Critério principal

> O sistema não deverá ser liberado caso exista um erro crítico que possa causar perda financeira, acesso indevido ou exposição de dados dos usuários.

---

# 6. Ambiente de Testes

Os testes serão realizados em um ambiente separado do ambiente de produção.

## Características

* Sistema bancário em ambiente de homologação/testes;
* Banco de dados específico para testes;
* Dados fictícios;
* Contas bancárias simuladas;
* Usuários fictícios;
* Navegadores atualizados;
* Computadores e dispositivos disponíveis para a equipe;
* Ferramentas de gerenciamento de código e testes.

### Dados de teste

Não serão utilizados dados reais de clientes.

Serão utilizados dados fictícios, por exemplo:

```text
Nome: João da Silva
CPF: 111.111.111-11
Conta: 00001-1
Saldo: R$ 1.000,00
```

Os dados devem ser utilizados apenas no ambiente de testes.

---

# 7. Recursos e Responsabilidades

Como o projeto possui um time reduzido, serão consideradas duas pessoas envolvidas diretamente nos testes.

## QA / Testador

Responsabilidades:

* Criar os casos de teste;
* Executar os testes;
* Registrar bugs;
* Priorizar problemas;
* Realizar testes de regressão;
* Validar correções;
* Elaborar o relatório final dos testes.

## Desenvolvedor

Responsabilidades:

* Implementar as funcionalidades;
* Corrigir os bugs encontrados;
* Realizar testes unitários;
* Auxiliar nos testes automatizados;
* Apoiar o QA na investigação de problemas.

### Responsabilidade compartilhada

Ambos devem trabalhar em conjunto para:

* Identificar riscos;
* Definir prioridades;
* Validar correções;
* Garantir a qualidade da versão final.

---

# 8. Cronograma Básico

O cronograma será organizado de acordo com o prazo de entrega do projeto.

| Etapa | Atividade                  | Momento                                |
| ----- | -------------------------- | -------------------------------------- |
| 1     | Análise dos requisitos     | Início do projeto                      |
| 2     | Criação dos casos de teste | Após definição dos requisitos          |
| 3     | Testes unitários           | Durante o desenvolvimento              |
| 4     | Testes funcionais          | Após implementação das funcionalidades |
| 5     | Testes de integração       | Após integração dos módulos            |
| 6     | Testes de segurança        | Durante e após implementação           |
| 7     | Testes de regressão        | Após cada correção relevante           |
| 8     | Testes de usabilidade      | Próximo à entrega                      |
| 9     | Testes finais              | Antes da entrega                       |
| 10    | Relatório final            | Final do ciclo de testes               |

### Estratégia do cronograma

Os testes serão realizados **continuamente durante o desenvolvimento**.

Não será recomendado deixar todos os testes para o final do projeto, pois isso poderia gerar muitos problemas próximos ao prazo de entrega.

A cada funcionalidade concluída:

```text
Desenvolvimento
      ↓
Teste
      ↓
Bug encontrado?
   ↙       ↘
 Sim       Não
  ↓         ↓
Correção   Aprovação
  ↓
Reteste
  ↓
Regressão
```

---

# 9. Riscos e Contingências

## Risco 1 — Time reduzido

**Problema:** Poucas pessoas disponíveis para executar todos os testes.

**Contingência:**

Priorizar os testes das funcionalidades de maior risco:

1. Transferências;
2. Saldo;
3. Login;
4. Segurança;
5. Extrato.

---

## Risco 2 — Prazo curto

**Problema:** O tempo disponível pode não ser suficiente para executar todos os testes.

**Contingência:**

Utilizar uma estratégia baseada em risco, dando prioridade às funcionalidades críticas.

---

## Risco 3 — Bugs críticos próximos da entrega

**Problema:** Um problema grave pode ser encontrado próximo à data de entrega.

**Contingência:**

* Priorizar a correção do bug;
* Realizar novo teste;
* Executar testes de regressão;
* Adiar funcionalidades não essenciais se necessário;
* Não liberar o sistema caso o problema envolva risco financeiro ou de segurança.

---

## Risco 4 — Alterações frequentes no sistema

**Problema:** Novas funcionalidades e correções podem gerar novos erros.

**Contingência:**

Realizar testes de regressão após alterações relevantes.

---

## Risco 5 — Falhas no ambiente de testes

**Problema:** O ambiente pode ficar indisponível ou apresentar problemas.

**Contingência:**

* Informar o responsável pelo ambiente;
* Registrar o problema;
* Utilizar ambiente alternativo quando disponível;
* Retomar os testes assim que o ambiente estiver normalizado.

---

## Risco 6 — Problemas de segurança

**Problema:** Um usuário pode conseguir acessar dados de outro usuário ou realizar operações indevidas.

**Contingência:**

Realizar testes de autenticação, autorização e controle de acesso antes da entrega.

---

# 10. Matriz de Prioridades

| Funcionalidade   | Risco       | Prioridade |
| ---------------- | ----------- | ---------- |
| Transferência    | Muito alto  | 🔴 Crítica |
| Segurança        | Muito alto  | 🔴 Crítica |
| Login            | Alto        | 🔴 Alta    |
| Saldo            | Muito alto  | 🔴 Crítica |
| Extrato          | Alto        | 🟠 Alta    |
| Cadastro         | Médio       | 🟡 Média   |
| Usabilidade      | Médio       | 🟡 Média   |
| Compatibilidade  | Baixo/Médio | 🟢 Baixa   |
| Detalhes visuais | Baixo       | 🟢 Baixa   |

---

# 11. Exemplo de Caso de Teste

## CT-001 — Transferência com saldo suficiente

**Objetivo:** Verificar se o usuário consegue realizar uma transferência quando possui saldo suficiente.

### Pré-condições

* Usuário autenticado;
* Conta ativa;
* Saldo de R$ 1.000,00;
* Conta de destino válida.

### Passos

1. Acessar a conta;
2. Acessar a opção "Transferência";
3. Informar a conta de destino;
4. Informar o valor de R$ 100,00;
5. Confirmar a operação.

### Resultado esperado

A transferência deve ser realizada com sucesso.

O sistema deve:

* Debitar R$ 100,00 da conta de origem;
* Creditar R$ 100,00 na conta de destino;
* Atualizar o saldo;
* Registrar a operação no extrato;
* Exibir uma confirmação da transferência.

---

# 12. Critérios para Aprovação do Sistema

O sistema será considerado apto para entrega quando:

* [x] Login funcionando corretamente;
* [x] Cadastro funcionando corretamente;
* [x] Saldo sendo apresentado corretamente;
* [x] Extrato apresentando as operações corretamente;
* [x] Transferências funcionando corretamente;
* [x] Validação de saldo insuficiente funcionando;
* [x] Controle de acesso funcionando;
* [x] Dados dos usuários protegidos;
* [x] Testes de regressão realizados;
* [x] Bugs críticos corrigidos;
* [x] Requisitos principais atendidos.

---

# 13. Conclusão

O plano de testes foi desenvolvido considerando as características de um sistema bancário, que possui funcionalidades críticas e trabalha com informações financeiras e pessoais.

Como o projeto possui **prazo definido, equipe reduzida e ambiente de testes disponível**, os testes serão priorizados de acordo com os riscos.

As funcionalidades relacionadas a **transferências, saldo, login, segurança e extrato** terão maior prioridade.

Os testes serão executados de maneira contínua durante o desenvolvimento, utilizando testes manuais e automatizados sempre que possível.

A principal finalidade do plano é garantir que o sistema seja entregue com qualidade, segurança e confiabilidade, reduzindo os riscos de falhas que possam prejudicar os usuários ou causar problemas financeiros.
