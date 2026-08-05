# Atividade Avaliativa — Testes Manuais e Automatizados

## Sistema Bancário

## 1. Introdução

A escolha entre realizar um teste de forma **manual ou automatizada** deve considerar fatores como frequência de execução, custo, estabilidade da funcionalidade, complexidade e objetivo do teste.

Em um sistema bancário, essa decisão é importante porque existem funcionalidades críticas, como login, consulta de saldo e transferências, que precisam ser testadas frequentemente e com precisão.

Considerando um **time reduzido**, prazo definido e desenvolvimento contínuo, os testes repetitivos e estáveis serão priorizados para automação, enquanto testes exploratórios e de usabilidade serão realizados manualmente.

---

# 2. Cenários de Teste

## CT-001 — Login com usuário e senha válidos

**Abordagem:** Automatizado

**Justificativa:**

O login é uma funcionalidade utilizada frequentemente e possui comportamento relativamente estável. O teste pode ser executado várias vezes após alterações no sistema.

A automação permite verificar rapidamente se o login continua funcionando e reduz o tempo gasto com testes repetitivos.

**Tipo:** Automatizado

---

## CT-002 — Login com senha incorreta

**Abordagem:** Automatizado

**Justificativa:**

É um cenário simples, repetitivo e com resultado esperado bem definido.

O sistema deve impedir o acesso e apresentar uma mensagem adequada.

Como pode ser executado várias vezes em diferentes ciclos de desenvolvimento, é um bom candidato à automação.

**Tipo:** Automatizado

---

## CT-003 — Cadastro de novo usuário

**Abordagem:** Automatizado

**Justificativa:**

O cadastro possui regras de validação que podem ser testadas automaticamente.

Podem ser verificadas situações como:

* Campos obrigatórios;
* CPF inválido;
* E-mail inválido;
* CPF já cadastrado;
* Dados válidos.

Como existem muitos cenários semelhantes, a automação ajuda a reduzir o tempo de execução.

**Tipo:** Automatizado

---

## CT-004 — Consulta de saldo

**Abordagem:** Automatizado

**Justificativa:**

A consulta de saldo possui um resultado objetivo e pode ser verificada automaticamente.

Além disso, deve ser testada após diversas operações, como transferências e pagamentos.

Por ser uma funcionalidade crítica e frequentemente utilizada, a automação facilita os testes de regressão.

**Tipo:** Automatizado

---

## CT-005 — Transferência com saldo suficiente

**Abordagem:** Automatizado

**Justificativa:**

A transferência é uma das funcionalidades mais críticas do sistema bancário.

Por envolver regras de negócio importantes, deve ser testada frequentemente.

A automação pode verificar:

```text
Saldo inicial
     ↓
Transferência
     ↓
Saldo final
     ↓
Extrato atualizado
```

Dessa forma, é possível verificar automaticamente se os valores foram corretamente debitados e registrados.

**Tipo:** Automatizado

**Prioridade:** Muito alta

---

## CT-006 — Transferência com saldo insuficiente

**Abordagem:** Automatizado

**Justificativa:**

É uma regra de negócio objetiva.

O sistema deve impedir a transferência quando o usuário não possui saldo suficiente.

Como esse cenário pode ser executado várias vezes e possui um resultado esperado claro, a automação é adequada.

**Tipo:** Automatizado

**Prioridade:** Muito alta

---

## CT-007 — Transferência para conta inexistente

**Abordagem:** Automatizado

**Justificativa:**

O cenário possui regras claras e pode ser executado repetidamente.

O sistema deve identificar que a conta de destino não existe e impedir a operação.

A automação permite verificar rapidamente essa regra após alterações no sistema.

**Tipo:** Automatizado

---

## CT-008 — Verificar extrato após transferência

**Abordagem:** Automatizado

**Justificativa:**

O teste possui um resultado esperado objetivo.

Após realizar uma transferência, o sistema deve registrar corretamente:

* Data;
* Valor;
* Tipo de operação;
* Conta de destino;
* Saldo atualizado.

Como essa validação pode ser repetida diversas vezes, a automação é recomendada.

**Tipo:** Automatizado

---

## CT-009 — Usuário tentando acessar conta de outro usuário

**Abordagem:** Automatizado

**Justificativa:**

Esse teste verifica uma regra de segurança crítica.

O sistema deve garantir que um usuário autenticado não consiga acessar informações pertencentes a outra conta.

Por ser um teste importante e que deve ser repetido após alterações no sistema, pode ser automatizado.

**Tipo:** Automatizado

**Prioridade:** Muito alta

---

## CT-010 — Expiração da sessão do usuário

**Abordagem:** Automatizado

**Justificativa:**

O comportamento esperado é objetivo: após determinado período ou condição, a sessão deve ser encerrada e o usuário deve ser direcionado novamente para autenticação.

Por ser uma regra de segurança que deve permanecer funcionando durante as atualizações, a automação é adequada.

**Tipo:** Automatizado

---

## CT-011 — Teste de usabilidade da tela de transferência

**Abordagem:** Manual

**Justificativa:**

Esse teste depende da percepção do usuário.

O objetivo é avaliar se a tela é fácil de entender, se os campos estão claros e se o processo de transferência é intuitivo.

Esses aspectos são difíceis de avaliar apenas com automação.

**Tipo:** Manual

---

## CT-012 — Avaliação das mensagens de erro

**Abordagem:** Manual

**Justificativa:**

Apesar de algumas mensagens poderem ser verificadas automaticamente, a avaliação da qualidade da mensagem é mais adequada manualmente.

O testador poderá verificar se a mensagem:

* É clara;
* É compreensível;
* Informa o problema corretamente;
* Orienta o usuário sobre como resolver o problema.

**Tipo:** Manual

---

## CT-013 — Teste exploratório do sistema

**Abordagem:** Manual

**Justificativa:**

Testes exploratórios dependem da análise humana e da capacidade do testador de encontrar comportamentos inesperados.

O testador pode utilizar o sistema livremente, combinando diferentes ações e observando comportamentos que não foram previstos nos casos de teste.

**Tipo:** Manual

---

## CT-014 — Verificar facilidade de navegação

**Abordagem:** Manual

**Justificativa:**

Esse teste tem como objetivo avaliar a experiência do usuário.

O testador deve verificar se é fácil encontrar:

* Saldo;
* Extrato;
* Transferências;
* Perfil;
* Logout;
* Outras funcionalidades.

Como envolve percepção e experiência, o teste manual é mais adequado.

**Tipo:** Manual

---

## CT-015 — Teste de regressão após correção

**Abordagem:** Automatizado

**Justificativa:**

Testes de regressão precisam ser executados frequentemente após correções e novas funcionalidades.

A automação permite executar rapidamente diversos testes para verificar se alterações recentes não quebraram funcionalidades existentes.

**Tipo:** Automatizado

**Prioridade:** Alta

---

# 3. Resumo dos Cenários

| ID     | Cenário                      | Abordagem    | Justificativa principal       |
| ------ | ---------------------------- | ------------ | ----------------------------- |
| CT-001 | Login válido                 | Automatizado | Repetitivo e estável          |
| CT-002 | Login inválido               | Automatizado | Regra objetiva                |
| CT-003 | Cadastro                     | Automatizado | Muitas validações repetitivas |
| CT-004 | Consulta de saldo            | Automatizado | Crítico e repetitivo          |
| CT-005 | Transferência válida         | Automatizado | Regra crítica e repetitiva    |
| CT-006 | Saldo insuficiente           | Automatizado | Regra objetiva                |
| CT-007 | Conta inexistente            | Automatizado | Regra objetiva                |
| CT-008 | Extrato após transferência   | Automatizado | Validação repetitiva          |
| CT-009 | Acesso indevido              | Automatizado | Segurança crítica             |
| CT-010 | Expiração de sessão          | Automatizado | Regra de segurança            |
| CT-011 | Usabilidade da transferência | Manual       | Avaliação humana              |
| CT-012 | Mensagens de erro            | Manual       | Clareza depende do usuário    |
| CT-013 | Teste exploratório           | Manual       | Necessita análise humana      |
| CT-014 | Navegação                    | Manual       | Experiência do usuário        |
| CT-015 | Regressão                    | Automatizado | Alta frequência de execução   |

---

# 4. Distribuição dos Testes

Considerando os 15 cenários analisados:

### Automatizados

**10 cenários**

* Login;
* Cadastro;
* Saldo;
* Transferências;
* Extrato;
* Segurança;
* Sessão;
* Regressão.

### Manuais

**5 cenários**

* Usabilidade;
* Mensagens;
* Exploração;
* Navegação;
* Experiência do usuário.

A maior quantidade de testes automatizados ocorre porque o sistema possui funcionalidades críticas que precisam ser verificadas frequentemente.

---

# 5. Critérios Utilizados para a Decisão

A decisão entre teste manual e automatizado foi baseada nos seguintes critérios:

| Critério                 | Manual | Automatizado |
| ------------------------ | ------ | ------------ |
| Repetição frequente      | ❌      | ✅            |
| Resultado objetivo       | 🟡     | ✅            |
| Teste exploratório       | ✅      | ❌            |
| Usabilidade              | ✅      | ❌            |
| Regras de negócio        | 🟡     | ✅            |
| Testes de regressão      | ❌      | ✅            |
| Avaliação da experiência | ✅      | ❌            |
| Segurança repetitiva     | 🟡     | ✅            |
| Funcionalidade estável   | 🟡     | ✅            |
| Funcionalidade nova      | ✅      | 🟡           |

---

# 6. Conclusão

Para o sistema bancário, a melhor abordagem é utilizar uma **combinação de testes manuais e automatizados**.

Os testes automatizados serão utilizados principalmente em funcionalidades **estáveis, repetitivas e críticas**, como login, saldo, transferências, extrato, segurança e regressão.

Os testes manuais serão utilizados principalmente em situações que exigem **análise humana**, como testes exploratórios, usabilidade, navegação e avaliação das mensagens apresentadas ao usuário.

Essa combinação permite aproveitar melhor os recursos do time reduzido, diminuir o custo de execução dos testes repetitivos e, ao mesmo tempo, manter a capacidade de identificar problemas que dependem da experiência e análise humana.

Portanto:

> **Testes automatizados são priorizados quando existe repetição, estabilidade e resultado objetivo.**

> **Testes manuais são priorizados quando é necessária exploração, percepção humana ou avaliação da experiência do usuário.**
