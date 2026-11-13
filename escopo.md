ESCOPO DO PROJETO — DEBTFLOW

Versão: 1.0
Nome: DebtFlow
Tipo: Sistema web responsivo e PWA
Tecnologia principal: Java 17 e Spring Boot 4
Banco de dados: PostgreSQL

1. Visão geral

O DebtFlow será um sistema de gerenciamento de dívidas pessoais, desenvolvido para permitir que o usuário organize suas obrigações financeiras, acompanhe parcelas, registre pagamentos e controle valores compartilhados com outras pessoas.

O sistema terá acesso por navegador e poderá ser instalado como aplicativo no celular por meio de PWA (Progressive Web App).

Embora seja inicialmente destinado a um único usuário, deverá permitir acesso seguro a partir de diferentes dispositivos.

2. Objetivo geral

Desenvolver uma aplicação que centralize o controle de dívidas, parcelas, juros, encargos, pagamentos e contribuições de terceiros, oferecendo uma visão clara da situação financeira do usuário.

3. Objetivos específicos

Cadastrar e gerenciar dívidas.

Controlar parcelas e vencimentos.

Registrar pagamentos totais e parciais.

Controlar juros e encargos adicionais.

Cadastrar pessoas que participam do pagamento de uma dívida.

Calcular a participação financeira de cada pessoa.

Controlar valores esperados e valores efetivamente recebidos.

Identificar parcelas vencidas e próximas do vencimento.

Disponibilizar um painel financeiro.

Enviar notificações ao celular.

Permitir acesso por diferentes dispositivos.

4. Escopo funcional

4.1. Gestão de dívidas

O sistema deverá permitir:

Cadastrar uma dívida.

Informar descrição, credor, valor original e data de contratação.

Informar observações.

Consultar dívidas cadastradas.

Editar informações.

Excluir dívidas, respeitando a integridade do histórico financeiro.

Consultar o saldo devedor atualizado.

4.2. Gestão de parcelas

Cada dívida poderá possuir uma ou mais parcelas.

Informações de cada parcela:

Número da parcela.

Valor original.

Data de vencimento.

Juros.

Encargos adicionais.

Valor atualizado.

Saldo pendente.

Situação: pendente, parcial, paga ou vencida.

4.3. Gestão de pagamentos

O sistema permitirá:

Registrar pagamento total.

Registrar pagamento parcial.

Informar data do pagamento.

Informar valor pago.

Consultar histórico de pagamentos.

Identificar quanto já foi pago.

Calcular o saldo restante.

Os pagamentos deverão ser registrados como movimentações independentes, preservando o histórico.

4.4. Gestão de participantes

Uma dívida poderá ter pessoas que contribuem para o pagamento.

O sistema permitirá:

Cadastrar participantes.

Associar participantes às dívidas.

Definir a participação de cada pessoa.

Consultar a responsabilidade financeira individual.

4.5. Divisão de valores

Serão disponibilizadas três modalidades:

Divisão igualitária: o valor é dividido igualmente entre os participantes.

Divisão percentual: cada participante possui um percentual de participação.

Valor personalizado: cada participante possui um valor definido manualmente.

O sistema deverá validar a consistência dos valores e percentuais.

4.6. Controle de contribuições

O sistema deverá diferenciar:

Valor esperado de cada participante.

Valor efetivamente recebido.

Data em que a contribuição foi recebida.

Saldo de contribuição pendente.

Uma contribuição esperada não deverá ser considerada dinheiro recebido até que seja registrada como efetivamente recebida.

4.7. Juros e encargos

O sistema deverá permitir registrar juros e encargos adicionais vinculados às dívidas ou parcelas.

Os valores deverão ser apresentados separadamente do principal, permitindo visualizar:

Valor original.

Total de juros.

Total de encargos.

Valor atualizado.

Saldo devedor.

As regras de cálculo deverão ser definidas antes da implementação dessa funcionalidade.

4.8. Dashboard

O painel principal deverá apresentar:

Total das dívidas.

Saldo devedor total.

Total já pago.

Parcelas próximas do vencimento.

Parcelas vencidas.

Valores de juros e encargos.

Participação financeira do usuário.

Valores esperados de terceiros.

Valores efetivamente recebidos.

4.9. Notificações

O sistema deverá enviar notificações para o celular sobre:

Parcelas próximas do vencimento.

Parcelas vencidas.

Lembretes de pagamento.

A implementação utilizará Web Push e Service Worker, com suporte a múltiplos dispositivos.

4.10. Acesso e segurança

O sistema deverá possuir:

Cadastro de uma conta pessoal.

Autenticação por usuário e senha.

Senhas armazenadas com hash seguro.

Proteção das rotas.

Comunicação HTTPS em produção.

Armazenamento seguro de credenciais e configurações.

Rotina de backup do banco de dados.

5. Requisitos não funcionais

Interface responsiva para computador e celular.

Aplicação instalável como PWA.

Persistência dos dados em PostgreSQL.

Código organizado em camadas.

Validação dos dados recebidos pela API.

Tratamento centralizado de erros.

Histórico financeiro consistente.

Segurança das informações.

Facilidade de manutenção e evolução.

6. Arquitetura proposta

A primeira versão será construída como uma aplicação monolítica, separada em camadas.

Backend

Java 17.

Spring Boot 4.

Spring Web MVC.

Spring Validation.

Spring Data JPA.

Spring Security.

Hibernate.

Maven.

Banco de dados

PostgreSQL.

Flyway para versionamento das migrações.

Relacionamentos e integridade referencial.

Frontend

HTML.

CSS.

JavaScript.

Bootstrap.

Service Worker.

Manifest PWA.

Testes

JUnit 5.

Spring Boot Test.

Mockito.

Testes de integração.

Infraestrutura

Git e GitHub.

WSL e VS Code no desenvolvimento.

Hospedagem com HTTPS.

Backup do banco de dados.

7. Modelo inicial de entidades

Entidade

Responsabilidade

User

Conta de acesso

Debt

Cadastro da dívida

Installment

Parcelas da dívida

Payment

Pagamentos realizados ao credor

Participant

Pessoas envolvidas

Contribution

Valores esperados e recebidos dos participantes

PushSubscription

Dispositivos cadastrados para notificações

Relacionamentos principais

User possui várias Debt.

Debt possui várias Installment.

Installment possui vários Payment.

Debt pode possuir vários Participant.

Participant pode estar associado a várias Debt.

Contribution relaciona participante, dívida e parcela.

User pode possuir várias PushSubscription.

8. Dependências técnicas

Dependências iniciais do projeto

Spring Web: criação de endpoints e comunicação HTTP.

Spring Validation: validação de entradas.

Spring Data JPA: persistência e consultas.

PostgreSQL Driver: conexão com PostgreSQL.

Flyway: controle de versões do banco de dados.

Spring Security: autenticação e autorização.

Spring Boot Test: testes.

Mockito: simulação de dependências nos testes.

Dependências de desenvolvimento

Java 17.

Maven Wrapper.

Git.

GitHub.

VS Code.

WSL.

Dependências futuras

Biblioteca de Web Push para notificações.

Configuração de HTTPS.

Serviço de hospedagem.

Banco PostgreSQL em ambiente de produção.

As versões das bibliotecas deverão ser compatíveis com Spring Boot 4 e Java 17. Sempre que possível, as versões gerenciadas pelo Spring Boot serão mantidas pelo Maven.

9. Etapas de desenvolvimento

Fase 1 — Fundação do projeto

Gerar projeto Spring Boot.

Configurar estrutura de pacotes.

Configurar Maven.

Criar repositório Git.

Executar aplicação inicial.

Fase 2 — Banco de dados

Instalar e configurar PostgreSQL.

Configurar conexão.

Integrar Spring Data JPA.

Configurar Flyway.

Criar primeira migração.

Fase 3 — Gestão de dívidas

Criar entidade Debt.

Criar DTOs.

Criar Repository.

Criar Service.

Criar Controller.

Implementar operações CRUD.

Criar testes.

Fase 4 — Parcelas e pagamentos

Criar entidade Installment.

Criar entidade Payment.

Implementar pagamentos parciais e totais.

Calcular saldos.

Preservar histórico.

Criar testes.

Fase 5 — Participantes e contribuições

Criar entidade Participant.

Criar entidade Contribution.

Implementar divisão igualitária.

Implementar divisão percentual.

Implementar valores personalizados.

Controlar valores esperados e recebidos.

Fase 6 — Juros e encargos

Definir regras de cálculo.

Implementar juros.

Implementar encargos.

Atualizar saldos.

Criar testes financeiros.

Fase 7 — Dashboard

Criar indicadores.

Exibir parcelas próximas do vencimento.

Exibir parcelas vencidas.

Exibir saldos e contribuições.

Fase 8 — Segurança

Implementar autenticação.

Configurar Spring Security.

Proteger endpoints.

Garantir isolamento dos dados do usuário.

Fase 9 — PWA e notificações

Criar Manifest.

Configurar Service Worker.

Implementar instalação.

Implementar Web Push.

Cadastrar dispositivos.

Implementar agendamento de notificações.

Fase 10 — Implantação

Preparar ambiente de produção.

Configurar banco de dados.

Configurar HTTPS.

Configurar variáveis de ambiente.

Publicar aplicação.

Configurar backups.

Executar testes finais.

10. Fora do escopo inicial

Não serão implementados inicialmente:

Aplicativo Android ou iOS nativo.

Integração bancária automática.

Open Finance.

Pagamento automático de boletos.

Integração com instituições financeiras.

Gestão financeira de múltiplos usuários independentes.

Relatórios contábeis avançados.

11. Critérios de aceite

O projeto será considerado funcional quando:

For possível cadastrar e consultar dívidas.

For possível cadastrar parcelas.

For possível registrar pagamentos parciais e totais.

Os saldos forem calculados corretamente.

For possível cadastrar participantes.

As três modalidades de divisão funcionarem.

Valores esperados e recebidos forem diferenciados.

Juros e encargos forem apresentados separadamente.

O dashboard apresentar informações consistentes.

O usuário conseguir acessar o sistema com segurança.

A aplicação puder ser instalada como PWA.

As notificações forem entregues nos dispositivos cadastrados.