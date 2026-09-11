PROJETO INTEGRADOR — CONSOLIDAÇÃO DO 1º BIMESTRE

Curso: Engenharia de Software — UniCesumar

Tema / Sistema: WebEducação — Plataforma de Aulas Particulares

Cenário Escolhido: Cenário J Aulas particulares entre alunos e professores autônomos

Integrantes do Grupo

Lucas Vinícius Strachulski (Lider)

Jhuan Pablo Kobinski de Souza

Pedro Henrique Chaves

Felipe Fernandes Maximo

Apresentação do Sistema

A WebEducaçao conecta alunos com dificuldade em matérias pesadas como Cálculo ou Estrutura de Dados a colegas dispostos a dar aulas particulares. O professor cadastra matérias, valores e horários vagos; o aluno busca, filtra por preço, reserva e paga pela própria plataforma pra evitar calotes ou faltas.

Por que escolhemos o Desenvolvimento Incremental?

Optamos pelo modelo Incremental (Ágil) em vez do Cascata porque as ideias mudavam direto no início. Esse modelo permite focar no MVP, testar as telas rápido com outros alunos e fazer ajustes sem precisar refazer o projeto do zero.

Backlog do Produto (User Stories)

Usuario 01 (Alta): Filtro de busca por matéria e valor limite por hora.

Usuario 02 (Alta): Escolha do horário vago com pagamento e bloqueio imediato da vaga.

Usuario 03 (Alta): Gestão de agenda do professor impedindo horários duplicados.

Usuario 04 (Alta): Perfil do professor com foto, bio e matérias lecionadas.

Usuario 05 (Média): Avaliação e comentário do professor pelo aluno pós-aula.

Usuario 06 (Média): Nota de presença de 1 a 5 dada pelo professor ao aluno.

Usuario 07 (Média): Envio de e-mail de confirmação e lembrete 2h antes da aula.

Usuario 08 (Baixa): Painel financeiro do professor mostrando saldo acumulado.

Usuario 09 (Baixa): Chat simples pós-aula para tirar dúvidas rápidas.


Sprint Simulada

Testamos as histórias Usuario 01, Usuario 02 e Usuario 03. Montamos a busca com filtro, o calendário sem conflito de horários e o checkout simulado que altera o status da aula para Confirmada. O fluxo completo rodou sem erros.

Testes do Sistema

Módulo 1: Busca de Professores Usuario 01

Cenário 1.1: Busca traz professores da matéria até o valor estipulado.

Cenário 1.2: Exibe aviso e opção de limpar filtro quando não encontra resultados.

Cenário 1.3: Exibe alerta ao digitar letras ou valores negativos no preço.

Módulo 2: Agendamento e Pagamento Usuario 02

Cenário 2.1: Pagamento aprovado confirma a aula e remove o horário da agenda pública.

Cenário 2.2: Cartão recusado segura o horário por 5 minutos antes de liberar pro público.

Cenário 2.3: Cancelamento prévio faz o estorno e reabre o horário na agenda do professor.

Módulo 3: Agenda do Professor Usuario 03

Cenário 3.1: Novo horário salvo com sucesso fica disponível na busca.

Cenário 3.2: Sistema bloqueia tentativa de salvar dois horários sobrepostos no mesmo dia.

Cenário 3.3: Em tentativa simultânea de compra, o pagamento aprovado primeiro garante a vaga e cancela a cobrança do outro.

Cuidados Éticos e Privacidade

LGPD: Coleta apenas dados básicos (senha criptografada) e cartão processado via gateway seguro.

Regras de Uso: Proibido o uso da plataforma para fraude em provas ou trabalhos.

Retenção do Pagamento: Repasse ao professor apenas após a realização confirmada da aula.
