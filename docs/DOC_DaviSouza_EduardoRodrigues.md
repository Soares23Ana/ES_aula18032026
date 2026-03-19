# FitPass Gym Management – Documento de Casos de Uso

# Diagrama de Casos de Uso

<img width="615" height="1909" alt="image" src="https://github.com/user-attachments/assets/34380bd5-9803-4d4d-82a8-be1e680ab465" />


---

## UC01 — Realizar Login

### Ator Principal
Usuário

### Objetivo
Permitir que o usuário acesse o sistema.

### Pré-condições
Usuário deve possuir cadastro ativo.

### Pós-condições
Sessão iniciada com sucesso.

### Fluxo Principal
1. O usuário informa e-mail e senha.
2. O sistema valida as credenciais.
3. O sistema autentica o usuário e redireciona para a tela inicial.

### Fluxos Alternativos
- **A1 — Senha incorreta:**  
  O sistema exibe mensagem de erro.

- **A2 — Conta bloqueada:**  
  O sistema impede o login e instrui o usuário a recuperar o acesso.

### RF Relacionados
- RF01

### RNF Relacionados
- RNF02 
- RNF04

### RN Relacionadas
- RN06

<img width="551" height="398" alt="image" src="https://github.com/user-attachments/assets/8fef24ed-881e-4ad9-a598-bc49a84b6718" />

---

## UC02 --- Cadastrar Aluno

### Ator Principal
Recepcionista

### Objetivo
Registrar um novo aluno no sistema.

### Pré-condições
- Recepcionista deve estar autenticado no sistema.

### Pós-condições
- Aluno cadastrado no sistema.

### Fluxo Principal
1. O recepcionista acessa a opção de cadastro de alunos.
2. O sistema exibe o formulário de cadastro.
3. O recepcionista preenche os dados pessoais, contato e endereço.
4. O recepcionista seleciona um plano.
5. O sistema salva o cadastro do aluno.

### Fluxos Alternativos
- **A1 --- Dados incompletos:**
  O sistema solicita preenchimento dos campos obrigatórios.

### RF Relacionados
- RF01

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN06

<img width="463" height="398" alt="image" src="https://github.com/user-attachments/assets/2f9a52e6-e905-4f45-a5d8-998eca049ab9" />


---

## UC03 --- Atualizar Dados do Aluno

### Ator Principal
Recepcionista

### Objetivo
Permitir atualizar informações cadastrais do aluno.

### Pré-condições
- Aluno deve estar cadastrado no sistema.

### Pós-condições
- Dados atualizados no sistema.

### Fluxo Principal
1. O recepcionista busca o aluno pelo nome ou CPF.
2. O sistema exibe os dados cadastrados.
3. O recepcionista altera as informações necessárias.
4. O sistema salva as alterações.

### Fluxos Alternativos
- **A1 --- Aluno não encontrado:**
  O sistema informa que não existe cadastro.

### RF Relacionados
- RF01

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN06

<img width="393" height="410" alt="image" src="https://github.com/user-attachments/assets/4596ee1c-6530-45bc-ad93-4af6d9888540" />


---

## UC04 --- Criar Plano

### Ator Principal
Gerente

### Objetivo
Criar novos planos de academia.

### Pré-condições
- Gerente autenticado no sistema.

### Pós-condições
- Novo plano disponível para contratação.

### Fluxo Principal
1. O gerente acessa a área de planos.
2. O sistema exibe formulário de criação.
3. O gerente informa nome, valor e duração do plano.
4. O sistema registra o plano.

### Fluxos Alternativos
- **A1 --- Dados inválidos:**
  O sistema solicita correção dos dados.

### RF Relacionados
- RF02

### RNF Relacionados
- RNF04
- RNF05

### RN Relacionadas
- RN06

<img width="421" height="398" alt="image" src="https://github.com/user-attachments/assets/e030562f-6996-44a0-933e-bea99a44a7b9" />


---

## UC05 --- Editar Plano

### Ator Principal
Gerente

### Objetivo
Modificar informações de um plano existente.

### Pré-condições
- Plano cadastrado no sistema.

### Pós-condições
- Plano atualizado.

### Fluxo Principal
1. O gerente seleciona um plano existente.
2. O sistema exibe os dados do plano.
3. O gerente altera as informações.
4. O sistema salva as alterações.

### Fluxos Alternativos
- **A1 --- Plano inexistente:**
  O sistema informa erro.

### RF Relacionados
- RF02

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN06

<img width="357" height="410" alt="image" src="https://github.com/user-attachments/assets/57dcd287-b60e-4eca-a40a-41332f8a029b" />


---

## UC06 --- Registrar Pagamento

### Ator Principal
Recepcionista

### Objetivo
Registrar pagamento da mensalidade.

### Pré-condições
- Aluno deve possuir plano ativo.

### Pós-condições
- Pagamento registrado.

### Fluxo Principal
1. O recepcionista seleciona o aluno.
2. O sistema exibe mensalidade pendente.
3. O recepcionista registra o pagamento.
4. O sistema atualiza a situação do aluno.

### Fluxos Alternativos
- **A1 --- Valor incorreto:**
  O sistema impede registro.

### RF Relacionados
- RF03

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN04
- RN07

<img width="614" height="469" alt="image" src="https://github.com/user-attachments/assets/7380ad80-39d9-4aee-91f9-754637e1d5b6" />


---

## UC07 --- Verificar Regularidade do Aluno

### Ator Principal
Sistema

### Objetivo
Verificar se o aluno está com pagamentos em dia.

### Pré-condições
- Aluno cadastrado.

### Pós-condições
- Status de regularidade atualizado.

### Fluxo Principal
1. O sistema consulta o histórico de pagamentos.
2. O sistema verifica a data de vencimento.
3. O sistema define o status do aluno.

### Fluxos Alternativos
- **A1 --- Mensalidade vencida:**
  O sistema marca o aluno como inadimplente.

### RF Relacionados
- RF04

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN01

<img width="273" height="312" alt="image" src="https://github.com/user-attachments/assets/f44a4f00-1c17-4db9-af7a-62c900140b95" />


---

## UC08 --- Validar Entrada na Academia

### Ator Principal
Aluno

### Objetivo
Permitir entrada utilizando RFID.

### Pré-condições
- Aluno deve possuir cartão RFID.

### Pós-condições
- Entrada liberada ou negada.

### Fluxo Principal
1. O aluno aproxima o cartão RFID da catraca.
2. O sistema verifica o cadastro.
3. O sistema verifica a regularidade do aluno.
4. A catraca é liberada.

### Fluxos Alternativos
- **A1 --- Aluno inadimplente:**
  A catraca permanece bloqueada.

### RF Relacionados
- RF05

### RNF Relacionados
- RNF03
- RNF06

### RN Relacionadas
- RN01

<img width="397" height="398" alt="image" src="https://github.com/user-attachments/assets/66d2158f-2da8-42ea-9ff5-399acb0f24bf" />


---

## UC09 --- Visualizar Aulas Disponíveis

### Ator Principal
Aluno

### Objetivo
Permitir consulta de horários de aulas.

### Pré-condições
- Aluno autenticado no sistema.

### Pós-condições
- Lista de aulas exibida.

### Fluxo Principal
1. O aluno acessa a área de aulas.
2. O sistema lista horários disponíveis.
3. O aluno escolhe uma aula.

### Fluxos Alternativos
- **A1 --- Nenhuma aula disponível:**
  O sistema informa indisponibilidade.

### RF Relacionados
- RF06

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN02

<img width="422" height="288" alt="image" src="https://github.com/user-attachments/assets/bb60df1c-46c8-4823-8656-a9bce943b4f5" />


---

## UC10 --- Agendar Aula

### Ator Principal
Aluno

### Objetivo
Reservar vaga em uma aula.

### Pré-condições
- Aula disponível.

### Pós-condições
- Reserva registrada.

### Fluxo Principal
1. O aluno seleciona uma aula.
2. O sistema verifica disponibilidade.
3. O sistema confirma o agendamento.

### Fluxos Alternativos
- **A1 --- Aula lotada:**
  O sistema bloqueia o agendamento.

### RF Relacionados
- RF06

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN02

<img width="485" height="288" alt="image" src="https://github.com/user-attachments/assets/89916c83-12cb-466c-a563-6499a34cb4d0" />


---

## UC11 --- Cancelar Agendamento

### Ator Principal
Aluno

### Objetivo
Permitir que o aluno cancele uma reserva de aula.

### Pré-condições
- O aluno deve possuir um agendamento ativo.

### Pós-condições
- Reserva cancelada no sistema.

### Fluxo Principal
1. O aluno acessa a lista de agendamentos.
2. O aluno seleciona a aula agendada.
3. O aluno escolhe cancelar.
4. O sistema remove a reserva.

### Fluxos Alternativos
- **A1 --- Prazo expirado:**
  O sistema impede o cancelamento.

### RF Relacionados
- RF06

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN03

<img width="491" height="343" alt="image" src="https://github.com/user-attachments/assets/a023efcb-0c3d-4522-b425-8169758ed513" />


---

## UC12 --- Registrar Presença em Aula

### Ator Principal
Instrutor

### Objetivo
Registrar presença dos alunos nas aulas.

### Pré-condições
- Aula em andamento.

### Pós-condições
- Presença registrada.

### Fluxo Principal
1. O instrutor abre a lista da aula.
2. O instrutor marca presença dos alunos.
3. O sistema salva os registros.

### Fluxos Alternativos
- **A1 --- Aluno não inscrito:**
  O sistema impede registro.

### RF Relacionados
- RF07

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN06

<img width="413" height="398" alt="image" src="https://github.com/user-attachments/assets/837dd701-4d07-4966-837b-c39408934829" />


---

## UC13 --- Registrar Avaliação Física

### Ator Principal
Instrutor

### Objetivo
Registrar dados físicos do aluno.

### Pré-condições
- Aluno ativo.

### Pós-condições
- Avaliação registrada.

### Fluxo Principal
1. O instrutor seleciona o aluno.
2. O instrutor registra peso, IMC e percentual de gordura.
3. O sistema salva os dados.

### Fluxos Alternativos
- **A1 --- Aluno irregular:**
  O sistema impede avaliação.

### RF Relacionados
- RF08

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN05

<img width="430" height="410" alt="image" src="https://github.com/user-attachments/assets/a7266951-c7db-4a37-ac1b-d7131b540340" />


---

## UC14 --- Anexar Arquivo à Avaliação

### Ator Principal
Instrutor

### Objetivo
Adicionar documentos ou imagens à avaliação física.

### Pré-condições
- Avaliação existente.

### Pós-condições
- Arquivo anexado.

### Fluxo Principal
1. O instrutor acessa avaliação.
2. O instrutor seleciona arquivo.
3. O sistema salva o anexo.

### Fluxos Alternativos
- **A1 --- Arquivo inválido:**
  O sistema rejeita upload.

### RF Relacionados
- RF08

### RNF Relacionados
- RNF02

### RN Relacionadas
- RN06

<img width="393" height="343" alt="image" src="https://github.com/user-attachments/assets/7f19d1ec-e704-4def-bfe8-3a8f1a4fcddb" />


---

## UC15 --- Gerar Relatório de Inadimplência

### Ator Principal
Gerente

### Objetivo
Visualizar alunos inadimplentes.

### Pré-condições
- Gerente autenticado.

### Pós-condições
- Relatório exibido.

### Fluxo Principal
1. O gerente acessa relatórios.
2. O gerente seleciona inadimplência.
3. O sistema gera relatório.

### Fluxos Alternativos
- **A1 --- Sem dados:**
  O sistema informa ausência de registros.

### RF Relacionados
- RF09

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN01

<img width="413" height="288" alt="image" src="https://github.com/user-attachments/assets/713cce5f-7404-451a-8167-c1e85d48a1aa" />


---

## UC16 --- Gerar Relatório de Alunos Ativos

### Ator Principal
Gerente

### Objetivo
Listar alunos com plano ativo.

### Pré-condições
- Gerente autenticado.

### Pós-condições
- Relatório gerado.

### Fluxo Principal
1. O gerente seleciona relatório de alunos ativos.
2. O sistema gera a lista.

### Fluxos Alternativos
- **A1 --- Nenhum aluno ativo:**
  O sistema informa.

### RF Relacionados
- RF09

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN06

<img width="374" height="288" alt="image" src="https://github.com/user-attachments/assets/b66d9114-68e8-4969-beee-1b5c50397474" />

---

## UC17 --- Gerar Relatório de Acessos

### Ator Principal
Gerente

### Objetivo
Consultar histórico de entradas na academia.

### Pré-condições
- Registros de acesso existentes.

### Pós-condições
- Relatório exibido.

### Fluxo Principal
1. O gerente seleciona relatório de acessos.
2. O sistema consulta histórico.
3. O sistema exibe dados.

### Fluxos Alternativos
- **A1 --- Sem registros:**
  O sistema informa.

### RF Relacionados
- RF09

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN06

<img width="421" height="288" alt="image" src="https://github.com/user-attachments/assets/880981de-0c3a-4611-9992-05c760ea9770" />


---

## UC18 --- Gerar Relatório de Ocupação de Aulas

### Ator Principal
Gerente

### Objetivo
Analisar participação nas aulas.

### Pré-condições
- Aulas cadastradas.

### Pós-condições
- Relatório exibido.

### Fluxo Principal
1. O gerente seleciona relatório de ocupação.
2. O sistema analisa presenças.
3. O sistema gera relatório.

### Fluxos Alternativos
- **A1 --- Nenhuma aula registrada:**
  O sistema informa.

### RF Relacionados
- RF09

### RNF Relacionados
- RNF05

### RN Relacionadas
- RN02

<img width="444" height="343" alt="image" src="https://github.com/user-attachments/assets/8bb84c95-3be8-45ad-9154-64d185164aa8" />


---

## UC19 --- Enviar Notificação de Vencimento

### Ator Principal
Sistema

### Objetivo
Avisar aluno sobre vencimento da mensalidade.

### Pré-condições
- Aluno com mensalidade ativa.

### Pós-condições
- Notificação enviada.

### Fluxo Principal
1. O sistema identifica mensalidade próxima do vencimento.
2. O sistema envia notificação.

### Fluxos Alternativos
- **A1 --- Falha no envio:**
  O sistema registra erro.

### RF Relacionados
- RF10

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN07

<img width="317" height="338" alt="image" src="https://github.com/user-attachments/assets/f7da29cb-be77-447b-8204-9fffb7719649" />


---

## UC20 --- Enviar Confirmação de Agendamento

### Ator Principal
Sistema

### Objetivo
Confirmar reserva de aula ao aluno.

### Pré-condições
- Agendamento realizado.

### Pós-condições
- Notificação enviada.

### Fluxo Principal
1. O sistema registra o agendamento.
2. O sistema envia confirmação.

### Fluxos Alternativos
- **A1 --- Falha no envio:**
  O sistema registra erro.

### RF Relacionados
- RF10

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN02

<img width="312" height="245" alt="image" src="https://github.com/user-attachments/assets/cce29948-efcf-4dfd-a742-bf7f6cb8adbd" />
