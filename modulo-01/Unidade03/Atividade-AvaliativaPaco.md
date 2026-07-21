# Atividade Avaliativa – Testes Não Funcionais

## Sistema: PACO (Plataforma de Agendamento de Consultas Online)

### Checklist de Testes Não Funcionais

| Categoria | O que será verificado | Risco associado |
|-----------|------------------------|-----------------|
| **Performance** | Verificar se o sistema suporta múltiplos usuários acessando e realizando agendamentos simultaneamente nos horários de pico. | Lentidão, travamentos ou indisponibilidade do sistema. |
| **Performance** | Verificar o tempo de resposta das funcionalidades de login, consulta de especialidades e agendamento de consultas. | Baixa satisfação dos usuários devido à demora nas respostas. |
| **Performance** | Verificar se as notificações de confirmação são enviadas rapidamente após o agendamento. | Usuário pode não receber a confirmação em tempo hábil. |
| **Segurança** | Verificar se apenas usuários autenticados conseguem realizar agendamentos. | Acesso não autorizado às funcionalidades do sistema. |
| **Segurança** | Verificar se os dados pessoais dos usuários são protegidos durante o armazenamento e a transmissão. | Vazamento de informações pessoais e violação da privacidade. |
| **Segurança** | Verificar se as senhas dos usuários são armazenadas de forma segura (criptografadas). | Comprometimento das contas em caso de invasão ao banco de dados. |
| **Segurança** | Verificar se há proteção contra múltiplas tentativas de login (força bruta). | Invasão de contas por ataques automatizados. |
| **Usabilidade** | Verificar se o processo de agendamento é simples, intuitivo e de fácil compreensão. | Usuários podem cometer erros ou desistir de utilizar a plataforma. |
| **Usabilidade** | Verificar se as mensagens de erro, alerta e confirmação são claras e objetivas. | Confusão durante a utilização do sistema. |
| **Usabilidade** | Verificar se a interface é responsiva e fácil de utilizar em desktop, tablet e celular. | Dificuldade de navegação em determinados dispositivos. |
| **Compatibilidade** | Verificar se o sistema funciona corretamente nos principais navegadores (Google Chrome, Mozilla Firefox, Microsoft Edge e Safari). | Falhas de funcionamento em alguns navegadores. |
| **Compatibilidade** | Verificar se a interface se adapta corretamente a diferentes resoluções de tela. | Problemas de visualização e uso em alguns dispositivos. |
| **Compatibilidade** | Verificar se todas as funcionalidades operam corretamente nos sistemas operacionais Windows, macOS, Android e iOS. | Incompatibilidade que impede o uso da plataforma por alguns usuários. |

## Conclusão

O checklist apresentado contempla os quatro grupos obrigatórios de testes não funcionais:

- **Performance:** desempenho, tempo de resposta e capacidade de suportar múltiplos acessos.
- **Segurança:** autenticação, proteção de dados e prevenção de acessos indevidos.
- **Usabilidade:** facilidade de uso, clareza das informações e experiência do usuário.
- **Compatibilidade:** funcionamento em diferentes navegadores, dispositivos e sistemas operacionais.

Cada item especifica **o que será verificado** e **o risco associado**, conforme solicitado na atividade.
