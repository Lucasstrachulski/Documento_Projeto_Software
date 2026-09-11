3. Backlog do produto expandida
Tabela do backlog com user stories

ID	                  User Story	                                                                                                                                   Prioridade

usuario01	               Como aluno, quero buscar professores por disciplina e valores preço,                                                                          
                         para encontrar um educador compatível com meu orçamento e necessidade.	                                                                          Alta


usuario02	               Como aluno, quero agendar e fazer o pagamento da minha aula, para garantir a reserva do meu horário                                             
                         com segurança.                                                                                                                                  Alta


usuario03	               Como professor, quero cadastrar minha grade de horários, para evitar                                                                            
                         dois ou mais agendamentos no mesmo horário.                                                                                                     Alta


usuario04	               Como professor, quero fazer um perfil completo com matérias, e valores, para chamar mais alunos .                                               Alta


usuario05	               Como aluno, quero avaliar o professor depois da aula, para ajudar outros estudantes na escolha de bons professores.                            Média


usuario06	               Como professor, quero registrar um feedback sobre o aluno, para manter o histórico de conduta e comprometimento.	                              Média


usuario07	               Como aluno, quero receber notificações sobre confirmações, cancelamentos e lembretes de aula,                                                  
                         para não perder os horários agendados.	                                                                                                        Média


usuario08	               Como professor, quero visualizar o relatório mensal dos rendimentos das minhas aulas, para ter                                                 Baixa
                         controle financeiro dos meus ganhos.	


4- Planos de testes e qualidade
Tipos de testes
Testes de unidade: testar coisas que ficam isoladas no sistemas um por um, como cálculo do valor da aula por exemplo.

Testes de usabilidade: ver se coisas que precisam funcionar juntas estão funcionando certo, como o agendamento e o pagamento.

Testes sistema e aceitação: ver se o programa está funcionando perfeitamente tanto pro professor quanto pro aluno.

Testes:
User story escolhidos:
usuario01 e usuario02.

usuario01 – Buscar professores por disciplina e faixa de preço
User Story: Como aluno, quero buscar professores por disciplina e faixa de preço, para encontrar um educador compatível com meu orçamento e necessidade.

Testes:

Unitário: ver se a função responsável pelo filtro de busca da os dados corretamente como por exemplo apenas os professores que ensinam a matéria escolhida e o valor da aula

Integração: ver se a busca feita pelo aluno traz corretamente os dados do perfil do professor do banco de dados.

Sistema: ver se o sistema traz certa a busca do aluno por preço e matéria por completo.

Aceitação: ver se o aluno consegue ver e usar o sistema com facilidade e ver a lista de professores filtrados e seus valores.

Critérios de aceite
Critério 1:
Se existem professores cadastrados com a disciplina de português por exemplo com valor de 40 reais por hora, quando o aluno filtrar por português e preço máximo de 50 reais, então o sistema tem que mostrar a lista com esses professores.

Critério 2:
Se o professor tem o valor maior que o que o aluno filtrou, ele não vai aparecer na pesquisa.


usuario02 – Agendar e realizar o pagamento de uma aula online
User Story: Como aluno, quero agendar e realizar o pagamento de uma aula online, para garantir a reserva do meu horário com segura 

testes:
Unitário: ver se a função que faz o processamento do pagamento e criação da reserva salva e atualiza certo o agendamento.

Integração: ver se a confirmação do pagamento se junta com o agendamento e atualiza a agenda do professor.

Sistema: checar todo o processo, desde a escolha do horário e preenchimento dos dados do pagamento até a confirmação da aula.

Aceitação: ver se o aluno consegue realizar a compra e o agendamento da aula sem dificuldades.


Critérios de aceite :

Critério 1:
Se o aluno escolheu um horário disponível e colocou dados válidos de pagamento, quando ele confirmar a compra, então o sistema tem que registrar a aula como agendada e mostrar uma mensagem de confirmação de sucesso.

Critério 2:
Se uma aula foi agendada e paga para certo horário, quando outro aluno ver a os horários do mesmo professor, o horário reservado não pode estar disponível para compra.
