PROJETO INTEGRADOR — CONSOLIDAÇÃO DO 1º BIMESTRE

Curso: Engenharia de Software — UniCesumar

Tema: WebEducação — Plataforma de Aulas Particulares

Cenário Escolhido: Aulas particulares entre alunos e professores autônomos

Integrantes do Grupo
Lucas Vinícius Strachulski (Lider)

Jhuan Pablo Kobinski de Souza

Pedro Henrique Chaves

Felipe Fernandes Maximo

Identificação e Visão Geral do Sistema
A WebEducação é uma plataforma web criada para conectar alunos com dificuldade em disciplinas do curso de Engenharia de Software (como Cálculo e Estrutura de Dados) a outros estudantes dispostos a dar aulas particulares. O sistema permite que o professor cadastre suas matérias, valores e disponibilidade, enquanto o aluno pesquisa, filtra por preço, escolhe o melhor horário e realiza o agendamento com pagamento intermediado.

Modelo de Processo Adotado
O grupo optou pelo Modelo Incremental. A escolha se justifica porque os requisitos do agendamento e pagamento apresentavam volatilidade inicial. O modelo Incremental permitiu focar no MVP, reduzindo riscos e permitindo validações rápidas das telas em ciclos curtos com os próprios estudantes do campus.

Backlog do Produto em User Stories

ID  User Story  Prioridade

Usuario 01  Como aluno, quero filtrar professores por matéria e preço máximo, para achar ajuda dentro do meu orçamento.  (Alta)

Usuario 02  Como aluno, quero escolher um horário e pagar na hora, para garantir a reserva sem riscos.  (Alta)

Usuario 03  Como professor, quero cadastrar meus horários da semana, para organizar minha rotina e evitar aulas sobrepostas.  (Alta)

Usuario 04  Como professor, quero montar meu perfil com fotos e matérias, para atrair mais interessados.  (Alta)

Usuario 05  Como aluno, quero avaliar o professor após a aula, para ajudar outros colegas na escolha.  (Média)

Usuario 06  Como professor, quero dar nota de presença ao aluno, para registrar o compromisso e pontualidade.  (Média)

Usuario 07  Como aluno, quero receber confirmação e lembrete por e-mail, para não esquecer a aula.  (Média)

Usuario 08  Como professor, quero ver um painel financeiro com meus ganhos do mês, para ter controle dos valores a sacar.  (Baixa)

Sprint Simulada e Resultado
Objetivos da Sprint: Entregar o fluxo completo de busca, reserva e pagamento com bloqueio de agenda.
Histórias Selecionadas: Usuario 01, Usuario 02 e Usuario 03.
Resultado da Review: Desenho da tela de busca funcional, calendário com validação de conflito de horários e tela de checkout simulada atualizando o status da reserva para Confirmada.

Plano de Testes e Qualidade
Para as histórias Usuario 01 e Usuario 02, aplicam-se Testes de Sistema e Testes de Aceitação.

Módulo 1: Busca de Professores (Usuario 01)
Cenário 1.1: Dado que estou na tela de busca, Quando pesquiso por Estrutura de Dados até R$ 70,00, Então o sistema exibe os professores que atendem a esses critérios.
Cenário 1.2: Dado que pesquiso por Cálculo 3 até R$ 15,00, Quando clico em buscar, Então o sistema exibe a mensagem "Nenhum professor encontrado para esse valor ou matéria".

Módulo 2: Agendamento e Pagamento (Usuario 02)
Cenário 2.1: Dado que escolhi um horário vago, Quando preencho os dados do cartão e confirmo, Então o pagamento é aprovado, a aula muda para Confirmada e o horário é removido da agenda pública.
Cenário 2.2: Dado que selecionei um horário, Quando o pagamento é recusado, Então o sistema exibe aviso de falha e segura a vaga por 5 minutos antes de reabri-la.

Atributos de Qualidade Críticos
Usabilidade: Essencial para que alunos e professores achem horários e concluam reservas com poucos cliques.
Confiabilidade: O sistema precisa garantir o bloqueio exato de horários para impedir reservas duplas no mesmo slot.

Análise Ética e de Privacidade

Risco  Descrição  Mitigação Proposta

Coleta excessiva de dados (LGPD)  Vazamento de informações sensíveis ou dados bancários de alunos.  Solicitar apenas dados básicos (nome, e-mail institucional), criptografar senhas e processar pagamentos via gateway externo.

Fraude acadêmica  Alunos contratarem professores para realizar provas ou trabalhos por eles.  Inserir cláusula expressa nos termos de uso proibindo realização de atividades avaliativas e criar canal de denúncia.

Ausência de serviço pago  Professor receber o dinheiro e não comparecer ao horário marcado.  Retenção do valor pelo sistema, realizando o repasse ao professor apenas após a confirmação da aula.
