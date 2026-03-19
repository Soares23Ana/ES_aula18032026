# CASOS DE USO COM DIAGRAMAS: 
- Diagrama: 
<img width="680" height="1538" alt="DUC_ThalesTardelli_GabrielSartorio (1)" src="https://github.com/user-attachments/assets/c2c970ca-350d-4ede-b9fb-ce14dde4a174" />

---

## UC01 - Realizar Login

### Ator Principal: 
- Usuário (Aluno, Recepcionista, Instrutor ou Gerente)

### Objetivo: 
Permitir acesso ao sistema de acordo com o perfil.

### Pré-condições: 
- Usuário cadastrado e ativo.

### Pós-condições: 
Sessão iniciada.

### Fluxo Principal: 
1. Usuário insere e-mail e senha; 
2. Sistema valida credenciais; 
3. Sistema redireciona conforme perfil (RN06).

### Requisitos Relacionados 
RF: RF01 
RNF: RNF02 
RN: RN06

<img width="428" height="336" alt="uc01" src="https://github.com/user-attachments/assets/70806b9b-4581-4671-8c3e-1e3b41512c08" />

---

## UC02 - Cadastrar Aluno

### Ator Principal: 
- Recepcionista

### Objetivo: 
Registrar novo aluno e vincular plano.

### Pré-condições: 
- Recepcionista logado.

### Pós-condições: 
- Aluno salvo no banco de dados.

### Fluxo Principal: 
1. Informar dados pessoais; 
2. Selecionar plano (RF02); 
3. Vincular tag RFID; 
4. Salvar.

### Requisitos Relacionados 
RF: RF01, RF02
RNF: RNF03, RNF04
RN: RN06

<img width="262" height="357" alt="uc02" src="https://github.com/user-attachments/assets/7bdc0f84-a15b-48bf-8570-eb17db76c10b" />

---

## UC03 - Gerenciar Planos (Criar/Editar)

### Ator Principal: 
- Gerente

### Objetivo: 
Configurar as opções de planos da academia.

### Pré-condições: 
- Gerente logado.

### Pós-condições: 
- Plano disponível para venda.

### Fluxo Principal: 
1. Definir nome, valor e duração; 
2. Salvar configuração.

### Requisitos Relacionados 
RF: RF02 
RNF: RNF04 
RN: RN06

<img width="279" height="302" alt="uc03" src="https://github.com/user-attachments/assets/6d602d7a-94e6-499f-8cfd-a077083f4ea7" />

---

## UC04 - Registrar Pagamento (Presencial)

### Ator Principal: 
- Recepcionista

### Objetivo: 
Quitar débitos de mensalidade.

### Pré-condições: 
Aluno selecionado.

### Pós-condições: 
Status financeiro atualizado para "Regular".

### Fluxo Principal: 
1. Selecionar parcela; 
2. Escolher forma de pagamento; 
3. Confirmar valor integral (RN04); 
4. Sistema atualiza status (RN07).

### Requisitos Relacionados 
RF: RF03, RF04 
RNF: RNF03 
RN: RN04, RN07

<img width="587" height="421" alt="uc04" src="https://github.com/user-attachments/assets/faef493f-624c-4412-995d-ee009c4cc759" />

---

## UC05 - Gerar Cobrança Online

### Ator Principal: 
- Recepcionista / Sistema

### Objetivo: 
Emitir boletos ou links de pagamento.

### Pré-condições: 
- Aluno com plano ativo.

### Pós-condições: 
- Cobrança enviada ao aluno.

### Fluxo Principal: 
1. Sistema gera fatura mensal; 
2. Disponibiliza link/boleto.

### Requisitos Relacionados 
RF: RF03 
RNF: RNF05 
RN: RN04

<img width="303" height="247" alt="uc05" src="https://github.com/user-attachments/assets/f6033291-33dc-4d1d-b11b-ffda1a75c25e" />

---

## UC06 - Validar Acesso na Catraca

### Ator Principal: 
- Sistema de Catraca (API)

### Objetivo: 
Liberar entrada física.

### Pré-condições: 
- Aluno aproximar RFID.

### Pós-condições: 
- Acesso liberado ou negado.

### Fluxo Principal: 
1. Leitura do RFID; 
2. Sistema verifica carência de 5 dias (RN01); 
3. Libera giro se regular.

### Requisitos Relacionados 
RF: RF04, RF05 
RNF: RNF03, RNF06 
RN: RN01

<img width="448" height="366" alt="uc06" src="https://github.com/user-attachments/assets/68634507-667a-4ee9-8f88-3a78bc0bf76b" />

---

## UC07 - Visualizar Grade de Aulas

### Ator Principal: 
- Aluno

### Objetivo: 
Ver horários disponíveis.

### Pré-condições: 
- Aluno logado.

### Pós-condições: 
Lista de aulas exibida.

### Fluxo Principal: 
1. Acessar menu "Aulas"; 
2. Filtrar por data/modalidade.

### Requisitos Relacionados 
RF: RF06 
RNF: RNF04 
RN: -

<img width="257" height="247" alt="uc07" src="https://github.com/user-attachments/assets/22e8ae59-66e0-4946-accf-c21c2f470d84" />

---

## UC08 - Realizar Agendamento de Aula

### Ator Principal: 
- Aluno

### Objetivo: 
Reservar vaga em aula coletiva.

### Pré-condições: 
- Aluno regular e aula com vagas.

### Pós-condições: 
- Vaga reservada.

### Fluxo Principal: 
1. Selecionar aula; 
2. Confirmar reserva; 
3. Sistema valida limite (RN02).

### Requisitos Relacionados:

RF: RF06 
RNF: RNF04
RN: RN02

<img width="486" height="366" alt="uc08" src="https://github.com/user-attachments/assets/46d13cc5-2975-45fc-8c9f-097d1dba8fc7" />

---

## UC09 - Cancelar Agendamento

### Ator Principal: 
- Aluno

### Objetivo: 
Desistir da vaga reservada.

### Pré-condições: 
- Prazo de 1 hora de antecedência (RN03).

### Pós-condições: 
- Vaga liberada para outros.

### Fluxo Principal: 
1. Selecionar aula agendada; 
2. Clicar em cancelar; 
3. Sistema valida tempo limite.

### Requisitos Relacionados:

RF: RF06 
RNF: RNF03 
RN: RN03

<img width="514" height="311" alt="uc09" src="https://github.com/user-attachments/assets/e0f11276-eb1a-4e00-aa8b-11c3725a882d" />

---

## UC10 - Lançar Presença em Aula

### Ator Principal: 
- Instrutor

### Objetivo: 
Registrar quem compareceu à aula.

### Pré-condições: 
- Instrutor logado e aula iniciada.

### Pós-condições: 
- Lista de presença salva.

### Fluxo Principal: 
1. Listar alunos agendados; 
2. Marcar presença.

### Requisitos Relacionados:

RF: RF07 
RNF: RNF04 
RN: RN06

<img width="329" height="400" alt="uc10" src="https://github.com/user-attachments/assets/81f9cf61-1436-4696-a5dc-2dc640b0b6ce" />

---

## UC11 - Realizar Avaliação Física

### Ator Principal: 
- Instrutor

### Objetivo: 
Registrar medidas e bioimpedância.

### Pré-condições: 
- Aluno ativo e regular (RN05).

### Pós-condições: 
- Avaliação salva e disponível para o aluno.

### Fluxo Principal: 
1. Inserir peso, IMC, gordura; 
2. Anexar arquivos; 
3. Salvar.

### Requisitos Relacionados:

RF: RF08 
RNF: RNF02 
RN: RN05, RN06

<img width="635" height="366" alt="uc11" src="https://github.com/user-attachments/assets/a34531e1-b975-4277-ae63-ae170cbb7feb" />

---

## UC12 - Consultar Avaliação Física

### Ator Principal: 
- Aluno

### Objetivo: 
Acompanhar evolução física.

### Pré-condições: 
- Avaliação realizada previamente.

### Pós-condições: 
- Visualização do progresso.

### Fluxo Principal: 
1. Acessar menu "Saúde"; 
2. Abrir PDF/Gráfico da avaliação.

### Requisitos Relacionados:

RF: RF08 
RNF: RNF04 
RN: -

<img width="250" height="247" alt="uc12" src="https://github.com/user-attachments/assets/534f46b4-be42-4f66-8628-efb814ed2f16" />

---

## UC13 A UC16 - Emitir Relatório de Inadimplência

### Ator Principal: 
- Gerente

### Objetivo: 
Identificar alunos com pagamentos atrasados.

### Pré-condições: 
- Gerente logado.

### Pós-condições: 
- Relatório gerado em tela/PDF.

### Fluxo Principal: 
1. Filtrar período; 
2. Sistema lista alunos com débito.

### Requisitos Relacionados: 

RF: RF09 
RNF: RNF03 
RN: RN06

<img width="283" height="450" alt="uc13_14_15_16" src="https://github.com/user-attachments/assets/7a53327a-2b1c-4b70-bb5a-31b7383cb4f6" />

---

## UC17 - Notificar Vencimento de Mensalidade

### Ator Principal: 
- Sistema (Automático)

### Objetivo: 
Alertar o aluno antes do bloqueio.

### Fluxo Principal: 
1. Verificar data de vencimento; 
2. Enviar push/e-mail.

### Requisitos Relacionados: 

RF: RF10 
RNF: RNF05 
RN: RN01

<img width="258" height="247" alt="uc17" src="https://github.com/user-attachments/assets/0b1572a6-9a4c-456b-a745-9429ce90aadb" />

---

## UC18 - Notificar Confirmação de Agendamento

### Ator Principal: 
- Sistema (Automático)

### Objetivo: 
Confirmar que a reserva foi feita com sucesso.

### Fluxo Principal: 
1. Após UC08, enviar notificação.

### Requisitos Relacionados: 

RF: RF10 
RNF: RNF01 
RN: -

<img width="277" height="247" alt="uc18" src="https://github.com/user-attachments/assets/8384599a-2417-44d6-95b4-084ebcfcda18" />

---

## UC19 - Atualizar Cadastro de Aluno

### Ator Principal: 
- Recepcionista

### Objetivo: 
Alterar endereço ou telefone.

### Fluxo Principal: 
1. Buscar aluno; 
2. Editar campos; 
3. Salvar.

### Requisitos Relacionados: 

RF: RF01 
RNF: RNF02 
RN: RN06

<img width="199" height="302" alt="uc19" src="https://github.com/user-attachments/assets/d2d7431c-9169-4c43-bad3-84ec4004092c" />

---

## UC20 - Inativar Plano

### Ator Principal: 
- Gerente

### Objetivo: 
Retirar plano de circulação sem excluir histórico.

### Fluxo Principal: 
1. Selecionar plano; 
2. Marcar como "Inativo".

### Requisitos Relacionados: 

RF: RF02 
RNF: RNF03 
RN: RN06

<img width="498" height="247" alt="uc20" src="https://github.com/user-attachments/assets/626227fd-7d6f-4e97-bc5c-1b0469d3a189" />




