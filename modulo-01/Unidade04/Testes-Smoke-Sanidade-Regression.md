# Atividade Avaliativa – Testes de Software

## Cenário

Uma nova versão de um sistema bancário foi implantada com:

- Correção no processo de login.
- Ajuste na exibição do saldo na tela inicial.
- Inclusão da funcionalidade **PIX**.

---

# Testes de Smoke

**Objetivo:** Verificar rapidamente se as principais funcionalidades do sistema estão funcionando após a implantação.

| Cenário | Justificativa |
|---------|---------------|
| 1. Realizar login com usuário e senha válidos. | O login é essencial para acessar o sistema e sofreu alteração. |
| 2. Verificar se a tela inicial é exibida corretamente. | Confirma que o sistema inicia normalmente após o login. |
| 3. Conferir se o saldo aparece corretamente na tela inicial. | O saldo foi ajustado nesta versão. |
| 4. Acessar a área do PIX. | Verifica se a nova funcionalidade está disponível. |
| 5. Realizar logout. | Garante que o fluxo básico do sistema está funcionando. |

---

# Testes de Sanidade (Sanity)

**Objetivo:** Validar especificamente as funcionalidades alteradas e adicionadas.

| Cenário | Justificativa |
|---------|---------------|
| 1. Efetuar login com credenciais válidas. | Confirma que a correção do login foi aplicada corretamente. |
| 2. Tentar login com senha incorreta. | Verifica se o sistema continua bloqueando acessos inválidos. |
| 3. Validar se o saldo exibido corresponde ao saldo real da conta. | Confirma que o ajuste da tela inicial está correto. |
| 4. Realizar uma transferência PIX com saldo suficiente. | Valida a principal funcionalidade do PIX. |
| 5. Tentar realizar um PIX com saldo insuficiente. | Confirma se as validações e mensagens de erro estão funcionando. |

---

# Testes de Regressão (Regression)

**Objetivo:** Garantir que as alterações realizadas não afetaram funcionalidades já existentes.

| Cenário | Justificativa |
|---------|---------------|
| 1. Consultar extrato bancário. | Verifica que o histórico continua funcionando normalmente. |
| 2. Efetuar uma transferência entre contas (TED/DOC). | Garante que outros tipos de transferência não foram afetados pelo PIX. |
| 3. Realizar pagamento de boleto. | Confirma que pagamentos continuam funcionando. |
| 4. Alterar dados cadastrais do cliente. | Verifica que funcionalidades do perfil permanecem operando corretamente. |
| 5. Encerrar a sessão e realizar um novo login. | Confirma que o gerenciamento da sessão continua funcionando após as alterações. |

---

# Justificativa dos Tipos de Teste

## Smoke Test

É executado logo após a implantação da nova versão para verificar se as funcionalidades essenciais do sistema estão operacionais. Caso algum desses testes falhe, a versão não deve seguir para testes mais detalhados.

---

## Sanity Test

É realizado para validar especificamente as funcionalidades que sofreram alterações, como a correção do login, o ajuste da exibição do saldo e a inclusão da funcionalidade PIX.

---

## Regression Test

É utilizado para garantir que as novas alterações não impactaram funcionalidades que já funcionavam corretamente nas versões anteriores.

---

# Apresentação para a turma

## Smoke

- Login com usuário válido.
- Abertura da tela inicial.
- Exibição do saldo.
- Acesso à área PIX.
- Logout.

**Objetivo:** Confirmar rapidamente que o sistema está utilizável.

---

## Sanidade

- Login válido.
- Login com senha incorreta.
- Conferência do saldo.
- Realizar PIX com sucesso.
- Tentar PIX com saldo insuficiente.

**Objetivo:** Validar as funcionalidades modificadas nesta versão.

---

## Regressão

- Consultar extrato.
- Transferência TED/DOC.
- Pagamento de boleto.
- Alteração cadastral.
- Novo login após logout.

**Objetivo:** Garantir que nenhuma funcionalidade existente foi comprometida pelas alterações realizadas.

---

# Conclusão

- **Smoke Test:** verifica se o sistema está operacional.
- **Sanity Test:** valida as funcionalidades alteradas (Login, Saldo e PIX).
- **Regression Test:** garante que as demais funcionalidades continuam funcionando corretamente após a nova versão.