# DebtFlow

Sistema web responsivo para gerenciamento de dívidas pessoais, parcelas, pagamentos e contribuições compartilhadas.

O DebtFlow está sendo desenvolvido com Java 17 e Spring Boot 4, com o objetivo de centralizar o controle financeiro pessoal em uma aplicação acessível pelo navegador e instalável em dispositivos móveis por meio de PWA (Progressive Web App).

## 1. Objetivo do projeto

Desenvolver uma aplicação para organizar dívidas pessoais, acompanhar vencimentos, registrar pagamentos e controlar valores compartilhados com outras pessoas.

O sistema deverá permitir acesso seguro a partir de diferentes dispositivos, mantendo as informações financeiras centralizadas.

## 2. Funcionalidades previstas

- Cadastro, consulta, edição e exclusão de dívidas.
- Controle de parcelas e datas de vencimento.
- Registro de pagamentos totais e parciais.
- Histórico de pagamentos.
- Controle de juros e encargos adicionais.
- Cadastro de participantes nas dívidas.
- Divisão de valores igualitária, percentual ou personalizada.
- Controle de contribuições esperadas e efetivamente recebidas.
- Dashboard com indicadores financeiros.
- Identificação de parcelas vencidas e próximas do vencimento.
- Autenticação e proteção dos dados.
- Aplicação instalável como PWA.
- Notificações de vencimentos no celular.

## 3. Tecnologias

### Já utilizadas na fundação do projeto

| Tecnologia | Finalidade |
|---|---|
| Java 17 | Linguagem de programação |
| Spring Boot 4 | Framework principal |
| Spring Web | Desenvolvimento de aplicações web e APIs |
| Spring Validation | Validação de dados |
| Maven | Gerenciamento do projeto e dependências |
| Git | Versionamento do código |
| GitHub | Hospedagem do repositório |

### Tecnologias planejadas

| Tecnologia | Finalidade |
|---|---|
| PostgreSQL | Banco de dados |
| Spring Data JPA | Persistência de dados |
| Hibernate | Mapeamento objeto-relacional |
| Flyway | Versionamento do banco de dados |
| Spring Security | Autenticação e segurança |
| HTML, CSS e JavaScript | Interface do usuário |
| Bootstrap | Estilização responsiva |
| JUnit 5 e Mockito | Testes automatizados |
| Service Worker e Web Push | PWA e notificações |

As dependências planejadas serão adicionadas gradualmente durante o desenvolvimento.

## 4. Arquitetura

O projeto utilizará inicialmente uma arquitetura monolítica organizada em camadas.

Estrutura planejada:

```text
debtflow/
├── .mvn/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── debtflow/
│   │   │           ├── config/
│   │   │           ├── controller/
│   │   │           ├── dto/
│   │   │           ├── entity/
│   │   │           ├── exception/
│   │   │           ├── repository/
│   │   │           ├── service/
│   │   │           └── DebtflowApplication.java
│   │   └── resources/
│   │       └── application.properties
│   └── test/
├── .gitignore
├── mvnw
├── mvnw.cmd
├── pom.xml
├── README.md
└── escopo.md
```

A estrutura será ampliada conforme as funcionalidades forem implementadas.

## 5. Modelo inicial de entidades

| Entidade | Responsabilidade |
|---|---|
| User | Conta de acesso |
| Debt | Cadastro das dívidas |
| Installment | Parcelas das dívidas |
| Payment | Pagamentos realizados |
| Participant | Pessoas envolvidas nas dívidas |
| Contribution | Valores esperados e recebidos |
| PushSubscription | Dispositivos cadastrados para notificações |

## 6. Pré-requisitos

Para desenvolver e executar o projeto localmente:

- Java JDK 17.
- Git.
- VS Code ou outra IDE compatível com Java.
- WSL ou ambiente Linux.
- Acesso ao terminal.

O Maven Wrapper já acompanha o projeto, portanto não é necessário instalar o Maven separadamente para executar os comandos do projeto.

## 7. Como executar o projeto

Clone o repositório:

```bash
git clone https://github.com/FilipeVieira1/DebtFlow.git
```

Entre na pasta:

```bash
cd debtflow
```

Dê permissão de execução ao Maven Wrapper, caso necessário:

```bash
chmod +x mvnw
```

Execute a aplicação:

```bash
./mvnw spring-boot:run
```

A aplicação estará disponível em:

```text
http://localhost:8080
```

**Observação:** nesta etapa inicial, a aplicação ainda não possui funcionalidades de negócio ou endpoints implementados.

## 8. Testes

Para executar os testes automatizados:

```bash
./mvnw test
```

## 9. Roadmap de desenvolvimento

| Fase | Descrição | Situação |
|---|---|---|
| 1 | Fundação do projeto e configuração inicial | Em andamento |
| 2 | Configuração do banco de dados | Pendente |
| 3 | Gestão de dívidas | Pendente |
| 4 | Parcelas e pagamentos | Pendente |
| 5 | Participantes e contribuições | Pendente |
| 6 | Juros e encargos | Pendente |
| 7 | Dashboard financeiro | Pendente |
| 8 | Autenticação e segurança | Pendente |
| 9 | PWA e notificações | Pendente |
| 10 | Implantação | Pendente |

O roadmap será atualizado conforme cada etapa for concluída.

## 10. Documentação

O documento [`escopo.md`](escopo.md) contém os requisitos funcionais e não funcionais, arquitetura proposta, dependências, modelo de entidades, critérios de aceite e planejamento detalhado do projeto.

## 11. Status do projeto

O DebtFlow está em fase inicial de desenvolvimento.

A estrutura Spring Boot foi criada, o projeto está versionado com Git e o repositório está hospedado no GitHub.

As funcionalidades serão implementadas gradualmente, com testes e documentação em cada etapa.

---

**DebtFlow** — Organização e controle das suas dívidas.