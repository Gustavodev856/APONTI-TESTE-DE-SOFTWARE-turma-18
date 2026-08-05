# Estratégia de Testes — Sistema Bancário

## 1. Objetivo da Estratégia

O principal objetivo da estratégia de testes é garantir que o sistema bancário seja **seguro, confiável e funcional**, principalmente nas operações que envolvem dados dos usuários e movimentações financeiras.

Como o sistema será utilizado por usuários reais, os testes devem priorizar funcionalidades críticas, evitando erros que possam causar **perdas financeiras, acesso indevido a contas ou exposição de dados pessoais**.

### O que é mais importante garantir?

Os testes devem garantir principalmente:

* Login e autenticação funcionando corretamente;
* Acesso seguro às contas dos usuários;
* Visualização correta do saldo e extrato;
* Transferências sendo realizadas corretamente;
* Valores sendo debitados e creditados corretamente;
* Impedir operações sem saldo suficiente;
* Proteção dos dados dos usuários;
* Impedir que um usuário acesse informações de outra conta;
* Sistema funcionando corretamente em diferentes situações;
* Correções não causando novos problemas.

### Aspectos que merecem maior atenção

As funcionalidades que envolvem **dinheiro e segurança** terão maior prioridade.

A ordem de atenção será:

1. Login e autenticação;
2. Transferências;
3. Saldo e extrato;
4. Segurança e controle de acesso;
5. Cadastro e atualização de dados;
6. Funcionalidades secundárias e aspectos visuais.

---

# 2. Tipos de Teste Prioritários

Devido ao contexto do projeto, serão priorizados os testes relacionados a **risco financeiro, segurança e experiência do usuário**.

## Testes Funcionais

Serão utilizados para verificar se cada funcionalidade está funcionando de acordo com os requisitos.

### Exemplos:

* Realizar login com dados válidos;
* Bloquear login com senha incorreta;
* Consultar saldo;
* Consultar extrato;
* Realizar transferência;
* Impedir transferência com saldo insuficiente;
* Validar valores de transferência;
* Realizar logout.

**Prioridade: Alta**

Os testes funcionais possuem alta prioridade porque falhas podem impedir o usuário de utilizar o sistema ou causar problemas financeiros.

---

## Testes de Integração

Serão utilizados para verificar se os diferentes componentes do sistema trabalham corretamente juntos.

Exemplo de fluxo:

```text
Login → Conta → Saldo → Transferência → Extrato
```

**Prioridade: Alta**

Uma falha na comunicação entre essas partes pode gerar informações incorretas ou operações incompletas.

---

## Testes de Segurança

Serão realizados para verificar se os dados e as contas dos usuários estão protegidos.

### Exemplos:

* Tentar acessar uma conta sem autenticação;
* Tentar acessar dados de outro usuário;
* Verificar controle de permissões;
* Testar sessões expiradas;
* Validar senhas e credenciais;
* Verificar exposição de informações sensíveis.

**Prioridade: Muito alta**

O sistema bancário trabalha com informações pessoais e financeiras, portanto, problemas de segurança podem gerar consequências graves.

---

## Testes de Regressão

Serão realizados após correções e implementação de novas funcionalidades.

Exemplo:

> Uma alteração na funcionalidade de transferência não deve fazer com que o saldo ou o extrato deixe de funcionar.

**Prioridade: Alta**

O sistema está em desenvolvimento ativo e receberá novas versões constantemente. Portanto, é importante garantir que alterações não causem novos problemas.

---

## Testes de Usabilidade

Serão utilizados para verificar se o usuário consegue utilizar o sistema de maneira simples e intuitiva.

### Exemplos:

* Facilidade para encontrar o saldo;
* Facilidade para realizar uma transferência;
* Clareza das mensagens de erro;
* Facilidade para consultar o extrato.

**Prioridade: Média/Alta**

Como o sistema será utilizado por usuários reais, a experiência de utilização também é importante.

---

## Testes de Menor Prioridade

Devido ao prazo de entrega e ao time reduzido, alguns testes terão menor prioridade inicialmente:

* Testes visuais muito detalhados;
* Testes de compatibilidade com uma grande quantidade de dispositivos;
* Testes exploratórios extensivos em funcionalidades de baixo risco;
* Testes de performance extremamente avançados.

Esses testes não serão ignorados, mas serão realizados conforme o tempo e os recursos disponíveis.

---

# 3. Abordagens de Teste

A estratégia utilizará uma combinação de **testes manuais e automatizados**.

## Testes Manuais

Serão realizados manualmente principalmente:

* Testes exploratórios;
* Testes de usabilidade;
* Avaliação da interface;
* Fluxos completos realizados por um usuário;
* Testes de mensagens de erro;
* Cenários novos ou que ainda estão em desenvolvimento;
* Validação de comportamentos inesperados.

### Exemplo

O testador realiza:

```text
Login
  ↓
Consulta do saldo
  ↓
Realização de transferência
  ↓
Consulta do saldo novamente
  ↓
Verificação do extrato
```

O objetivo é verificar se o fluxo completo funciona corretamente.

---

## Testes Automatizados

Poderão ser automatizados principalmente:

* Login;
* Cadastro;
* Validação de campos;
* Consulta de saldo;
* Transferências;
* Regras de negócio;
* Testes de API;
* Testes de regressão;
* Testes repetitivos.

Por exemplo, um teste automatizado pode verificar diversas vezes se uma transferência de **R$ 100,00** é corretamente descontada da conta de origem e adicionada à conta de destino.

---

## Por que utilizar os dois?

A combinação foi escolhida porque testes manuais e automatizados possuem objetivos diferentes.

### Automação

* Maior velocidade;
* Repetição dos testes;
* Redução do trabalho manual;
* Execução frequente;
* Maior facilidade nos testes de regressão.

### Testes manuais

* Exploração do sistema;
* Avaliação da experiência do usuário;
* Testes de usabilidade;
* Identificação de comportamentos inesperados;
* Validação de funcionalidades novas.

Portanto:

> **Automação = velocidade, repetição e regressão.**

> **Manual = exploração, usabilidade e validação humana.**

---

# 4. Riscos e Mitigação

Por ser um sistema bancário, existem diversos riscos importantes.

| Risco                                   | Impacto    | Mitigação                            |
| --------------------------------------- | ---------- | ------------------------------------ |
| Saldo apresentado incorretamente        | Muito alto | Testes funcionais e de integração    |
| Transferência com valor incorreto       | Muito alto | Testes funcionais e automatizados    |
| Transferência duplicada                 | Muito alto | Testes de integração e regressão     |
| Usuário acessar conta de outra pessoa   | Muito alto | Testes de segurança                  |
| Falha no login                          | Alto       | Testes funcionais                    |
| Sistema indisponível                    | Alto       | Testes de performance e estabilidade |
| Dados pessoais expostos                 | Muito alto | Testes de segurança                  |
| Alteração gerar novos erros             | Alto       | Testes de regressão                  |
| Usuário não entender uma funcionalidade | Médio/Alto | Testes de usabilidade                |
| Erros em dispositivos/navegadores       | Médio      | Testes de compatibilidade            |

## Como a estratégia reduz os riscos?

A estratégia reduz os riscos concentrando os esforços nas funcionalidades que podem causar maior impacto.

Se houver pouco tempo disponível para testar todo o sistema, será mais importante testar:

```text
Transferência
     +
Saldo
     +
Login
     +
Segurança
```

do que gastar grande parte do tempo testando detalhes visuais de uma funcionalidade secundária.

Essa abordagem permite utilizar melhor os recursos disponíveis e priorizar aquilo que representa maior risco para o usuário e para o negócio.

---

# 5. Recursos e Cronograma

Como o cenário apresenta um **time reduzido**, serão consideradas **2 pessoas envolvidas nos testes**.

## Equipe

### 1. QA/Testador

Responsável por:

* Criar casos de teste;
* Executar testes manuais;
* Registrar bugs;
* Realizar testes de regressão;
* Validar correções;
* Auxiliar na definição das prioridades.

### 2. Desenvolvedor

Responsável por:

* Corrigir os problemas encontrados;
* Auxiliar na automação;
* Executar testes técnicos;
* Realizar testes unitários;
* Apoiar o QA durante a validação.

---

# 6. Cronograma

Os testes acontecerão durante todo o desenvolvimento do sistema.

## Etapa 1 — Planejamento

Antes da implementação das funcionalidades:

* Identificação dos requisitos;
* Identificação dos riscos;
* Definição dos casos de teste;
* Priorização das funcionalidades críticas.

---

## Etapa 2 — Desenvolvimento

Durante o desenvolvimento:

* Testes unitários;
* Testes de API;
* Testes funcionais iniciais;
* Validação das regras de negócio.

---

## Etapa 3 — Integração

Após a implementação das principais funcionalidades:

* Testes de integração;
* Testes de segurança;
* Testes de fluxo completo;
* Testes de regressão.

---

## Etapa 4 — Validação

Antes da entrega:

* Testes de aceitação;
* Testes de usabilidade;
* Testes de segurança;
* Testes de performance;
* Correção dos problemas encontrados.

---

## Etapa 5 — Pós-Entrega

Após a disponibilização do sistema:

* Monitoramento de erros;
* Testes das correções;
* Testes de regressão;
* Validação de novas funcionalidades.

---

# 7. Testes Contínuos ou Concentrados?

Os testes serão realizados de maneira **contínua**, mas existirão momentos de maior concentração.

Durante o desenvolvimento, cada funcionalidade deverá ser testada assim que estiver disponível.

Após correções, serão realizados testes de regressão para garantir que o problema foi resolvido e que a alteração não afetou outras funcionalidades.

Antes da entrega final, haverá uma etapa de testes mais intensa, concentrando os esforços nas funcionalidades críticas.

---

# 8. Resumo da Estratégia

A estratégia de testes do sistema bancário será baseada principalmente em **risco e prioridade**.

Como o sistema trabalha com dinheiro, informações pessoais e usuários reais, os testes de **segurança, funcionalidades financeiras, integração e regressão** terão maior prioridade.

A equipe utilizará testes manuais para explorar o sistema e avaliar sua usabilidade, enquanto os testes automatizados serão utilizados principalmente para funcionalidades repetitivas e testes de regressão.

Os testes serão realizados de forma contínua durante o desenvolvimento, com uma etapa mais intensa antes da entrega.

O objetivo final é garantir que o sistema seja:

* **Seguro**
* **Confiável**
* **Funcional**
* **Estável**
* **Adequado para usuários reais**

Dessa forma, a estratégia busca reduzir principalmente os riscos relacionados a **transações financeiras, acesso indevido, inconsistência de dados e falhas nas funcionalidades críticas**.
