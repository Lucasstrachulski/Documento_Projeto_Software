PROJETO INTEGRADOR — CONSOLIDAÇÃO DO 1º BIMESTRE

Curso: Engenharia de Software — UniCesumar
Tema / Sistema: WebEducação — Plataforma de Aulas Particulares
Cenário Escolhido: Cenário J Aulas particulares entre alunos e professores autônomos

Integrantes do Grupo

Lucas Vinícius Strachulski Lider do Grupo

Jhuan Pablo Kobinski de Souza

Pedro Henrique Chaves

Felipe Fernandes Maximo

Apresentação do Sistema
A WebEducação nasceu pra resolver um problema bem comum na UniCesumar: a dificuldade de achar monitores ou professores particulares pra matérias mais pesadas (tipo Cálculo, Estrutura de Dados ou Física). Do outro lado, quem quer dar aula também sofre pra organizar a agenda e receber pelo serviço.

A ideia é ser um ponto de encontro simples. O professor se cadastra, coloca as matérias que domina, o preço da hora/aula e marca na agenda os horários livres. O aluno entra, pesquisa a matéria, ajusta o filtro pro valor que cabe no bolso, escolhe o horário e reserva. Pra ninguém levar calote ou furar a aula, o pagamento é feito direto pela plataforma.

Por que escolhemos o Desenvolvimento Incremental?
A gente conversou e achou melhor ir pelo modelo Incremental (Ágil). Fazer tudo no modelo Cascata (aquele tradicional e travado) não ia dar certo por alguns motivos bem práticos:

As ideias mudavam toda hora: Conforme a gente desenhava como o sistema ia funcionar, percebia que o fluxo de agendamento precisava de ajustes. Se ficasse travado no papel antes de codar, a gente ia ter que refazer tudo do zero depois.

Foco no principal MVP: Decidimos focar o primeiro ciclo só no básico pra rodar: achar o professor, agendar e validar o pagamento. Funcionando isso, as outras coisas (tipo chat e relatórios) entram nas próximas entregas.

Testar rápido com o pessoal: Entregando em ciclos curtos, dá pra mostrar as telas funcionando prós próprios colegas e ver se tá fácil de usar antes de ir mais fundo.

Backlog do Produto e Divisão das Tarefas

4.1. Histórias de Usuário User Stories
Aqui tá o que a gente mapeou que o sistema precisa ter:

Usuario 01 Prioridade Alta — Filtro de Busca por Matéria e Preço

Como: Aluno

Eu quero: Filtrar professores por matéria e preço máximo.

Para que: Achar alguém pra me ajudar na matéria sem estourar o orçamento.

O que precisa ter: Campo de busca por texto e um filtro de preço limite.

Usuario 02 Prioridade Alta — Escolha de Horário e Pagamento Imediato

Como: Aluno

Eu quero: Escolher o horário vago e já pagar a aula na hora.

Para que: Garantir a vaga no horário sem correr o risco de perder pra outro.

O que precisa ter: Travar o horário na agenda e mudar o status assim que o pagamento passar.

Usuario 03 Prioridade Alta — Gestão da Agenda do Professor

Como: Professor

Eu quero: Cadastrar e mexer nos meus horários da semana.

Para que: Organizar minha rotina e não marcar duas aulas no mesmo horário.

O que precisa ter: O sistema não pode deixar salvar dois horários encavalados no mesmo dia.

Usuario 04 Prioridade Alta — Perfil do Professor

Como: Professor

Eu quero: Montar meu perfil com matérias, preços e minha formação.

Para que: Passar confiança pros alunos e fechar mais aulas.

O que precisa ter: Foto, biografia rápida e a lista das matérias que ensino.

Usuario 05 Prioridade Média — Avaliação do Professor pelo Aluno

Como: Aluno

Eu quero: Dar uma nota e deixar um comentário depois da aula.

Para que: Ajudar outros alunos a saberem se o professor manda bem.

O que precisa ter: Liberar a avaliação só depois que o horário da aula terminar.

Usuario 06 Prioridade Média — Avaliação do Aluno pelo Professor

Como: Professor

Eu quero: Dar uma nota de presença pro aluno.

Para que: Deixar registrado se o aluno foi pontual e de boa na aula.

O que precisa ter: Campo de nota de 1 a 5 no histórico de aulas do professor.

Usuario 07 Prioridade Média — Lembretes e Notificações por E-mail

Como: Aluno

Eu quero: Receber e-mail confirmando a aula e me lembrando do horário.

Para que: Eu não esqueça do compromisso.

O que precisa ter: Disparo de e-mail assim que agenda e outro 2 horas antes de começar.

Usuario 08 Prioridade Baixa — Painel Financeiro do Professor

Como: Professor

Eu quero: Ver um resumo de quanto ganhei no mês.

Para que: Saber quanto tenho liberado pra sacar.

O que precisa ter: Tela mostrando o total líquido e o histórico das aulas pagas.

Usuario 09 Prioridade Baixa — Chat de Dúvidas Pós-Aula

Como: Aluno

Eu quero: Mandar mensagem pro professor depois que a aula fechar.

Para que: Tirar alguma dúvida rápida sobre a aula.

O que precisa ter: Chat simples atrelado àquela aula específica.

4.2. O que fizemos na Sprint Simulada
Pra testar o primeiro ciclo Sprint, a gente pegou as três tarefas mais importantes (Usuario 01, Usuario 02 e Usuario 03), que cobrem o caminho principal do uso.

Meta da Sprint: Deixar o fluxo completo rodando: da busca da aula até a confirmação do pagamento com o bloqueio da agenda.

O que a gente fez e testou:

Montamos a tela de busca onde o aluno pesquisa a matéria tipo Algoritmos e limita o preço máximo ex: até R$ 60.

Criamos a lógica do calendário pra permitir cadastrar horários sem deixar dar choque de agenda.

Fizemos a tela de checkout simulada, que valida o cartão e muda a aula de Pendente pra Confirmada.

Resultado do teste: Deu pra simular certinho o aluno reservando a aula de um professor de teste sem dar nenhum erro de conflito na agenda.

Testes do Sistema Escritos em Gherkin / BDD
Pra ter certeza que tudo vai funcionar na prática, montamos os cenários de teste pensando no dia a dia.

Módulo 1: Busca de Professores Usuario 01

Cenário 1.1: Busca normal com filtros
Dado que estou na tela de busca
E digito Estrutura de Dados no campo de pesquisa
E coloco o valor máximo de R$ 70,00
Quando clico em Buscar
Então o sistema mostra a lista de professores de Estrutura de Dados que cobram até R$ 70,00 por hora.

Cenário 1.2: Quando não acha ninguém no filtro
Dado que pesquiso por Cálculo 3
E coloco o preço máximo de R$ 15,00
Quando clico em Buscar
Então o sistema avisa Nenhum professor encontrado para esse valor ou matéria
E dá a opção de limpar os filtros.

Cenário 1.3: Digitando valor inválido no filtro
Dado que estou na tela de busca
E coloco letras ou números negativos no preço máximo
Quando tento buscar
Então o sistema avisa que o valor tá errado e pede pra corrigir.

Módulo 2: Agendamento e Pagamento Usuario 02

Cenário 2.1: Agendando e pagando com sucesso
Dado que escolhi a aula de Estrutura de Dados com o professor Carlos pra quinta-feira às 15:00
E estou na tela de pagamento
Quando preencho o cartão certinho e clico em Pagar e Confirmar
Então o sistema aprova o pagamento
E muda o status da aula pra Confirmada
E tira o horário das 15:00 da lista de horários livres do professor.

Cenário 2.2: Cartão recusado ou sem saldo
Dado que escolhi um horário na agenda
E tentei pagar com um cartão recusado
Quando o sistema tenta cobrar
Então ele mostra a mensagem Pagamento não aprovado. Tente outro cartão
E segura a vaga por 5 minutos antes de devolver pra agenda pública.

Cenário 2.3: Aluno cancelando a aula com antecedência
Dado que tenho uma aula confirmada pra daqui a 3 dias
E entro em Minhas Aulas e clico em Cancelar Aula
Quando confirmo o cancelamento
Então o sistema cancela a reserva
E avisa que o dinheiro vai ser devolvido
E libera o horário de novo na agenda do professor.

Módulo 3: Agenda do Professor e Bloqueio de Choques Usuario 03

Cenário 3.1: Cadastrando novo horário livre
Dado que entrei no meu painel de professor
E escolho a data de amanhã no horário das 09:00 às 10:00
Quando clico em Salvar Horário
Então o sistema salva a disponibilidade e ela começa a aparecer na busca pros alunos.

Cenário 3.2: Tentando cadastrar dois horários no mesmo horário
Dado que já tenho um horário das 14:00 às 15:00 no dia 15/10
Quando tento cadastrar outro das 14:30 às 15:30 no mesmo dia
Então o sistema não deixa salvar e avisa Você já possui uma disponibilidade cadastrada nesse mesmo intervalo.

Cenário 3.3: Dois alunos tentando a mesma vaga ao mesmo tempo
Dado que o Aluno A e o Aluno B estão com o mesmo horário das 16:00 aberto no pagamento
Quando o Aluno A clica em pagar e a transação passa um segundo antes do Aluno B
Então o Aluno A garante a vaga
E o Aluno B recebe o aviso Este horário acabou de ser reservado por outro usuário e a cobrança é cancelada.

Cuidados Éticos, Regras e Privacidade
A gente alinhou alguns pontos essenciais pra plataforma rodar sem quebrar regras da faculdade ou leis de privacidade:

Cuidado com a LGPD: Nada de pedir dado à toa. O cadastro pede só nome, e-mail da faculdade, telefone e senha (que fica criptografada). Dados de cartão não ficam salvos no nosso banco, vão direto pelo gateway de pagamento.

Proibido cola ou fraude: A plataforma é estritamente pra aulas particulares, explicação de matéria e tirar dúvidas. Vamos deixar bem claro nos termos de uso que é proibido contratar gente pra fazer trabalho ou prova no lugar de aluno.

Garantia do pagamento: Pra evitar calote dos dois lados, o dinheiro só vai pro professor depois que a aula for marcada como realizada no sistema.

Conclusão do Grupo
Fazer esse relatório do 1º Bimestre ajudou muito a gente a entender como organizar um projeto de software desde a fase de ideias. Conseguimos montar um backlog realista, definir o MVP e testar na prática.

O formato BDD ajudou bastante a enxergar a plataforma pela visão do usuário, o que evitou vários furos nas regras de negócio. O grupo tá bem alinhado e pronto pras próximas etapas, onde vamos desenhar a arquitetura e os protótipos das telas.
