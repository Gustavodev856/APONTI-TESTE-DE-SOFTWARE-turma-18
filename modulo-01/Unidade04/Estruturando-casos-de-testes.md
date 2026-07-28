# Atividade Avaliativa – Casos de Teste da Tela de Login

## Objetivo

Elaborar casos de teste para validar o comportamento da tela de login, contemplando o **caminho feliz**, cenários de erro e situações alternativas ("fora da caixa"), utilizando linguagem clara, passos bem definidos e resultados esperados observáveis.

---

# Caso de Teste 01

## 1. ID
**CT-001**

## 2. Título
Login com credenciais válidas

## 3. Objetivo
Validar que um usuário com credenciais válidas consegue acessar o sistema.

## 4. Pré-condições
- Usuário cadastrado no sistema.
- Conta ativa.
- Usuário não autenticado.

## 5. Passos
1. Acessar a tela de login.
2. Informar um e-mail válido cadastrado.
3. Informar a senha correta.
4. Clicar no botão **Entrar**.

## 6. Resultado Esperado
- O sistema autentica o usuário com sucesso.
- O usuário é redirecionado para a página inicial (Dashboard).
- As informações do usuário autenticado são exibidas.

---

# Caso de Teste 02

## 1. ID
**CT-002**

## 2. Título
Login com senha incorreta

## 3. Objetivo
Verificar se o sistema impede o acesso quando a senha informada está incorreta.

## 4. Pré-condições
- Usuário cadastrado.
- Conta ativa.

## 5. Passos
1. Acessar a tela de login.
2. Informar um e-mail válido.
3. Informar uma senha incorreta.
4. Clicar no botão **Entrar**.

## 6. Resultado Esperado
- O sistema não realiza a autenticação.
- É exibida a mensagem **"E-mail ou senha inválidos."**
- O usuário permanece na tela de login.

---

# Caso de Teste 03

## 1. ID
**CT-003**

## 2. Título
Login com e-mail não cadastrado

## 3. Objetivo
Validar que usuários inexistentes não conseguem acessar o sistema.

## 4. Pré-condições
- O e-mail informado não existe na base de usuários.

## 5. Passos
1. Acessar a tela de login.
2. Informar um e-mail não cadastrado.
3. Informar qualquer senha.
4. Clicar no botão **Entrar**.

## 6. Resultado Esperado
- O sistema impede o login.
- É apresentada uma mensagem informando que as credenciais são inválidas.

---

# Caso de Teste 04

## 1. ID
**CT-004**

## 2. Título
Tentativa de login com campos obrigatórios vazios

## 3. Objetivo
Validar a obrigatoriedade do preenchimento dos campos.

## 4. Pré-condições
- Tela de login disponível.

## 5. Passos
1. Acessar a tela de login.
2. Não preencher os campos **E-mail** e **Senha**.
3. Clicar no botão **Entrar**.

## 6. Resultado Esperado
- O sistema não envia a solicitação de autenticação.
- São exibidas mensagens indicando que os campos são obrigatórios.

---

# Caso de Teste 05

## 1. ID
**CT-005**

## 2. Título
Login com formato de e-mail inválido

## 3. Objetivo
Verificar a validação do formato do endereço de e-mail.

## 4. Pré-condições
- Tela de login disponível.

## 5. Passos
1. Acessar a tela de login.
2. Informar o e-mail `usuario@`.
3. Informar qualquer senha.
4. Clicar no botão **Entrar**.

## 6. Resultado Esperado
- O sistema identifica o formato inválido.
- É exibida uma mensagem solicitando um endereço de e-mail válido.

---

# Caso de Teste 06

## 1. ID
**CT-006**

## 2. Título
Login com usuário bloqueado

## 3. Objetivo
Validar o comportamento do sistema para contas bloqueadas.

## 4. Pré-condições
- Usuário cadastrado.
- Conta bloqueada.

## 5. Passos
1. Acessar a tela de login.
2. Informar o e-mail do usuário bloqueado.
3. Informar a senha correta.
4. Clicar no botão **Entrar**.

## 6. Resultado Esperado
- O sistema impede a autenticação.
- É apresentada uma mensagem informando que a conta está bloqueada.

---

# Caso de Teste 07

## 1. ID
**CT-007**

## 2. Título
Login com espaços em branco antes e depois do e-mail

## 3. Objetivo
Verificar se o sistema remove espaços extras do e-mail antes da autenticação.

## 4. Pré-condições
- Usuário cadastrado.
- Conta ativa.

## 5. Passos
1. Acessar a tela de login.
2. Informar o e-mail com espaços antes e depois.
3. Informar a senha correta.
4. Clicar no botão **Entrar**.

## 6. Resultado Esperado
- O sistema remove automaticamente os espaços.
- O login é realizado com sucesso.

---

# Caso de Teste 08

## 1. ID
**CT-008**

## 2. Título
Login utilizando e-mail em letras maiúsculas

## 3. Objetivo
Verificar que o sistema não diferencia letras maiúsculas e minúsculas no e-mail.

## 4. Pré-condições
- Usuário cadastrado.
- Conta ativa.

## 5. Passos
1. Acessar a tela de login.
2. Informar o e-mail utilizando apenas letras maiúsculas.
3. Informar a senha correta.
4. Clicar no botão **Entrar**.

## 6. Resultado Esperado
- O sistema reconhece o e-mail corretamente.
- O login é realizado com sucesso.

---

# Caso de Teste 09 (Fora da Caixa)

## 1. ID
**CT-009**

## 2. Título
Bloqueio após múltiplas tentativas de login com senha incorreta

## 3. Objetivo
Validar a política de bloqueio após sucessivas tentativas de autenticação sem sucesso.

## 4. Pré-condições
- Usuário cadastrado.
- Conta ativa.
- Existe política de bloqueio configurada.

## 5. Passos
1. Acessar a tela de login.
2. Informar um e-mail válido.
3. Informar uma senha incorreta.
4. Clicar em **Entrar**.
5. Repetir o processo até atingir o limite permitido.

## 6. Resultado Esperado
- O sistema bloqueia temporariamente a conta ou solicita uma verificação adicional.
- Novas tentativas de login são impedidas até o desbloqueio.

---

# Caso de Teste 10 (Fora da Caixa)

## 1. ID
**CT-010**

## 2. Título
Tentativa de login utilizando caracteres especiais (Teste de Segurança)

## 3. Objetivo
Verificar se o sistema trata corretamente entradas potencialmente maliciosas.

## 4. Pré-condições
- Tela de login disponível.

## 5. Passos
1. Acessar a tela de login.
2. Informar no campo de e-mail ou senha:
   ```text
   ' OR '1'='1
   ```
3. Clicar no botão **Entrar**.

## 6. Resultado Esperado
- O sistema trata a entrada como texto comum.
- Nenhum comando indevido é executado.
- O login é negado.
- É exibida uma mensagem de credenciais inválidas.
- Nenhuma informação interna do sistema é apresentada.

---

# Caso de Teste 11 (Fora da Caixa)

## 1. ID
**CT-011**

## 2. Título
Realizar login utilizando a tecla Enter

## 3. Objetivo
Verificar se a tecla **Enter** executa a mesma ação do botão **Entrar**.

## 4. Pré-condições
- Usuário cadastrado.
- Conta ativa.

## 5. Passos
1. Acessar a tela de login.
2. Informar um e-mail válido.
3. Informar a senha correta.
4. Pressionar a tecla **Enter**.

## 6. Resultado Esperado
- O sistema realiza a autenticação normalmente.
- O usuário é redirecionado para o Dashboard.

---

# Caso de Teste 12 (Fora da Caixa)

## 1. ID
**CT-012**

## 2. Título
Login com senha contendo espaços antes e depois

## 3. Objetivo
Validar o tratamento da senha quando contém espaços extras.

## 4. Pré-condições
- Usuário cadastrado.
- Conta ativa.

## 5. Passos
1. Acessar a tela de login.
2. Informar um e-mail válido.
3. Informar a senha com espaços antes e depois.
4. Clicar no botão **Entrar**.

## 6. Resultado Esperado
- O sistema utiliza a senha exatamente como foi digitada.
- Caso os espaços façam parte da senha cadastrada, o login é realizado.
- Caso contrário, a autenticação é negada.

---

# Considerações Finais

Os casos de teste apresentados contemplam:

- ✅ Caminho feliz (login com sucesso);
- ✅ Validação de credenciais inválidas;
- ✅ Validação de campos obrigatórios;
- ✅ Validação do formato do e-mail;
- ✅ Tratamento de contas bloqueadas;
- ✅ Tratamento de espaços em branco;
- ✅ Validação de e-mail com letras maiúsculas;
- ✅ Política de bloqueio por múltiplas tentativas;
- ✅ Teste básico de segurança contra entradas maliciosas;
- ✅ Cenários alternativos ("fora da caixa"), como autenticação pela tecla **Enter** e comportamento da senha com espaços.

Esses testes seguem uma estrutura padronizada de documentação de QA, com linguagem objetiva, passos separados e resultados esperados claramente observáveis.
