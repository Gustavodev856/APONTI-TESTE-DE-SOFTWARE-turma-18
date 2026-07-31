# Atividade Avaliativa — Teste de Performance

## Análise de um Relatório de Teste de Performance

### Cenário analisado

Foi realizado um teste de performance em um sistema web com o objetivo de avaliar seu comportamento sob uma quantidade elevada de usuários simultâneos.

Durante o teste, foram observadas as seguintes métricas:

* **Usuários simultâneos:** 500
* **Tempo médio de resposta:** 4,8 segundos
* **Percentual de erros:** 6%
* **CPU do servidor:** 92% de utilização
* **Memória RAM:** 88% de utilização
* **Tempo máximo de resposta:** 12 segundos
* **Requisições por segundo:** apresentou redução conforme o número de usuários aumentou.

---

## 1. O sistema pode ser considerado aprovado?

**Não. O sistema não pode ser considerado aprovado no cenário analisado.**

Apesar de conseguir atender aos usuários, os resultados demonstram problemas significativos de performance.

O tempo médio de resposta de **4,8 segundos** é elevado para uma aplicação web, principalmente quando existem operações que deveriam responder em poucos segundos ou menos.

Além disso, o percentual de **6% de erros** indica que uma quantidade considerável de requisições não foi processada corretamente.

A utilização de **92% de CPU** e **88% de memória** também demonstra que os recursos do servidor estão próximos do limite, podendo causar degradação ainda maior caso a quantidade de usuários aumente.

Portanto, o sistema precisa passar por otimizações antes de ser considerado aprovado para esse nível de utilização.

---

## 2. Quais métricas indicam problemas de performance?

As principais métricas que indicam problemas são:

### Tempo de resposta

O tempo médio de resposta foi de **4,8 segundos**, enquanto o tempo máximo chegou a **12 segundos**.

Isso indica que alguns usuários estão enfrentando uma espera muito elevada para receber uma resposta do sistema.

### Taxa de erros

O teste apresentou **6% de erros**.

Esse percentual é preocupante porque significa que aproximadamente 6 a cada 100 requisições podem estar apresentando algum tipo de falha.

### Utilização da CPU

A CPU chegou a **92% de utilização**.

Esse valor indica que o processamento do servidor está próximo da capacidade máxima e pode representar um gargalo.

### Utilização de memória

A memória chegou a **88% de utilização**.

Caso o consumo continue aumentando, pode ocorrer falta de memória, uso excessivo de swap ou até indisponibilidade da aplicação.

### Throughput

A quantidade de requisições processadas por segundo apresentou redução conforme o número de usuários aumentou.

Isso pode indicar que o sistema está chegando ao seu limite de processamento.

---

## 3. Quais possíveis gargalos podem existir?

Com base nos resultados, alguns possíveis gargalos são:

* **Processamento elevado no servidor**, devido ao uso de CPU acima de 90%;
* **Consumo elevado de memória RAM**;
* **Consultas ao banco de dados pouco otimizadas**;
* Falta de **índices adequados no banco de dados**;
* Código ou operações que exigem muito processamento;
* Falta de **cache** para informações acessadas frequentemente;
* Configuração inadequada do servidor;
* Limitação de recursos de infraestrutura;
* Problemas de rede ou latência;
* Falta de escalabilidade da aplicação;
* Número insuficiente de conexões disponíveis no banco de dados;
* Ausência de mecanismos de balanceamento de carga.

É importante realizar uma análise mais detalhada utilizando ferramentas de monitoramento e profiling para identificar exatamente onde o tempo está sendo consumido.

---

## 4. Esse cenário se aproxima mais de Carga, Stress ou Capacidade?

O cenário se aproxima principalmente de um **Teste de Carga**.

O teste foi realizado utilizando **500 usuários simultâneos**, com o objetivo de verificar como o sistema se comporta diante de uma quantidade elevada de usuários em uma situação esperada de utilização.

### Teste de Carga

Avalia o comportamento do sistema sob uma carga de usuários ou requisições esperada ou próxima da realidade.

### Teste de Stress

Busca ultrapassar os limites normais do sistema para descobrir em que ponto ele começa a falhar ou apresentar comportamento inadequado.

### Teste de Capacidade

Tem como objetivo descobrir a quantidade máxima de usuários, requisições ou operações que o sistema consegue suportar mantendo os requisitos de performance estabelecidos.

**Conclusão:** neste cenário, o teste é principalmente de **Carga**, pois busca verificar o comportamento da aplicação diante de uma quantidade significativa de usuários simultâneos.

---

## 5. O que você recomendaria ao time técnico?

Eu recomendaria que o time técnico realizasse uma investigação detalhada dos principais pontos de gargalo antes da liberação do sistema para produção.

As seguintes ações poderiam ser realizadas:

### Otimização do banco de dados

* Analisar as consultas SQL;
* Criar índices quando necessário;
* Identificar consultas que demoram muito;
* Evitar consultas desnecessárias;
* Avaliar o uso de paginação.

### Otimização da aplicação

* Identificar funções que consomem muitos recursos;
* Reduzir processamento desnecessário;
* Melhorar o gerenciamento de memória;
* Utilizar técnicas de cache quando apropriado.

### Melhorias na infraestrutura

* Avaliar o aumento de CPU e memória;
* Verificar configurações do servidor;
* Considerar escalabilidade horizontal ou vertical;
* Avaliar a utilização de balanceadores de carga.

### Monitoramento

Implementar ferramentas de monitoramento para acompanhar:

* CPU;
* Memória;
* Disco;
* Rede;
* Banco de dados;
* Tempo de resposta;
* Taxa de erros;
* Quantidade de requisições por segundo.

### Novos testes

Após realizar as otimizações, seria recomendado executar novamente os testes de performance.

Também seria interessante realizar:

* Teste de carga;
* Teste de stress;
* Teste de capacidade;
* Teste de endurance, para verificar o comportamento do sistema durante um período prolongado.

---

## Conclusão

Com base nos resultados apresentados, **o sistema não deve ser considerado aprovado** para o cenário avaliado.

Os principais problemas identificados foram o **tempo elevado de resposta**, a **taxa de erros de 6%**, o **alto consumo de CPU** e a **utilização elevada de memória**.

Os possíveis gargalos podem estar relacionados à aplicação, ao banco de dados ou à infraestrutura utilizada.

O cenário analisado se aproxima principalmente de um **Teste de Carga**, pois avalia o comportamento do sistema diante de uma quantidade significativa de usuários simultâneos.

Antes da aprovação, recomenda-se realizar otimizações na aplicação, banco de dados e infraestrutura e, posteriormente, repetir os testes para verificar se os problemas foram solucionados.
