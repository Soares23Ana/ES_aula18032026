# Casos de Uso – Sistema FitPass Gym Management

---

## UC01 — Realizar Login

### Ator Principal
Usuário

### Objetivo
Permitir que o usuário acesse o sistema.

### Pré-condições
- Usuário deve possuir cadastro ativo.

### Pós-condições
- Sessão iniciada com sucesso.

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

<img width="316" height="374" alt="image" src="https://github.com/user-attachments/assets/29266110-4ec4-4b5b-bfd9-2873fd5b5423" />

---

## UC02 — Cadastrar Aluno

### Ator Principal
Recepcionista

### Objetivo
Cadastrar um novo aluno no sistema.

### Pré-condições
- Recepcionista deve estar autenticado no sistema.

### Pós-condições
- Aluno cadastrado com sucesso.

### Fluxo Principal
1. O recepcionista acessa a tela de cadastro.
2. Informa os dados pessoais do aluno.
3. Seleciona o plano desejado.
4. O sistema salva o cadastro.

### Fluxos Alternativos
- **A1 — Dados incompletos:**  
  O sistema solicita o preenchimento dos campos obrigatórios.

### RF Relacionados
- RF01

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN06

<img width="302" height="312" alt="image" src="https://github.com/user-attachments/assets/cd9650ce-acc1-4280-9ed0-dccf8f6b297e" />

---

## UC03 — Criar Plano

### Ator Principal
Gerente

### Objetivo
Cadastrar um novo plano de academia.

### Pré-condições
- Gerente autenticado no sistema.

### Pós-condições
- Plano criado com sucesso.

### Fluxo Principal
1. O gerente acessa a área de planos.
2. Informa nome, valor e duração.
3. O sistema registra o plano.

### Fluxos Alternativos
- **A1 — Plano já existente:**  
  O sistema informa que o plano já existe.

### RF Relacionados
- RF02

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN06

<img width="173" height="248" alt="image" src="https://github.com/user-attachments/assets/7f0f45a4-8176-4694-b005-3eed0f38123c" />

---

## UC04 — Editar Plano

### Ator Principal
Gerente

### Objetivo
Atualizar informações de um plano.

### Pré-condições
- Plano existente no sistema.

### Pós-condições
- Plano atualizado.

### Fluxo Principal
1. O gerente seleciona o plano.
2. Edita as informações.
3. O sistema salva as alterações.

### Fluxos Alternativos
- **A1 — Plano não encontrado:**  
  O sistema informa erro.

### RF Relacionados
- RF02

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN06

<img width="177" height="248" alt="image" src="https://github.com/user-attachments/assets/ad160b21-3523-4e75-b886-85afe1dd5dfa" />

---

## UC05 — Registrar Pagamento

### Ator Principal
Recepcionista

### Objetivo
Registrar pagamento de mensalidade.

### Pré-condições
- Aluno cadastrado no sistema.

### Pós-condições
- Pagamento registrado.

### Fluxo Principal
1. O recepcionista busca o aluno.
2. Seleciona forma de pagamento.
3. O sistema registra o pagamento.

### Fluxos Alternativos
- **A1 — Falha no pagamento:**  
  O sistema informa erro.

### RF Relacionados
- RF03

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN04
- RN07

<img width="300" height="312" alt="image" src="https://github.com/user-attachments/assets/11b095e7-5414-4829-aa60-93a9cb5ca2d1" />

---

## UC06 — Verificar Situação do Aluno

### Ator Principal
Sistema

### Objetivo
Verificar se o aluno está em dia com a mensalidade.

### Pré-condições
- Aluno cadastrado.

### Pós-condições
- Situação atualizada.

### Fluxo Principal
1. O sistema verifica pagamentos.
2. O sistema define se o aluno está regular.

### Fluxos Alternativos
- **A1 — Pagamento vencido:**  
  O sistema marca como inadimplente.

### RF Relacionados
- RF04

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN01

<img width="261" height="257" alt="image" src="https://github.com/user-attachments/assets/9d17eb66-10e0-4c09-a1b8-4a8b66559aa5" />

---

## UC07 — Validar Entrada na Academia

### Ator Principal
Sistema de Catraca

### Objetivo
Permitir ou bloquear entrada do aluno.

### Pré-condições
- Aluno possuir cartão RFID.

### Pós-condições
- Entrada liberada ou bloqueada.

### Fluxo Principal
1. O aluno aproxima o cartão da catraca.
2. O sistema verifica a situação do aluno.
3. A entrada é liberada.

### Fluxos Alternativos
- **A1 — Aluno inadimplente:**  
  Entrada bloqueada.

### RF Relacionados
- RF05

### RNF Relacionados
- RNF03
- RNF06

### RN Relacionadas
- RN01

<img width="255" height="312" alt="image" src="https://github.com/user-attachments/assets/ec01f169-e9c2-4c13-8c52-780d737193c0" />

---

## UC08 — Visualizar Horários de Aula

### Ator Principal
Aluno

### Objetivo
Consultar horários disponíveis.

### Pré-condições
- Aluno autenticado.

### Pós-condições
- Horários exibidos.

### Fluxo Principal
1. O aluno acessa a área de aulas.
2. O sistema mostra os horários.

### Fluxos Alternativos
- **A1 — Nenhuma aula disponível:**  
  Sistema informa ausência de horários.

### RF Relacionados
- RF06

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN02

<img width="169" height="193" alt="image" src="https://github.com/user-attachments/assets/da515642-7863-4606-9e08-fc0f37243dbf" />

---

## UC09 — Reservar Aula

### Ator Principal
Aluno

### Objetivo
Agendar vaga em uma aula.

### Pré-condições
- Aluno ativo no sistema.

### Pós-condições
- Reserva registrada.

### Fluxo Principal
1. O aluno seleciona a aula.
2. Confirma a reserva.
3. O sistema registra.

### Fluxos Alternativos
- **A1 — Aula lotada:**  
  Sistema bloqueia reserva.

### RF Relacionados
- RF06

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN02

<img width="250" height="257" alt="image" src="https://github.com/user-attachments/assets/b94eb9de-6ca6-4658-b5f6-d27ec0dc0cdf" />

---

## UC10 — Cancelar Reserva de Aula

### Ator Principal
Aluno

### Objetivo
Cancelar agendamento de aula.

### Pré-condições
- Reserva existente.

### Pós-condições
- Reserva cancelada.

### Fluxo Principal
1. O aluno acessa suas reservas.
2. Seleciona cancelar.
3. O sistema remove a reserva.

### Fluxos Alternativos
- **A1 — Prazo expirado:**  
  Cancelamento não permitido.

### RF Relacionados
- RF06

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN03

<img width="242" height="257" alt="image" src="https://github.com/user-attachments/assets/3c022574-161b-40b7-aff3-97a8c6834c6e" />

---

## UC11 — Registrar Presença em Aula

### Ator Principal
Instrutor

### Objetivo
Registrar a presença dos alunos em uma aula.

### Pré-condições
- Aula cadastrada no sistema.

### Pós-condições
- Presença dos alunos registrada.

### Fluxo Principal
1. O instrutor acessa a lista da aula.
2. Visualiza os alunos inscritos.
3. Marca os alunos presentes.
4. O sistema salva a lista de presença.

### Fluxos Alternativos
- **A1 — Aluno não compareceu:**  
  O instrutor marca o aluno como ausente.

### RF Relacionados
- RF07

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN06

<img width="175" height="248" alt="image" src="https://github.com/user-attachments/assets/efed1ed6-dc21-4c2f-a33e-ff35aaece40a" />

---

## UC12 — Registrar Avaliação Física

### Ator Principal
Instrutor

### Objetivo
Registrar os dados da avaliação física do aluno.

### Pré-condições
- Aluno cadastrado e ativo no sistema.

### Pós-condições
- Avaliação física registrada.

### Fluxo Principal
1. O instrutor seleciona o aluno.
2. Informa dados como peso, altura e percentual de gordura.
3. O sistema salva a avaliação.

### Fluxos Alternativos
- **A1 — Aluno irregular:**  
  O sistema bloqueia o registro da avaliação.

### RF Relacionados
- RF08

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN05

<img width="263" height="257" alt="image" src="https://github.com/user-attachments/assets/d812c964-f265-44f8-9477-cb017f9616eb" />

---

## UC13 — Anexar Arquivo à Avaliação Física

### Ator Principal
Instrutor

### Objetivo
Adicionar arquivos ou documentos à avaliação física.

### Pré-condições
- Avaliação física existente.

### Pós-condições
- Arquivo anexado ao registro da avaliação.

### Fluxo Principal
1. O instrutor acessa a avaliação do aluno.
2. Seleciona a opção de anexar arquivo.
3. Faz upload do documento.
4. O sistema salva o arquivo.

### Fluxos Alternativos
- **A1 — Arquivo inválido:**  
  O sistema impede o upload.

### RF Relacionados
- RF08

### RNF Relacionados
- RNF02

### RN Relacionadas
- RN05

<img width="225" height="312" alt="image" src="https://github.com/user-attachments/assets/d44efed6-a865-4b5c-8ee6-b153b6dae546" />

---

## UC14 — Emitir Relatório de Inadimplência

### Ator Principal
Gerente

### Objetivo
Visualizar alunos com mensalidade em atraso.

### Pré-condições
- Gerente autenticado no sistema.

### Pós-condições
- Relatório exibido.

### Fluxo Principal
1. O gerente acessa a área de relatórios.
2. Seleciona relatório de inadimplência.
3. O sistema gera a lista de alunos com pagamentos atrasados.

### Fluxos Alternativos
- **A1 — Nenhum aluno inadimplente:**  
  O sistema informa que não há registros.

### RF Relacionados
- RF09

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN01

<img width="185" height="248" alt="image" src="https://github.com/user-attachments/assets/184814ee-dfe6-48ad-848f-df97948ae595" />

---

## UC15 — Emitir Relatório de Alunos Ativos

### Ator Principal
Gerente

### Objetivo
Consultar os alunos ativos no sistema.

### Pré-condições
- Gerente logado no sistema.

### Pós-condições
- Lista de alunos ativos exibida.

### Fluxo Principal
1. O gerente acessa o menu de relatórios.
2. Seleciona alunos ativos.
3. O sistema exibe a lista.

### Fluxos Alternativos
- **A1 — Nenhum aluno ativo:**  
  O sistema informa que não há registros.

### RF Relacionados
- RF09

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN06

<img width="185" height="248" alt="image" src="https://github.com/user-attachments/assets/4695c201-1231-475a-aad6-4c01ea43b7e8" />

---

## UC16 — Emitir Relatório de Acessos

### Ator Principal
Gerente

### Objetivo
Visualizar o histórico de entrada dos alunos na academia.

### Pré-condições
- Gerente autenticado.

### Pós-condições
- Relatório exibido.

### Fluxo Principal
1. O gerente acessa o menu de relatórios.
2. Seleciona histórico de acessos.
3. O sistema gera o relatório.

### Fluxos Alternativos
- **A1 — Falha na consulta:**  
  O sistema informa erro ao gerar o relatório.

### RF Relacionados
- RF09

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN01

<img width="185" height="248" alt="image" src="https://github.com/user-attachments/assets/e32eb6ec-1fb9-4ab3-983a-09abba403044" />

---

## UC17 — Emitir Relatório de Ocupação de Aulas

### Ator Principal
Gerente

### Objetivo
Analisar a quantidade de alunos em cada aula.

### Pré-condições
- Aulas cadastradas no sistema.

### Pós-condições
- Relatório de ocupação exibido.

### Fluxo Principal
1. O gerente acessa relatórios.
2. Seleciona ocupação das aulas.
3. O sistema apresenta os dados.

### Fluxos Alternativos
- **A1 — Nenhuma aula cadastrada:**  
  O sistema informa ausência de dados.

### RF Relacionados
- RF09

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN02

<img width="185" height="248" alt="image" src="https://github.com/user-attachments/assets/65ee074e-18b7-46b4-8fee-bb14bad87203" />

---

## UC18 — Enviar Notificação de Vencimento

### Ator Principal
Sistema

### Objetivo
Avisar o aluno sobre o vencimento da mensalidade.

### Pré-condições
- Mensalidade próxima do vencimento.

### Pós-condições
- Notificação enviada ao aluno.

### Fluxo Principal
1. O sistema identifica mensalidades próximas do vencimento.
2. O sistema envia uma notificação ao aluno.

### Fluxos Alternativos
- **A1 — Falha no envio:**  
  O sistema registra erro e tenta novamente.

### RF Relacionados
- RF10

### RNF Relacionados
- RNF01

### RN Relacionadas
- RN01

<img width="202" height="193" alt="image" src="https://github.com/user-attachments/assets/fe74444a-11ec-454c-ad27-a151abc16570" />


---

## UC19 — Enviar Confirmação de Agendamento

### Ator Principal
Sistema

### Objetivo
Confirmar ao aluno que o agendamento da aula foi realizado.

### Pré-condições
- Reserva de aula registrada.

### Pós-condições
- Notificação enviada ao aluno.

### Fluxo Principal
1. O sistema detecta um novo agendamento.
2. O sistema envia confirmação ao aluno.

### Fluxos Alternativos
- **A1 — Falha no envio:**  
  O sistema registra erro.

### RF Relacionados
- RF10

### RNF Relacionados
- RNF01

### RN Relacionadas
- RN02
<img width="175" height="193" alt="image" src="https://github.com/user-attachments/assets/489a11b7-f98c-4671-bba0-73be1502b638" />

---

## UC20 — Notificar Nova Avaliação Física

### Ator Principal
Sistema

### Objetivo
Informar ao aluno que uma nova avaliação física foi registrada.

### Pré-condições
- Avaliação física registrada pelo instrutor.

### Pós-condições
- Aluno recebe notificação.

### Fluxo Principal
1. O instrutor registra nova avaliação.
2. O sistema envia notificação ao aluno.

### Fluxos Alternativos
- **A1 — Falha no envio:**  
  O sistema registra erro e tenta novamente.

### RF Relacionados
- RF10

### RNF Relacionados
- RNF01

### RN Relacionadas
- RN05

<img width="187" height="193" alt="image" src="https://github.com/user-attachments/assets/c78ec9ad-82f4-4527-bc16-d5fcec9e6b06" />
