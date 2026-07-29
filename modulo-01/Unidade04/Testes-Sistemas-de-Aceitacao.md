# ATIVIDADE AVALIATIVA — TESTES DE SISTEMA E DE ACEITAÇÃO

## Etapa 1 — Compreensão do Cenário

### Cenário

Um sistema bancário permite que usuários realizem login, acessem sua conta e visualizem seu saldo atual.

### 1. Funcionalidades envolvidas

As principais funcionalidades envolvidas são:

- Acesso à tela de login;
- Preenchimento do usuário ou CPF;
- Preenchimento da senha;
- Validação das credenciais;
- Autenticação do usuário;
- Acesso à área da conta bancária;
- Consulta e exibição do saldo atual;
- Tratamento de login com dados inválidos.

### 2. Fluxo principal

O fluxo principal esperado é:

1. O usuário acessa o sistema bancário;
2. O sistema apresenta a tela de login;
3. O usuário informa suas credenciais válidas;
4. O usuário seleciona a opção "Entrar";
5. O sistema valida as credenciais;
6. O sistema permite o acesso à conta;
7. O sistema apresenta o saldo atual do usuário.

### 3. Variações de fluxo

Algumas variações possíveis são:

- Usuário informa senha incorreta;
- Usuário informa usuário ou CPF incorreto;
- Usuário deixa algum campo obrigatório vazio;
- Usuário acessa a conta corretamente, mas o saldo não é apresentado;
- Usuário consegue realizar o login, porém ocorre um erro ao carregar a tela da conta.

---

# Etapa 2 — Testes de Sistema

## Objetivo

Os testes de sistema têm como objetivo verificar se o sistema funciona corretamente como um todo, considerando a integração entre suas telas e funcionalidades.

O foco será verificar o funcionamento do fluxo de login até a visualização do saldo, sem avaliar regras de negócio complexas.

---

## Teste de Sistema 01 — Login e acesso à conta

**ID:** TS-001

**Título:** Realizar login com credenciais válidas e acessar a conta

**Pré-condições:**

- O sistema bancário está disponível;
- O usuário possui cadastro;
- O usuário possui credenciais válidas;
- O usuário está na tela de login.

**Passos:**

1. Informar um usuário ou CPF válido;
2. Informar a senha correta;
3. Clicar no botão "Entrar";
4. Aguardar o processamento da autenticação.

**Resultado esperado:**

O sistema deve validar as credenciais e direcionar o usuário para a área da sua conta bancária.

---

## Teste de Sistema 02 — Acessar conta e visualizar saldo

**ID:** TS-002

**Título:** Visualizar saldo após realizar login

**Pré-condições:**

- O sistema está disponível;
- O usuário possui credenciais válidas;
- O usuário está na tela de login.

**Passos:**

1. Informar usuário ou CPF válido;
2. Informar senha válida;
3. Clicar em "Entrar";
4. Aguardar o carregamento da conta;
5. Localizar a informação de saldo.

**Resultado esperado:**

O sistema deve realizar o login, carregar a área da conta e apresentar o saldo atual do usuário corretamente.

---

## Teste de Sistema 03 — Login com senha inválida

**ID:** TS-003

**Título:** Tentar acessar a conta utilizando senha incorreta

**Pré-condições:**

- O sistema está disponível;
- O usuário possui cadastro;
- O usuário está na tela de login.

**Passos:**

1. Informar um usuário ou CPF válido;
2. Informar uma senha incorreta;
3. Clicar em "Entrar".

**Resultado esperado:**

O sistema deve impedir o acesso à conta e apresentar uma mensagem informando que as credenciais são inválidas.

---

## Teste de Sistema 04 — Acesso sem preencher a senha

**ID:** TS-004

**Título:** Tentar realizar login sem informar a senha

**Pré-condições:**

- O sistema está disponível;
- O usuário está na tela de login.

**Passos:**

1. Informar um usuário ou CPF válido;
2. Deixar o campo de senha vazio;
3. Clicar em "Entrar".

**Resultado esperado:**

O sistema deve impedir o envio do formulário e informar que o preenchimento da senha é obrigatório.

---

# Etapa 3 — Testes de Aceitação

## Objetivo

Os testes de aceitação verificam se o sistema atende às necessidades e expectativas do usuário e do negócio.

Nesse caso, o objetivo é garantir que o usuário consiga entrar em sua conta e consultar seu saldo de forma clara e funcional.

---

## Teste de Aceitação 01 — Usuário consegue consultar seu saldo

**ID:** TA-001

**Título:** Consultar saldo da conta após login

**Pré-condições:**

- O usuário possui uma conta cadastrada;
- O usuário possui credenciais válidas;
- O sistema está disponível.

**Passos:**

1. O usuário acessa o sistema;
2. Informa suas credenciais válidas;
3. Realiza o login;
4. Acessa sua conta;
5. Consulta a área de saldo.

**Resultado esperado:**

O usuário deve conseguir acessar sua conta e visualizar de maneira clara o saldo atual disponível, atendendo à necessidade de consultar sua situação financeira.

---

## Teste de Aceitação 02 — Acesso à conta com credenciais válidas

**ID:** TA-002

**Título:** Usuário consegue acessar sua conta utilizando credenciais válidas

**Pré-condições:**

- O usuário possui uma conta ativa;
- O usuário possui usuário ou CPF e senha válidos;
- O sistema está disponível.

**Passos:**

1. O usuário acessa a página de login;
2. Informa seu usuário ou CPF;
3. Informa sua senha;
4. Seleciona "Entrar".

**Resultado esperado:**

O usuário deve conseguir acessar sua conta com sucesso e visualizar a área principal do sistema bancário.

---

## Teste de Aceitação 03 — Usuário recebe retorno ao informar senha incorreta

**ID:** TA-003

**Título:** Sistema informa ao usuário que a senha está incorreta

**Pré-condições:**

- O usuário possui uma conta cadastrada;
- O sistema está disponível;
- O usuário está na tela de login.

**Passos:**

1. Informar usuário ou CPF válido;
2. Informar uma senha incorreta;
3. Selecionar "Entrar".

**Resultado esperado:**

O sistema deve impedir o acesso e apresentar uma mensagem clara ao usuário, permitindo que ele compreenda que as credenciais informadas não são válidas.

---

## Teste de Aceitação 04 — Usuário é informado sobre campo obrigatório

**ID:** TA-004

**Título:** Sistema informa que a senha deve ser preenchida

**Pré-condições:**

- O sistema está disponível;
- O usuário está na tela de login.

**Passos:**

1. Informar usuário ou CPF válido;
2. Não informar a senha;
3. Selecionar "Entrar".

**Resultado esperado:**

O sistema deve informar claramente que a senha é obrigatória, permitindo que o usuário corrija o preenchimento e tente realizar o acesso novamente.

---

# Etapa 4 — Justificativa e Classificação

## Teste de Sistema 01 — TS-001

### Por que este é um teste de sistema?

É um teste de sistema porque verifica o funcionamento integrado do processo de autenticação. O teste começa na tela de login e termina no acesso à área da conta.

### Objetivo do teste

Verificar se o usuário consegue realizar login utilizando credenciais válidas e acessar sua conta.

### Ponto de vista adotado

O ponto de vista é técnico e funcional, avaliando o comportamento do sistema durante a execução do fluxo.

### Tipo de validação realizada

Validação funcional e de integração entre a tela de login e a área da conta.

---

## Teste de Sistema 02 — TS-002

### Por que este é um teste de sistema?

É um teste de sistema porque verifica a integração entre autenticação, acesso à conta e apresentação do saldo.

### Objetivo do teste

Garantir que, após o login, o sistema carregue corretamente a conta e apresente o saldo.

### Ponto de vista adotado

Ponto de vista técnico e funcional, observando se as funcionalidades do sistema trabalham corretamente em conjunto.

### Tipo de validação realizada

Validação funcional e de integração entre diferentes partes do sistema.

---

## Teste de Sistema 03 — TS-003

### Por que este é um teste de sistema?

É um teste de sistema porque verifica o comportamento do sistema completo diante de uma tentativa de login com credenciais inválidas.

### Objetivo do teste

Garantir que o sistema não permita o acesso quando a senha estiver incorreta.

### Ponto de vista adotado

Ponto de vista funcional, verificando a resposta do sistema para uma situação de erro.

### Tipo de validação realizada

Validação funcional do fluxo alternativo de autenticação.

---

## Teste de Sistema 04 — TS-004

### Por que este é um teste de sistema?

É um teste de sistema porque verifica o comportamento da tela de login quando uma informação necessária não é fornecida.

### Objetivo do teste

Garantir que o sistema reconheça a ausência da senha e não permita o prosseguimento do login.

### Ponto de vista adotado

Ponto de vista funcional e técnico.

### Tipo de validação realizada

Validação funcional e de tratamento de entrada inválida.

---

# Justificativa dos Testes de Aceitação

## Teste de Aceitação 01 — TA-001

### Por que este é um teste de aceitação?

É um teste de aceitação porque verifica uma necessidade real do usuário: conseguir consultar seu saldo após acessar sua conta.

### Objetivo do teste

Confirmar que o sistema entrega ao usuário a informação de saldo de forma acessível.

### Ponto de vista adotado

Ponto de vista do usuário e do negócio.

### Tipo de validação realizada

Validação da entrega de valor ao usuário.

---

## Teste de Aceitação 02 — TA-002

### Por que este é um teste de aceitação?

É um teste de aceitação porque verifica se o usuário consegue utilizar a funcionalidade principal do sistema, que é acessar sua própria conta.

### Objetivo do teste

Garantir que o usuário consiga acessar sua conta utilizando suas credenciais.

### Ponto de vista adotado

Ponto de vista do usuário final.

### Tipo de validação realizada

Validação da experiência e do resultado esperado pelo usuário.

---

## Teste de Aceitação 03 — TA-003

### Por que este é um teste de aceitação?

É um teste de aceitação porque verifica se o sistema fornece ao usuário um retorno compreensível quando ele informa uma senha incorreta.

### Objetivo do teste

Garantir que o usuário compreenda o motivo pelo qual não conseguiu acessar sua conta.

### Ponto de vista adotado

Ponto de vista do usuário.

### Tipo de validação realizada

Validação da clareza do retorno apresentado pelo sistema.

---

## Teste de Aceitação 04 — TA-004

### Por que este é um teste de aceitação?

É um teste de aceitação porque verifica se o sistema orienta adequadamente o usuário quando uma informação obrigatória não foi preenchida.

### Objetivo do teste

Garantir que o usuário saiba como corrigir o preenchimento do formulário.

### Ponto de vista adotado

Ponto de vista do usuário final.

### Tipo de validação realizada

Validação da usabilidade e do atendimento ao comportamento esperado pelo usuário.

---

# Etapa 5 — Revisão por Pares

Para realizar a revisão dos casos de teste de outro aluno, podem ser utilizados os seguintes critérios:

## 1. Clareza

Verificar se:

- O título do teste é fácil de compreender;
- Os passos estão escritos de maneira objetiva;
- O resultado esperado está claro;
- Não existem informações que causem dúvidas.

## 2. Estrutura

Verificar se todos os testes possuem:

- ID;
- Título;
- Pré-condições;
- Passos;
- Resultado esperado.

## 3. Coerência com o tipo de teste

Verificar se o teste realmente corresponde ao tipo escolhido.

### Teste de Sistema

Deve:

- Focar no funcionamento do sistema;
- Verificar funcionalidades;
- Avaliar integração entre telas quando necessário;
- Observar o comportamento do sistema como um todo.

### Teste de Aceitação

Deve:

- Focar na necessidade do usuário;
- Considerar o valor entregue;
- Verificar se o resultado atende à expectativa do negócio;
- Possuir critérios claros de aceitação.

---

## Modelo de Revisão por Pares

**Caso de teste avaliado:** TA-001

**Clareza:**  
Aprovado. Os passos estão descritos de maneira objetiva e o resultado esperado está compreensível.

**Estrutura:**  
Aprovado. O caso apresenta ID, título, pré-condições, passos e resultado esperado.

**Coerência com o tipo de teste:**  
Aprovado. O teste está adequado como teste de aceitação porque verifica se o usuário consegue consultar seu saldo, que é uma necessidade diretamente relacionada ao valor entregue pelo sistema.

**Sugestão de melhoria:**  
Poderia ser especificado que o saldo deve estar visível de forma clara na área principal da conta.

---

# Conclusão

A atividade permitiu diferenciar os testes de sistema dos testes de aceitação.

Os **testes de sistema** possuem maior foco no funcionamento técnico e funcional da aplicação, verificando se as diferentes funcionalidades e telas trabalham corretamente em conjunto.

Já os **testes de aceitação** possuem foco no usuário e no negócio, verificando se o sistema realmente entrega o resultado esperado e atende à necessidade do usuário.

No cenário apresentado, os testes de sistema verificaram principalmente o fluxo de login, acesso à conta e apresentação do saldo, enquanto os testes de aceitação verificaram se o usuário consegue realizar essas ações e obter o valor esperado da aplicação.