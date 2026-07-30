# Teste de Sanidade – Transferência via PIX

## Cenário

Após a implantação da nova versão do sistema bancário, foi disponibilizada a funcionalidade de transferência via PIX. O objetivo deste teste é validar se a operação está funcionando corretamente.

---

## Objetivo

Verificar se um cliente consegue realizar uma transferência PIX com sucesso e se o sistema atualiza corretamente o saldo da conta após a operação.

---

## Cenário de Teste

**Título:** Realizar um PIX com saldo suficiente.

### Pré-condições

- O sistema está atualizado para a nova versão.
- O usuário está cadastrado e autenticado no sistema.
- A conta possui saldo suficiente para realizar a transferência.
- Existe uma chave PIX válida para o destinatário.

### Passos

1. Acessar o sistema bancário.
2. Realizar login com usuário e senha válidos.
3. Acessar o menu **PIX**.
4. Informar uma chave PIX válida.
5. Digitar o valor de **R$ 100,00**.
6. Confirmar a transferência.
7. Verificar a mensagem de sucesso.
8. Conferir se o saldo da conta foi atualizado.

### Resultado Esperado

- A transferência PIX deve ser concluída com sucesso.
- O sistema deve exibir uma mensagem de confirmação.
- O comprovante da transação deve ser gerado.
- O saldo da conta deve ser atualizado corretamente.

---

## Justificativa da Escolha

Este cenário foi escolhido porque a funcionalidade **PIX** é uma das operações mais utilizadas pelos clientes de um sistema bancário. Como o objetivo do **Teste de Sanidade** é validar se uma funcionalidade alterada ou recém-implementada está funcionando corretamente, realizar uma transferência PIX permite confirmar rapidamente que o fluxo principal da funcionalidade está operacional.

---

## Por que este é um Teste de Sanidade?

Porque o teste está focado apenas na funcionalidade do **PIX**, verificando se ela funciona conforme esperado após a atualização do sistema. O objetivo não é testar todas as funcionalidades do banco, mas confirmar que essa alteração específica foi implementada corretamente.

---

# Apresentação para a turma

> **"Escolhi apresentar o teste da transferência via PIX porque é uma das funcionalidades mais importantes de um sistema bancário. Neste teste, verificamos se um cliente consegue realizar um PIX utilizando uma chave válida e saldo suficiente. Após a confirmação da transferência, o sistema deve gerar o comprovante e atualizar o saldo da conta. Esse é um Teste de Sanidade porque seu objetivo é validar apenas a funcionalidade que foi alterada ou adicionada, confirmando que ela está funcionando corretamente antes da execução dos demais testes do sistema."**