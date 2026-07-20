# Explorando Workflows Automatizados com AWS Step Functions

Este repositório foi criado para consolidar os aprendizados, anotações e insights adquiridos durante o laboratório prático focado no gerenciamento e orquestração de workflows automatizados utilizando o **AWS Step Functions**.

## Objetivos do Projeto
* Aplicar os conceitos teóricos do AWS Step Functions em um ambiente prático.
* Documentar processos técnicos e arquitetura serverless de forma clara e estruturada.
* Orquestrar microsserviços e funções serverless (como AWS Lambda) de forma integrada.

---

## Conteúdos Aprendidos & Anotações

### 1. Conhecendo o AWS Step Functions
O AWS Step Functions é um orquestrador de fluxos de trabalho visual e *serverless* que facilita a conexão de múltiplos serviços da AWS. Ele resolve o problema de gerenciar a lógica de fluxos complexos diretamente no código das aplicações, centralizando o estado e as transições.
* **Máquinas de Estado (State Machines):** Definem o comportamento do workflow utilizando a linguagem baseada em JSON chamada *Amazon States Language* (ASL).
* **Estados Principais:**
  * `Task`: Executa uma unidade de trabalho (como chamar uma função Lambda).
  * `Choice`: Adiciona ramificações condicionais baseadas em decisões de lógica (if/else).
  * `Parallel`: Executa múltiplos ramos de trabalho simultaneamente.
  * `Wait`: Atrasa a execução por um período específico ou até um horário definido.

### 2. Benefícios e Projeto Modelo
* **Gerenciamento de Estado Automático:** A AWS cuida do progresso de cada etapa, eliminando a necessidade de bancos de dados intermediários para salvar o progresso.
* **Tratamento de Erros Integrado:** Facilidade para configurar políticas de *Retry* (tentar novamente) e *Catch* (capturar exceções) diretamente no fluxo visual.
* **Auditoria Visual:** O console permite rastrear o histórico de execuções com cores que indicam o sucesso (verde), falha (vermelho) ou progresso (azul) de cada nó.

### 3. Validações e Tratamento de Erros
* Implementação de validações lógicas nas transições de dados utilizando caminhos de entrada e saída (`InputPath`, `ResultPath` e `OutputPath`).
* Configuração de desvios condicionais com estados do tipo `Choice` para verificar respostas e rotear o fluxo dinamicamente.

### 4. Criando e Executando Lambda no AWS Step Functions
* Desenvolvimento e publicação de funções **AWS Lambda**.
* Integração direta das Lambdas no Step Functions mapeando os ARNs (Amazon Resource Names) correspondentes como recursos do tipo `Task`.
* Teste prático passando dados de entrada da máquina de estados, processando-os na Lambda e recebendo o retorno para a próxima etapa.

## Tecnologias Utilizadas
* **AWS Step Functions**
* **AWS Lambda**
* **Amazon CloudWatch** (para monitoramento dos logs)
* **GitHub** (para versionamento e documentação)