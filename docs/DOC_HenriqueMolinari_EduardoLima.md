# DOC – FitPass Gym Management
**Alunos:** Henrique Molinari | Eduardo Lima  
**Disciplina:** Engenharia de Software  
**Documento:** Documentação Unificada de Casos de Uso, Diagramas de Caso de Uso e Diagramas de Atividade

---

## Sumário

1. [Diagramas de Caso de Uso](#1-diagramas-de-caso-de-uso)
2. [Documentação dos Casos de Uso](#2-documentação-dos-casos-de-uso)
3. [Diagramas de Atividade](#3-diagramas-de-atividade)

---

## 1. Diagramas de Caso de Uso

Os diagramas abaixo representam os 20 casos de uso identificados para o sistema FitPass Gym Management, organizados em três agrupamentos lógicos.

---

### DUC_01 – Gestão e Acesso

![DUC_01 – FitPass Gestão e Acesso](https://github.com/HenriqueMolinari/ES_aula11032026_fork/blob/main/docs/DUC_01_HenriqueMolinari_EduardoLima.png?raw=true)

**Atores:** Recepcionista, Gerente, Sistema de Catraca (API)

**Casos de uso representados:**
- UC01 – Cadastrar Aluno
- UC02 – Gerenciar Planos
- UC04 – Editar Cadastro Aluno
- UC05 – Verificar Regularidade
- UC09 – Validar Acesso Catraca
- UC17 – Emitir Relatório Gerencial
- UC18 – Relatório Ocupação Aulas
- UC19 – Consultar Histórico Acessos

---

### DUC_02 – Treino e Aulas

![DUC_02 – FitPass Treino e Aulas](https://github.com/HenriqueMolinari/ES_aula11032026_fork/blob/main/docs/DUC_02_HenriqueMolinari_EduardoLima.png?raw=true)

**Atores:** Aluno, Instrutor, Gerente

**Casos de uso representados:**
- UC10 – Agendar Aula
- UC11 – Confirmar Agendamento *(extend de UC10)*
- UC12 – Cancelar Agendamento
- UC13 – Registrar Presença
- UC14 – Registrar Avaliação Física
- UC15 – Notificar Liberação Avaliação *(extend de UC14)*
- UC16 – Consultar Avaliação Física
- UC18 – Relatório Ocupação Aulas

---

### DUC_03 – Financeiro e Core

![DUC_03 – FitPass Financeiro e Core](https://github.com/HenriqueMolinari/ES_aula11032026_fork/blob/main/docs/DUC_03_HenriqueMolinari_EduardoLima.png?raw=true)

**Atores:** Aluno, Recepcionista, Gerente, Usuário

**Casos de uso representados:**
- UC03 – Realizar Login
- UC06 – Registrar Pagamento
- UC07 – Gerar Cobrança Online
- UC08 – Notificar Vencimento
- UC11 – Confirmar Agendamento
- UC15 – Notificar Avaliação
- UC17 – Emitir Relatório Gerencial
- UC20 – Realizar Logout

---

## 2. Documentação dos Casos de Uso

---

### UC01 – Cadastrar Aluno

| Campo | Descrição |
|---|---|
| **Ator principal** | Recepcionista |
| **Objetivo** | Permitir que a recepcionista registre um novo aluno no sistema com seus dados pessoais e plano contratado |
| **Pré-condições** | Recepcionista autenticada no sistema; plano a ser atribuído deve estar ativo |
| **Pós-condições** | Aluno cadastrado com situação "ativo" no sistema; cartão RFID vinculado ao aluno |

**Fluxo Principal:**
1. A recepcionista acessa o módulo de matrículas.
2. O sistema exibe o formulário de cadastro.
3. A recepcionista preenche os dados pessoais, de contato e endereço do aluno.
4. A recepcionista seleciona o plano contratado.
5. O sistema valida os dados informados.
6. O sistema registra o aluno e vincula o cartão RFID.
7. O sistema exibe confirmação de cadastro realizado com sucesso.

**Fluxos Alternativos:**
- **A1 – Dados obrigatórios não preenchidos:** O sistema exibe mensagem de erro indicando os campos ausentes e aguarda a correção.
- **A2 – Plano selecionado está inativo:** O sistema alerta que o plano não está disponível e solicita a seleção de outro.

**Requisitos relacionados:** RF01, RF02
**Requisitos não funcionais:** RNF02, RNF04
**Regras de negócio:** RN06

---

### UC02 – Gerenciar Planos

| Campo | Descrição |
|---|---|
| **Ator principal** | Gerente |
| **Objetivo** | Permitir que o gerente crie, edite, ative ou desative planos oferecidos pela academia |
| **Pré-condições** | Gerente autenticado no sistema |
| **Pós-condições** | Plano criado, alterado ou com status atualizado no sistema |

**Fluxo Principal:**
1. O gerente acessa o módulo de gerenciamento de planos.
2. O sistema exibe a lista de planos cadastrados e seus status.
3. O gerente seleciona a ação desejada: criar, editar, ativar ou desativar.
4. O sistema exibe o formulário correspondente à ação.
5. O gerente preenche ou altera as informações do plano.
6. O sistema valida e salva as alterações.
7. O sistema exibe confirmação da operação realizada.

**Fluxos Alternativos:**
- **A1 – Tentativa de desativar plano com alunos vinculados:** O sistema alerta que existem alunos ativos no plano e solicita confirmação para prosseguir.

**Requisitos relacionados:** RF02
**Requisitos não funcionais:** RNF04, RNF05
**Regras de negócio:** RN06

---

### UC03 – Realizar Login

| Campo | Descrição |
|---|---|
| **Ator principal** | Usuário (Aluno, Recepcionista, Instrutor ou Gerente) |
| **Objetivo** | Permitir que o usuário acesse o sistema autenticando-se com suas credenciais |
| **Pré-condições** | Usuário deve possuir cadastro ativo no sistema |
| **Pós-condições** | Sessão iniciada com sucesso; sistema redireciona o usuário para a tela inicial correspondente ao seu perfil |

**Fluxo Principal:**
1. O usuário acessa a tela de login do sistema.
2. O usuário informa e-mail e senha.
3. O sistema valida as credenciais informadas.
4. O sistema identifica o perfil do usuário (Aluno, Recepcionista, Instrutor ou Gerente).
5. O sistema inicia a sessão e redireciona para a tela inicial do perfil correspondente.

**Fluxos Alternativos:**
- **A1 – Credenciais inválidas:** O sistema exibe mensagem de erro e permite nova tentativa.
- **A2 – Conta bloqueada ou inativa:** O sistema impede o login e orienta o usuário a contatar a recepção.

**Requisitos relacionados:** RF04
**Requisitos não funcionais:** RNF02, RNF03, RNF04
**Regras de negócio:** RN06

---

### UC04 – Editar Cadastro de Aluno

| Campo | Descrição |
|---|---|
| **Ator principal** | Recepcionista |
| **Objetivo** | Permitir a atualização dos dados pessoais, de contato ou de plano de um aluno já cadastrado |
| **Pré-condições** | Recepcionista autenticada no sistema; aluno deve estar cadastrado |
| **Pós-condições** | Dados do aluno atualizados e salvos no sistema |

**Fluxo Principal:**
1. A recepcionista acessa o módulo de matrículas e busca o aluno pelo nome ou CPF.
2. O sistema exibe os dados atuais do aluno.
3. A recepcionista seleciona a opção de edição.
4. O sistema exibe o formulário preenchido com os dados existentes.
5. A recepcionista altera os campos desejados.
6. O sistema valida os dados informados.
7. O sistema salva as alterações e exibe confirmação.

**Fluxos Alternativos:**
- **A1 – Aluno não encontrado:** O sistema informa que o aluno não foi localizado e retorna à tela de busca.
- **A2 – Dados inválidos:** O sistema exibe mensagem de erro indicando os campos com problema e aguarda a correção.

**Requisitos relacionados:** RF01
**Requisitos não funcionais:** RNF02, RNF04
**Regras de negócio:** RN06

---

### UC05 – Verificar Regularidade do Aluno

| Campo | Descrição |
|---|---|
| **Ator principal** | Recepcionista |
| **Objetivo** | Consultar a situação financeira e de cadastro de um aluno para fins de atendimento ou suporte |
| **Pré-condições** | Recepcionista autenticada no sistema; aluno deve estar cadastrado |
| **Pós-condições** | Situação do aluno exibida na tela (regular, inadimplente ou inativo) |

**Fluxo Principal:**
1. A recepcionista acessa o módulo de consulta de alunos.
2. A recepcionista busca o aluno pelo nome ou CPF.
3. O sistema localiza o aluno e exibe seu status atual: regular, inadimplente ou inativo.
4. O sistema exibe também o histórico de pagamentos e a data do próximo vencimento.

**Fluxos Alternativos:**
- **A1 – Aluno não encontrado:** O sistema informa que o aluno não foi localizado e retorna à tela de busca.

**Requisitos relacionados:** RF04
**Requisitos não funcionais:** RNF02, RNF03
**Regras de negócio:** RN01, RN07

---

### UC06 – Registrar Pagamento de Mensalidade

| Campo | Descrição |
|---|---|
| **Ator principal** | Recepcionista |
| **Objetivo** | Registrar o pagamento da mensalidade de um aluno e atualizar sua situação de regularidade |
| **Pré-condições** | Recepcionista autenticada no sistema; aluno deve estar cadastrado |
| **Pós-condições** | Pagamento registrado no histórico do aluno; situação do aluno atualizada para "regular" |

**Fluxo Principal:**
1. A recepcionista busca o aluno pelo nome ou CPF.
2. O sistema exibe os dados do aluno e o valor da mensalidade em aberto.
3. A recepcionista seleciona a forma de pagamento (dinheiro, cartão ou PIX).
4. O sistema registra o pagamento pelo valor integral.
5. O sistema atualiza imediatamente a situação do aluno para "regular".
6. O sistema exibe confirmação do pagamento.

**Fluxos Alternativos:**
- **A1 – Aluno não encontrado:** O sistema informa que o aluno não foi localizado e retorna à tela de busca.
- **A2 – Tentativa de pagamento parcial:** O sistema bloqueia a operação e exibe mensagem informando que apenas pagamento integral é permitido.

**Requisitos relacionados:** RF03, RF04
**Requisitos não funcionais:** RNF02, RNF03
**Regras de negócio:** RN04, RN07

---

### UC07 – Gerar Cobrança Online

| Campo | Descrição |
|---|---|
| **Ator principal** | Aluno |
| **Objetivo** | Gerar boleto ou link de pagamento online para que o aluno quite sua mensalidade de forma remota |
| **Pré-condições** | Aluno cadastrado e ativo no sistema; mensalidade deve estar em aberto |
| **Pós-condições** | Cobrança gerada e enviada ao aluno pelo canal configurado (e-mail ou app) |

**Fluxo Principal:**
1. O sistema identifica os alunos com mensalidade em aberto.
2. O sistema gera o boleto ou o link de pagamento para cada aluno elegível.
3. O sistema envia a cobrança ao aluno pelo canal configurado.
4. O sistema registra a geração da cobrança no histórico do aluno.
5. Após o pagamento confirmado, o sistema atualiza a situação do aluno para "regular".

**Fluxos Alternativos:**
- **A1 – Falha na geração da cobrança:** O sistema registra o erro e agenda nova tentativa de geração.
- **A2 – Pagamento não confirmado até a data de vencimento:** O sistema mantém a situação do aluno como inadimplente e aciona o bloqueio de acesso conforme RN01.

**Requisitos relacionados:** RF03, RF04, RF10
**Requisitos não funcionais:** RNF01, RNF02
**Regras de negócio:** RN01, RN04, RN07

---

### UC08 – Enviar Notificação de Vencimento de Mensalidade

| Campo | Descrição |
|---|---|
| **Ator principal** | Aluno |
| **Objetivo** | Notificar automaticamente o aluno sobre o próximo vencimento de sua mensalidade, a fim de evitar inadimplência |
| **Pré-condições** | Aluno cadastrado e ativo no sistema; data de vencimento da mensalidade deve estar configurada |
| **Pós-condições** | Notificação enviada ao aluno com as informações de vencimento |

**Fluxo Principal:**
1. O sistema verifica diariamente as datas de vencimento das mensalidades.
2. O sistema identifica os alunos com vencimento próximo (conforme regra de antecedência configurada).
3. O sistema gera a notificação com os dados do valor e da data de vencimento.
4. O sistema envia a notificação ao aluno pelo canal configurado (e-mail ou app).
5. O sistema registra o envio da notificação no histórico do aluno.

**Fluxos Alternativos:**
- **A1 – Falha no envio da notificação:** O sistema registra a falha e realiza nova tentativa de envio no ciclo seguinte.

**Requisitos relacionados:** RF10
**Requisitos não funcionais:** RNF01, RNF02
**Regras de negócio:** RN01

---

### UC09 – Validar Acesso pela Catraca

| Campo | Descrição |
|---|---|
| **Ator principal** | Sistema de Catraca (API externa) |
| **Objetivo** | Verificar se o aluno possui autorização para entrar na academia via leitura do cartão RFID |
| **Pré-condições** | Sistema de catraca integrado via API REST; aluno deve possuir cartão RFID vinculado ao seu cadastro |
| **Pós-condições** | Acesso liberado e registrado no histórico do aluno, ou acesso negado com registro da tentativa |

**Fluxo Principal:**
1. O aluno aproxima o cartão RFID da catraca.
2. A catraca envia o código RFID ao sistema via API REST.
3. O sistema identifica o aluno pelo código RFID.
4. O sistema verifica se o aluno está com a mensalidade em dia.
5. O sistema retorna autorização de acesso à catraca.
6. A catraca libera a entrada e o sistema registra o acesso.

**Fluxos Alternativos:**
- **A1 – Mensalidade vencida há mais de 5 dias:** O sistema retorna negação de acesso. A catraca permanece bloqueada.
- **A2 – Cartão RFID não reconhecido:** O sistema retorna erro de identificação. O acesso é negado.

**Requisitos relacionados:** RF04, RF05
**Requisitos não funcionais:** RNF01, RNF03, RNF06
**Regras de negócio:** RN01

---

### UC10 – Agendar Aula

| Campo | Descrição |
|---|---|
| **Ator principal** | Aluno |
| **Objetivo** | Permitir que o aluno reserve uma vaga em uma aula disponível |
| **Pré-condições** | Aluno autenticado no sistema; aluno com situação "regular"; aula deve possuir vagas disponíveis |
| **Pós-condições** | Reserva registrada para o aluno na aula selecionada; notificação de confirmação enviada ao aluno |

**Fluxo Principal:**
1. O aluno acessa o módulo de agendamento.
2. O sistema exibe a lista de aulas disponíveis com horários e vagas.
3. O aluno seleciona a aula desejada.
4. O sistema verifica a disponibilidade de vagas.
5. O sistema registra a reserva do aluno.
6. O sistema envia notificação de confirmação ao aluno.

**Fluxos Alternativos:**
- **A1 – Aula sem vagas disponíveis:** O sistema informa que a capacidade máxima foi atingida e bloqueia o agendamento.
- **A2 – Aluno inadimplente:** O sistema impede o agendamento e orienta o aluno a regularizar a situação.

**Requisitos relacionados:** RF06, RF10
**Requisitos não funcionais:** RNF04
**Regras de negócio:** RN02

---

### UC11 – Confirmar Agendamento de Aula

| Campo | Descrição |
|---|---|
| **Ator principal** | Aluno |
| **Objetivo** | Confirmar automaticamente o agendamento do aluno e enviar notificação de confirmação após a reserva ser registrada |
| **Pré-condições** | Agendamento do aluno realizado com sucesso (UC10); aluno deve possuir canal de notificação configurado |
| **Pós-condições** | Notificação de confirmação enviada ao aluno com os dados da aula agendada |

**Fluxo Principal:**
1. O sistema recebe o registro de novo agendamento (originado pelo UC10).
2. O sistema verifica o canal de notificação do aluno.
3. O sistema gera a mensagem de confirmação com nome da aula, data e horário.
4. O sistema envia a notificação ao aluno.
5. O sistema registra o envio no histórico de notificações do aluno.

**Fluxos Alternativos:**
- **A1 – Falha no envio da notificação:** O sistema registra a falha e realiza nova tentativa de envio.
- **A2 – Canal de notificação não configurado:** O sistema ignora o envio e registra que o aluno não possui canal ativo.

**Requisitos relacionados:** RF06, RF10
**Requisitos não funcionais:** RNF01, RNF03
**Regras de negócio:** RN02

---

### UC12 – Cancelar Agendamento de Aula

| Campo | Descrição |
|---|---|
| **Ator principal** | Aluno |
| **Objetivo** | Permitir que o aluno cancele uma reserva em uma aula previamente agendada |
| **Pré-condições** | Aluno autenticado no sistema; aluno deve possuir agendamento ativo para a aula; cancelamento deve ser realizado com pelo menos 1 hora de antecedência |
| **Pós-condições** | Reserva cancelada; vaga liberada para outros alunos |

**Fluxo Principal:**
1. O aluno acessa seus agendamentos.
2. O sistema lista as aulas reservadas.
3. O aluno seleciona a aula que deseja cancelar.
4. O sistema verifica se o cancelamento respeita o prazo mínimo de 1 hora.
5. O sistema cancela a reserva e libera a vaga.
6. O sistema exibe confirmação do cancelamento.

**Fluxos Alternativos:**
- **A1 – Cancelamento fora do prazo permitido:** O sistema informa que o prazo de cancelamento (1 hora antes) foi encerrado e bloqueia a operação.

**Requisitos relacionados:** RF06
**Requisitos não funcionais:** RNF04
**Regras de negócio:** RN03

---

### UC13 – Registrar Presença em Aula

| Campo | Descrição |
|---|---|
| **Ator principal** | Instrutor |
| **Objetivo** | Registrar a presença dos alunos em uma aula ministrada |
| **Pré-condições** | Instrutor autenticado no sistema; aula deve estar cadastrada e no horário vigente |
| **Pós-condições** | Presença registrada no histórico da aula e do aluno |

**Fluxo Principal:**
1. O instrutor acessa o módulo de aulas do dia.
2. O sistema exibe a lista de aulas e os alunos agendados.
3. O instrutor seleciona a aula correspondente.
4. O sistema exibe a lista de alunos com agendamento confirmado.
5. O instrutor marca a presença de cada aluno.
6. O sistema salva o registro de presença.

**Fluxos Alternativos:**
- **A1 – Aluno presente sem agendamento:** O instrutor pode incluir manualmente o aluno na lista, desde que haja vaga disponível.

**Requisitos relacionados:** RF07
**Requisitos não funcionais:** RNF04
**Regras de negócio:** RN06

---

### UC14 – Registrar Avaliação Física

| Campo | Descrição |
|---|---|
| **Ator principal** | Instrutor |
| **Objetivo** | Registrar os dados de avaliação física de um aluno, como peso, IMC e percentual de gordura |
| **Pré-condições** | Instrutor autenticado no sistema; aluno com situação "ativo" e "regular" |
| **Pós-condições** | Avaliação física registrada e vinculada ao histórico do aluno; notificação enviada ao aluno |

**Fluxo Principal:**
1. O instrutor acessa o módulo de avaliações físicas.
2. O instrutor busca e seleciona o aluno a ser avaliado.
3. O sistema verifica se o aluno está ativo e regular.
4. O instrutor preenche os dados da avaliação (peso, IMC, percentual de gordura etc.).
5. O instrutor pode anexar arquivos complementares, se necessário.
6. O sistema salva a avaliação e notifica o aluno.

**Fluxos Alternativos:**
- **A1 – Aluno inadimplente ou inativo:** O sistema bloqueia o registro e exibe mensagem indicando que o aluno não está elegível para avaliação.

**Requisitos relacionados:** RF08, RF10
**Requisitos não funcionais:** RNF02
**Regras de negócio:** RN05, RN06

---

### UC15 – Notificar Liberação de Avaliação Física

| Campo | Descrição |
|---|---|
| **Ator principal** | Aluno |
| **Objetivo** | Notificar o aluno quando uma nova avaliação física for registrada pelo instrutor e estiver disponível para consulta |
| **Pré-condições** | Avaliação física registrada com sucesso pelo instrutor (UC14); aluno deve possuir canal de notificação configurado |
| **Pós-condições** | Notificação enviada ao aluno informando a disponibilidade da nova avaliação física |

**Fluxo Principal:**
1. O sistema detecta o registro de uma nova avaliação física vinculada ao aluno.
2. O sistema verifica o canal de notificação do aluno.
3. O sistema gera a mensagem de notificação com a data da avaliação.
4. O sistema envia a notificação ao aluno.
5. O sistema registra o envio no histórico de notificações do aluno.

**Fluxos Alternativos:**
- **A1 – Falha no envio:** O sistema registra a falha e agenda nova tentativa de envio.

**Requisitos relacionados:** RF08, RF10
**Requisitos não funcionais:** RNF01, RNF02
**Regras de negócio:** RN05

---

### UC16 – Consultar Avaliação Física

| Campo | Descrição |
|---|---|
| **Ator principal** | Aluno |
| **Objetivo** | Permitir que o aluno visualize os resultados de suas avaliações físicas registradas pelo instrutor |
| **Pré-condições** | Aluno autenticado no sistema; deve existir ao menos uma avaliação física registrada para o aluno |
| **Pós-condições** | Dados da avaliação exibidos ao aluno (peso, IMC, percentual de gordura e histórico) |

**Fluxo Principal:**
1. O aluno acessa o módulo de avaliações físicas.
2. O sistema exibe a lista de avaliações registradas em ordem cronológica.
3. O aluno seleciona a avaliação desejada.
4. O sistema exibe os detalhes completos da avaliação selecionada.
5. O aluno pode visualizar arquivos anexados, se houver.

**Fluxos Alternativos:**
- **A1 – Nenhuma avaliação registrada:** O sistema informa que ainda não há avaliações físicas disponíveis para o aluno.

**Requisitos relacionados:** RF08
**Requisitos não funcionais:** RNF02, RNF04
**Regras de negócio:** RN05

---

### UC17 – Emitir Relatório Gerencial

| Campo | Descrição |
|---|---|
| **Ator principal** | Gerente |
| **Objetivo** | Permitir que o gerente gere relatórios sobre a situação da academia, como inadimplência e alunos ativos |
| **Pré-condições** | Gerente autenticado no sistema |
| **Pós-condições** | Relatório gerado e disponível para visualização ou exportação |

**Fluxo Principal:**
1. O gerente acessa o módulo de relatórios.
2. O sistema exibe os tipos de relatórios disponíveis.
3. O gerente seleciona o tipo de relatório e o período desejado.
4. O sistema processa e gera o relatório solicitado.
5. O gerente visualiza o relatório e pode exportá-lo.

**Fluxos Alternativos:**
- **A1 – Nenhum dado encontrado para o período:** O sistema informa que não há registros para os filtros aplicados.

**Requisitos relacionados:** RF09
**Requisitos não funcionais:** RNF02, RNF05
**Regras de negócio:** RN06

---

### UC18 – Emitir Relatório de Ocupação de Aulas

| Campo | Descrição |
|---|---|
| **Ator principal** | Gerente |
| **Objetivo** | Gerar um relatório com a taxa de ocupação das aulas em um período selecionado, identificando aulas com alta ou baixa adesão |
| **Pré-condições** | Gerente autenticado no sistema; devem existir registros de agendamento e presença no período consultado |
| **Pós-condições** | Relatório de ocupação gerado com os dados de vagas, agendamentos e presenças por aula |

**Fluxo Principal:**
1. O gerente acessa o módulo de relatórios.
2. O gerente seleciona o tipo "Ocupação de Aulas".
3. O gerente define o período de análise desejado.
4. O sistema processa os dados de agendamento e presença das aulas no período.
5. O sistema gera o relatório com percentual de ocupação por aula.
6. O gerente visualiza o relatório e pode exportá-lo.

**Fluxos Alternativos:**
- **A1 – Nenhum dado no período selecionado:** O sistema informa que não há registros para os filtros aplicados.

**Requisitos relacionados:** RF09
**Requisitos não funcionais:** RNF02, RNF05
**Regras de negócio:** RN02, RN06

---

### UC19 – Consultar Histórico de Acessos

| Campo | Descrição |
|---|---|
| **Ator principal** | Gerente |
| **Objetivo** | Permitir que o gerente visualize o histórico de entradas dos alunos na academia para fins de controle e auditoria |
| **Pré-condições** | Gerente autenticado no sistema; devem existir registros de acesso no período consultado |
| **Pós-condições** | Histórico de acessos exibido com data, horário e identificação do aluno |

**Fluxo Principal:**
1. O gerente acessa o módulo de relatórios.
2. O gerente seleciona o tipo "Histórico de Acessos".
3. O gerente define o período e, opcionalmente, filtra por aluno.
4. O sistema consulta os registros de entrada no período informado.
5. O sistema exibe a listagem de acessos com data, horário e nome do aluno.
6. O gerente pode exportar o relatório.

**Fluxos Alternativos:**
- **A1 – Nenhum registro encontrado:** O sistema informa que não há acessos para os filtros aplicados.

**Requisitos relacionados:** RF09
**Requisitos não funcionais:** RNF02, RNF05
**Regras de negócio:** RN06

---

### UC20 – Realizar Logout

| Campo | Descrição |
|---|---|
| **Ator principal** | Usuário (Aluno, Recepcionista, Instrutor ou Gerente) |
| **Objetivo** | Encerrar a sessão autenticada do usuário no sistema de forma segura |
| **Pré-condições** | Usuário autenticado com sessão ativa |
| **Pós-condições** | Sessão encerrada; usuário redirecionado para a tela de login |

**Fluxo Principal:**
1. O usuário acessa a opção de logout no sistema.
2. O sistema solicita confirmação do encerramento da sessão.
3. O usuário confirma.
4. O sistema invalida o token de sessão do usuário.
5. O sistema redireciona para a tela de login.

**Fluxos Alternativos:**
- **A1 – Sessão expirada por inatividade:** O sistema encerra a sessão automaticamente e redireciona o usuário para a tela de login com aviso de expiração.

**Requisitos relacionados:** RF04
**Requisitos não funcionais:** RNF02, RNF04
**Regras de negócio:** RN06

---

## 3. Diagramas de Atividade

Os diagramas de atividade a seguir representam os fluxos de execução de cada caso de uso em notação PlantUML, espelhando fielmente os fluxos principais e alternativos documentados na Seção 2. Foram adicionados também três diagramas agrupados contemplando fluxos interdependentes.

---

### DA01 – Cadastrar Aluno (UC01)

@startuml DA01_CadastrarAluno
start
:Recepcionista acessa o módulo de matrículas;
:Sistema exibe o formulário de cadastro;
:Recepcionista preenche dados pessoais, de contato e endereço do aluno;
:Recepcionista seleciona o plano contratado;
:Sistema valida os dados informados;
if (Dados obrigatórios preenchidos?) then (Não)
  :Sistema exibe mensagem de erro indicando campos ausentes;
  stop
else (Sim)
  if (Plano selecionado está ativo?) then (Não)
    :Sistema alerta que o plano não está disponível;
    stop
  else (Sim)
    :Sistema registra o aluno e vincula o cartão RFID;
    :Sistema exibe confirmação de cadastro realizado com sucesso;
    stop
  endif
endif
@enduml

---

### DA02 – Gerenciar Planos (UC02)

```plantuml
@startuml DA02_GerenciarPlanos
start
:Gerente acessa o módulo de gerenciamento de planos;
:Sistema exibe a lista de planos cadastrados e seus status;
:Gerente seleciona a ação desejada (criar/editar/ativar/desativar);
:Sistema exibe o formulário correspondente à ação;
:Gerente preenche ou altera as informações do plano;
if (Ação = Desativar?) then (Sim)
  if (Plano possui alunos ativos vinculados?) then (Sim)
    :Sistema alerta sobre alunos ativos no plano;
    :Gerente confirma ação para prosseguir;
  else (Não)
  endif
endif
:Sistema valida e salva as alterações;
:Sistema exibe confirmação da operação realizada;
stop
@enduml
```

---

### DA03 – Realizar Login (UC03)

```plantuml
@startuml DA03_RealizarLogin
start
:Usuário acessa a tela de login do sistema;
:Usuário informa e-mail e senha;
:Sistema valida as credenciais informadas;
if (Credenciais válidas?) then (Não)
  :Sistema exibe mensagem de erro e permite nova tentativa;
  stop
else (Sim)
  if (Conta bloqueada ou inativa?) then (Sim)
    :Sistema impede o login e orienta contato com a recepção;
    stop
  else (Não)
    :Sistema identifica o perfil do usuário;
    :Sistema inicia a sessão e redireciona para a tela inicial do perfil;
    stop
  endif
endif
@enduml
```

---

### DA04 – Editar Cadastro de Aluno (UC04)

```plantuml
@startuml DA04_EditarCadastroAluno
start
:Recepcionista acessa o módulo de matrículas e busca o aluno pelo nome ou CPF;
if (Aluno encontrado?) then (Não)
  :Sistema informa que o aluno não foi localizado e retorna à tela de busca;
  stop
else (Sim)
  :Sistema exibe os dados atuais do aluno;
  :Recepcionista seleciona a opção de edição;
  :Sistema exibe o formulário preenchido com os dados existentes;
  :Recepcionista altera os campos desejados;
  :Sistema valida os dados informados;
  if (Dados válidos?) then (Não)
    :Sistema exibe mensagem de erro indicando campos com problema;
    stop
  else (Sim)
    :Sistema salva as alterações e exibe confirmação;
    stop
  endif
endif
@enduml
```

---

### DA05 – Verificar Regularidade do Aluno (UC05)

```plantuml
@startuml DA05_VerificarRegularidade
start
:Recepcionista acessa o módulo de consulta de alunos;
:Recepcionista busca o aluno pelo nome ou CPF;
if (Aluno encontrado?) then (Não)
  :Sistema informa que o aluno não foi localizado e retorna à tela de busca;
  stop
else (Sim)
  :Sistema exibe o status atual do aluno: regular, inadimplente ou inativo;
  :Sistema exibe o histórico de pagamentos e a data do próximo vencimento;
  stop
endif
@enduml
```

---

### DA06 – Registrar Pagamento de Mensalidade (UC06)

```plantuml
@startuml DA06_RegistrarPagamento
start
:Recepcionista busca o aluno pelo nome ou CPF;
if (Aluno encontrado?) then (Não)
  :Sistema informa que o aluno não foi localizado e retorna à tela de busca;
  stop
else (Sim)
  :Sistema exibe os dados do aluno e o valor da mensalidade em aberto;
  :Recepcionista seleciona a forma de pagamento (dinheiro, cartão ou PIX);
  if (Pagamento é integral?) then (Não)
    :Sistema bloqueia a operação (RN04);
    :Sistema exibe mensagem informando que apenas pagamento integral é permitido;
    stop
  else (Sim)
    :Sistema registra o pagamento pelo valor integral;
    :Sistema atualiza imediatamente a situação do aluno para "regular" (RN07);
    :Sistema exibe confirmação do pagamento;
    stop
  endif
endif
@enduml
```

---

### DA07 – Gerar Cobrança Online (UC07)

```plantuml
@startuml DA07_GerarCobrancaOnline
start
:Sistema identifica os alunos com mensalidade em aberto;
if (Geração da cobrança bem-sucedida?) then (Não)
  :Sistema registra o erro e agenda nova tentativa de geração;
  stop
else (Sim)
  :Sistema gera o boleto ou link de pagamento para cada aluno elegível;
  :Sistema envia a cobrança ao aluno pelo canal configurado;
  :Sistema registra a geração da cobrança no histórico do aluno;
  if (Pagamento confirmado até a data de vencimento?) then (Não)
    :Sistema mantém situação do aluno como inadimplente (RN01);
    stop
  else (Sim)
    :Sistema atualiza a situação do aluno para "regular" (RN07);
    stop
  endif
endif
@enduml
```

---

### DA08 – Enviar Notificação de Vencimento de Mensalidade (UC08)

```plantuml
@startuml DA08_NotificarVencimento
start
:Sistema verifica diariamente as datas de vencimento das mensalidades;
:Sistema identifica os alunos com vencimento próximo;
:Sistema gera a notificação com os dados do valor e da data de vencimento;
:Sistema envia a notificação ao aluno pelo canal configurado (e-mail ou app);
if (Envio bem-sucedido?) then (Não)
  :Sistema registra a falha e realiza nova tentativa no ciclo seguinte;
else (Sim)
  :Sistema registra o envio da notificação no histórico do aluno;
endif
stop
@enduml
```

---

### DA09 – Validar Acesso pela Catraca (UC09)

```plantuml
@startuml DA09_ValidarAcessoCatraca
start
:Aluno aproxima o cartão RFID da catraca;
:Catraca envia o código RFID ao sistema via API REST;
:Sistema identifica o aluno pelo código RFID;
if (Cartão RFID reconhecido?) then (Não)
  :Sistema retorna erro de identificação;
  :Acesso negado; catraca permanece bloqueada;
  stop
else (Sim)
  :Sistema verifica se o aluno está com a mensalidade em dia;
  if (Mensalidade vencida há mais de 5 dias?) then (Sim)
    :Sistema retorna negação de acesso (RN01);
    :Catraca permanece bloqueada;
    stop
  else (Não)
    :Sistema retorna autorização de acesso à catraca;
    :Catraca libera a entrada;
    :Sistema registra o acesso no histórico do aluno;
    stop
  endif
endif
@enduml
```

---

### DA10 – Agendar Aula (UC10)

```plantuml
@startuml DA10_AgendarAula
start
:Aluno acessa o módulo de agendamento;
:Sistema exibe a lista de aulas disponíveis com horários e vagas;
:Aluno seleciona a aula desejada;
:Sistema verifica a disponibilidade de vagas;
if (Aluno inadimplente?) then (Sim)
  :Sistema impede o agendamento e orienta o aluno a regularizar a situação;
  stop
else (Não)
  if (Vagas disponíveis?) then (Não)
    :Sistema informa que a capacidade máxima foi atingida (RN02);
    stop
  else (Sim)
    :Sistema registra a reserva do aluno;
    :Sistema envia notificação de confirmação ao aluno (UC11);
    stop
  endif
endif
@enduml
```

---

### DA11 – Confirmar Agendamento de Aula (UC11)

```plantuml
@startuml DA11_ConfirmarAgendamento
start
:Sistema recebe o registro de novo agendamento (originado pelo UC10);
:Sistema verifica o canal de notificação do aluno;
if (Canal de notificação configurado?) then (Não)
  :Sistema ignora o envio e registra que o aluno não possui canal ativo;
  stop
else (Sim)
  :Sistema gera a mensagem de confirmação com nome da aula, data e horário;
  :Sistema envia a notificação ao aluno;
  if (Envio bem-sucedido?) then (Não)
    :Sistema registra a falha e realiza nova tentativa de envio;
  else (Sim)
    :Sistema registra o envio no histórico de notificações do aluno;
  endif
  stop
endif
@enduml
```

---

### DA12 – Cancelar Agendamento de Aula (UC12)

```plantuml
@startuml DA12_CancelarAgendamento
start
:Aluno acessa seus agendamentos;
:Sistema lista as aulas reservadas;
:Aluno seleciona a aula que deseja cancelar;
:Sistema verifica se o cancelamento respeita o prazo mínimo de 1 hora;
if (Cancelamento dentro do prazo?) then (Não)
  :Sistema informa que o prazo foi encerrado e bloqueia a operação (RN03);
  stop
else (Sim)
  :Sistema cancela a reserva e libera a vaga;
  :Sistema exibe confirmação do cancelamento;
  stop
endif
@enduml
```

---

### DA13 – Registrar Presença em Aula (UC13)

```plantuml
@startuml DA13_RegistrarPresenca
start
:Instrutor acessa o módulo de aulas do dia;
:Sistema exibe a lista de aulas e os alunos agendados;
:Instrutor seleciona a aula correspondente;
:Sistema exibe a lista de alunos com agendamento confirmado;
:Instrutor marca a presença de cada aluno;
if (Aluno presente sem agendamento?) then (Sim)
  if (Vaga disponível?) then (Sim)
    :Instrutor inclui manualmente o aluno na lista;
  else (Não)
    :Sistema impede a inclusão por falta de vaga;
  endif
endif
:Sistema salva o registro de presença;
stop
@enduml
```

---

### DA14 – Registrar Avaliação Física (UC14)

```plantuml
@startuml DA14_RegistrarAvaliacaoFisica
start
:Instrutor acessa o módulo de avaliações físicas;
:Instrutor busca e seleciona o aluno a ser avaliado;
:Sistema verifica se o aluno está ativo e regular;
if (Aluno ativo e regular?) then (Não)
  :Sistema bloqueia o registro (RN05);
  stop
else (Sim)
  :Instrutor preenche os dados da avaliação (peso, IMC, percentual de gordura etc.);
  :Instrutor pode anexar arquivos complementares, se necessário;
  :Sistema salva a avaliação e notifica o aluno (UC15);
  stop
endif
@enduml
```

---

### DA15 – Notificar Liberação de Avaliação Física (UC15)

```plantuml
@startuml DA15_NotificarLiberacaoAvaliacao
start
:Sistema detecta o registro de nova avaliação física vinculada ao aluno (UC14);
:Sistema verifica o canal de notificação do aluno;
:Sistema gera a mensagem de notificação com a data da avaliação;
:Sistema envia a notificação ao aluno;
if (Envio bem-sucedido?) then (Não)
  :Sistema registra a falha e agenda nova tentativa de envio;
else (Sim)
  :Sistema registra o envio no histórico de notificações do aluno;
endif
stop
@enduml
```

---

### DA16 – Consultar Avaliação Física (UC16)

```plantuml
@startuml DA16_ConsultarAvaliacaoFisica
start
:Aluno acessa o módulo de avaliações físicas;
:Sistema exibe a lista de avaliações registradas em ordem cronológica;
if (Existe avaliação registrada?) then (Não)
  :Sistema informa que não há avaliações físicas disponíveis para o aluno;
  stop
else (Sim)
  :Aluno seleciona a avaliação desejada;
  :Sistema exibe os detalhes completos da avaliação selecionada;
  if (Possui arquivos anexados?) then (Sim)
    :Aluno pode visualizar os arquivos anexados;
  endif
  stop
endif
@enduml
```

---

### DA17 – Emitir Relatório Gerencial (UC17)

```plantuml
@startuml DA17_EmitirRelatorioGerencial
start
:Gerente acessa o módulo de relatórios;
:Sistema exibe os tipos de relatórios disponíveis;
:Gerente seleciona o tipo de relatório e o período desejado;
:Sistema processa e gera o relatório solicitado;
if (Dados encontrados?) then (Não)
  :Sistema informa que não há registros para os filtros aplicados;
  stop
else (Sim)
  :Gerente visualiza o relatório;
  :Gerente pode exportar o relatório;
  stop
endif
@enduml
```

---

### DA18 – Emitir Relatório de Ocupação de Aulas (UC18)

```plantuml
@startuml DA18_RelatorioOcupacaoAulas
start
:Gerente acessa o módulo de relatórios;
:Gerente seleciona o tipo "Ocupação de Aulas";
:Gerente define o período de análise desejado;
:Sistema processa os dados de agendamento e presença das aulas no período;
:Sistema gera o relatório com percentual de ocupação por aula;
if (Dados encontrados?) then (Não)
  :Sistema informa que não há registros para os filtros aplicados;
  stop
else (Sim)
  :Gerente visualiza o relatório e pode exportá-lo;
  stop
endif
@enduml
```

---

### DA19 – Consultar Histórico de Acessos (UC19)

```plantuml
@startuml DA19_ConsultarHistoricoAcessos
start
:Gerente acessa o módulo de relatórios;
:Gerente seleciona o tipo "Histórico de Acessos";
:Gerente define o período e, opcionalmente, filtra por aluno;
:Sistema consulta os registros de entrada no período informado;
if (Registros encontrados?) then (Não)
  :Sistema informa que não há acessos para os filtros aplicados;
  stop
else (Sim)
  :Sistema exibe a listagem de acessos com data, horário e nome do aluno;
  :Gerente pode exportar o relatório;
  stop
endif
@enduml
```

---

### DA20 – Realizar Logout (UC20)

```plantuml
@startuml DA20_RealizarLogout
start
:Usuário acessa a opção de logout no sistema;
:Sistema solicita confirmação do encerramento da sessão;
:Usuário confirma;
:Sistema invalida o token de sessão do usuário;
:Sistema redireciona para a tela de login;
stop

note right
  FA1: Sessão expirada por inatividade —
  Sistema encerra automaticamente e
  redireciona com aviso de expiração,
  sem necessidade de confirmação do usuário.
end note
@enduml
```

---

### DA-GRP01 – Fluxo de Acesso e Validação (UC03 + UC09 + UC05)

> Diagrama agrupado representando o ciclo completo de um aluno desde o login até a validação de acesso físico.

```plantuml
@startuml DA_GRP01_AcessoValidacao
start
:Usuário acessa a tela de login e informa credenciais (UC03);
if (Autenticação válida?) then (Não)
  :Sistema bloqueia acesso;
  stop
else (Sim)
  :Sistema identifica perfil e inicia sessão;
  if (Perfil = Aluno?) then (Sim)
    :Aluno se dirige à catraca e aproxima cartão RFID (UC09);
    :Sistema consulta regularidade do aluno (UC05);
    if (Mensalidade vencida há mais de 5 dias?) then (Sim)
      :Sistema nega acesso (RN01);
      :Catraca permanece bloqueada;
      stop
    else (Não)
      :Sistema autoriza acesso;
      :Catraca libera entrada e sistema registra acesso;
      stop
    endif
  else (Não)
    :Usuário acessa painel do seu perfil;
    stop
  endif
endif
@enduml
```

---

### DA-GRP02 – Fluxo Financeiro (UC06 + UC07 + UC08 + UC05)

> Diagrama agrupado representando o ciclo financeiro: notificação, cobrança, pagamento e atualização de regularidade.

```plantuml
@startuml DA_GRP02_FluxoFinanceiro
start
:Sistema verifica vencimentos diariamente e envia notificação ao aluno (UC08);
fork
  :Aluno opta por pagar presencialmente;
  :Recepcionista busca aluno e registra pagamento integral (UC06);
fork again
  :Sistema gera cobrança online e envia ao aluno (UC07);
  :Aluno realiza pagamento pelo canal online;
end fork
:Sistema atualiza situação do aluno para "regular" (RN07);
:Sistema verifica regularidade atualizada (UC05);
:Aluno liberado para acesso à academia;
stop
@enduml
```

---

### DA-GRP03 – Fluxo de Agendamento e Aula (UC10 + UC11 + UC12 + UC13)

> Diagrama agrupado representando o ciclo completo de uma aula: agendamento, confirmação, possível cancelamento e registro de presença.

```plantuml
@startuml DA_GRP03_FluxoAgendamentoAula
start
:Aluno acessa módulo de agendamento e seleciona aula (UC10);
if (Aluno inadimplente ou sem vagas?) then (Sim)
  :Sistema bloqueia agendamento;
  stop
else (Não)
  :Sistema registra reserva;
  :Sistema envia notificação de confirmação ao aluno (UC11);
  if (Aluno cancela com pelo menos 1h de antecedência?) then (Sim)
    :Sistema cancela agendamento e libera vaga (UC12);
    stop
  else (Não)
    :Aula ocorre no horário agendado;
    :Instrutor seleciona aula, marca presenças e sistema salva registro (UC13);
    stop
  endif
endif
@enduml
```

---

*Documento gerado para fins acadêmicos – Disciplina de Engenharia de Software – UNIFEOB*
