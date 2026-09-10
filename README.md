PROJETO INTEGRADOR — CONSOLIDAÇÃO DO 1º BIMESTRE
Curso: Engenharia de Software — UniCesumar
Tema / Sistema: WebEducação — Plataforma de Aulas Particulares
Cenário Escolhido: Cenário J (Aulas particulares entre alunos e professores autônomos)
1. Integrantes do Grupo
Lucas Vinícius Strachulski (Líder do Grupo)
Jhuan Pablo Kobinski de Souza
Pedro Henrique Chaves
Felipe Fernandes Maximo
2. Apresentação do Sistema
A ideia da WebEducação surgiu para resolver um problema bem comum no campus da UniCesumar: a dificuldade que muitos alunos têm para encontrar monitores ou professores particulares de matérias específicas (como Cálculo, Estrutura de Dados ou Física) e, do outro lado, a falta de uma forma simples para os alunos que querem dar aula organizarem seus horários e receberem pelo serviço.
A plataforma vai funcionar como um ponto de encontro simples e direto. O professor entra, cadastra as matérias que domina, coloca o valor da sua hora/aula e marca na agenda quais dias e horários está livre. O aluno entra, pesquisa pela matéria que está precisando de ajuda, ajusta o filtro de preço de acordo com o bolso dele, escolhe o melhor horário e faz a reserva. Para que ninguém leve calote ou reserve horário e não apareça, o pagamento é intermediado pela própria plataforma.
3. Por que escolhemos o Desenvolvimento Incremental?
Conversando sobre como poderíamos tocar o projeto, decidimos seguir o modelo Incremental (Ágil). Não faria sentido usar um modelo tradicional e engessado (como o Cascata) pelos seguintes motivos práticos que vimos durante as discussões do grupo:
Mudanças constantes de ideias: Conforme desenhávamos os fluxos do sistema, percebemos que a forma de agendar aulas mudava toda hora. Se fôssemos fechar todos os requisitos no papel antes de codificar, teríamos que refazer o projeto inteiro mais tarde.
Foco no que importa de verdade (MVP): Preferimos concentrar o primeiro ciclo naquilo que o sistema precisa ter para funcionar o básico: achar o professor, agendar o horário e validar o pagamento. Tendo isso pronto, o resto (como chat ou relatórios) a gente adiciona nas entregas seguintes.
Validação rápida com outros alunos: Com entregas menores em ciclos curtos, conseguimos mostrar telas funcionais mais rápido para os próprios colegas de curso e ver se a usabilidade está boa antes de avançar.
4. Backlog do Produto e Divisão das Tarefas
4.1. Histórias de Usuário (User Stories)
Abaixo estão detalhadas as histórias de usuário levantadas pelo grupo para o desenvolvimento da plataforma:
US01 (Prioridade Alta) — Filtro de Busca por Matéria e Preço
Como: Aluno
Eu quero: Filtrar professores por matéria e por valor limite por hora.
Para que: Achar alguém que me ajude na matéria que preciso sem gastar mais do que posso.
O que precisa ter: Ter campo de busca de texto para a disciplina e um seletor/filtro de valor máximo.
US02 (Prioridade Alta) — Escolha de Horário e Pagamento Imediato
Como: Aluno
Eu quero: Escolher o horário vago e pagar a aula na hora.
Para que: Garantir que aquele horário é meu e não ser passado pra trás.
O que precisa ter: Bloquear a agenda e mudar o status da reserva assim que o pagamento for aprovado.
US03 (Prioridade Alta) — Gestão da Agenda do Professor
Como: Professor
Eu quero: Cadastrar e editar meus horários de aula da semana.
Para que: Organizar minha rotina de estudos e não ter duas aulas marcadas no mesmo horário.
O que precisa ter: Não permitir salvar horários que se sobrepõem no mesmo dia.
US04 (Prioridade Alta) — Perfil do Professor
Como: Professor
Eu quero: Montar meu perfil com minhas matérias, preços e formação.
Para que: Passar confiança pros alunos e atrair mais interessados.
O que precisa ter: Campos de foto, biografia curta e lista de matérias lecionadas.
US05 (Prioridade Média) — Avaliação do Professor pelo Aluno
Como: Aluno
Eu quero: Deixar uma nota e um comentário depois da aula.
Para que: Ajudar outros alunos a saberem se o professor explica bem.
O que precisa ter: Liberar a opção de avaliar somente após o horário da aula ter terminado.
US06 (Prioridade Média) — Avaliação do Aluno pelo Professor
Como: Professor
Eu quero: Dar uma nota de presença pro aluno.
Para que: Registrar se o aluno foi pontual e respeitoso durante a aula.
O que precisa ter: Campo simples de nota de 1 a 5 no histórico de aulas do professor.
US07 (Prioridade Média) — Lembretes e Notificações por E-mail
Como: Aluno
Eu quero: Receber e-mails confirmando a aula e lembrando do horário.
Para que: Não esquecer do compromisso no dia da aula.
O que precisa ter: Envio de e-mail na hora que agenda e 2 horas antes de começar.
US08 (Prioridade Baixa) — Painel Financeiro do Professor
Como: Professor
Eu quero: Ver um resumo de quanto ganhei no mês.
Para que: Saber quanto tenho para sacar das aulas que já dei.
O que precisa ter: Tela mostrando o total líquido acumulado e histórico de aulas pagas.
US09 (Prioridade Baixa) — Chat de Dúvidas Pós-Aula
Como: Aluno
Eu quero: Mandar mensagem pro professor depois que a aula acabar.
Para que: Tirar alguma dúvida rápida sobre o que foi visto.
O que precisa ter: Caixa de mensagem simples vinculada àquela aula específica.
4.2. O que fizemos na Sprint Simulada
Para simular o primeiro ciclo de entrega (Sprint), pegamos as três histórias mais importantes do sistema (US01, US02 e US03), que formam o fluxo completo de uso da plataforma.
Meta da Sprint: Deixar o fluxo principal funcionando: desde a busca da aula pelo aluno até a confirmação do pagamento com bloqueio do horário na agenda.
O que foi desenvolvido e testado no grupo:
Desenhamos a tela de busca onde o aluno digita a matéria (ex: "Algoritmos") e limita o valor máximo (ex: até R$ 60).
Montamos a lógica do calendário do professor para permitir cadastrar horários e impedir que ele marque dois compromissos no mesmo horário.
Criamos a tela de checkout simulada, que recebe os dados do cartão, valida se a compra deu certo e muda o status da aula de "Pendente" para "Confirmada".
Resultado do teste interno: Conseguimos simular todo o caminho de um aluno reservando uma aula de um professor de teste sem dar erro de conflito de horário na agenda.
5. Testes do Sistema (Escritos em Gherkin / BDD)
Para ter certeza de que o sistema vai se comportar do jeito certo na prática, escrevemos os cenários de teste pensando nas situações do dia a dia do aluno e do professor.
Módulo 1: Busca de Professores (US01)
Cenário 1.1: Busca comum funcionando com filtros
Dado que estou na tela de busca de professores
E digito "Estrutura de Dados" na caixa de pesquisa
E coloco o valor máximo de "R$ 70,00"
Quando clico em "Buscar"
Então o sistema deve me mostrar a lista com os professores de Estrutura de Dados que cobram R$ 70,00 ou menos por hora.
Cenário 1.2: Quando não existe nenhum professor com aquele filtro
Dado que estou pesquisando por "Cálculo 3"
E coloco o preço máximo de "R$ 15,00"
Quando clico em "Buscar"
Então o sistema deve exibir o aviso "Nenhum professor encontrado para esse valor ou matéria"
E me dar a opção de limpar os filtros.
Cenário 1.3: Quando digita valor inválido no filtro de preço
Dado que estou na tela de busca
E digito letras ou valores negativos no campo de preço máximo
Quando tento buscar
Então o sistema me avisa que o valor informado não é válido e pede para corrigir.
Módulo 2: Agendamento e Pagamento (US02)
Cenário 2.1: Agendando e pagando com sucesso
Dado que escolhi a aula de "Estrutura de Dados" com o professor Carlos para quinta-feira às 15:00
E estou na tela de pagamento
Quando preencho os dados do cartão corretamente e clico em "Pagar e Confirmar"
Então o sistema aprova o pagamento
E muda o status da aula para "Confirmada"
E aquele horário das 15:00 some da lista de horários livres do professor para outros alunos.
Cenário 2.2: Cartão recusado ou sem saldo
Dado que selecionei um horário na agenda do professor
E tentei pagar com um cartão que foi recusado pela operadora
Quando o sistema tenta processar a cobrança
Então ele me mostra a mensagem "Pagamento não aprovado. Tente outro cartão"
E segura aquele horário por 5 minutos antes de devolver o horário para a agenda pública.
Cenário 2.3: Aluno cancelando a aula com antecedência
Dado que tenho uma aula confirmada para daqui a 3 dias
E entro na minha área de "Minhas Aulas" e clico em "Cancelar Aula"
Quando confirmo que quero cancelar
Então o sistema cancela a reserva
E avisa que o dinheiro será devolvido
E coloca aquele horário como livre de novo na agenda do professor.
Módulo 3: Agenda do Professor e Bloqueio de Choques (US03)
Cenário 3.1: Cadastrando novo horário livre
Dado que entrei no meu painel de professor
E escolho a data de amanhã no horário das 09:00 às 10:00
Quando clico em "Salvar Horário"
Então o sistema grava essa disponibilidade e esse horário passa a aparecer para os alunos na busca.
Cenário 3.2: Tentativa de cadastrar dois horários no mesmo momento
Dado que já tenho cadastrado um horário das 14:00 às 15:00 no dia 15/10
Quando tento cadastrar outro horário das 14:30 às 15:30 na mesma data
Então o sistema não deixa salvar e avisa "Você já possui uma disponibilidade cadastrada nesse mesmo intervalo".
Cenário 3.3: Dois alunos tentando pegar a mesma vaga ao mesmo tempo
Dado que o Aluno A e o Aluno B estão com a mesma aula das 16:00 aberta na tela de pagamento
Quando o Aluno A clica em pagar e a transação dele é aprovada um segundo antes do Aluno B
Então o Aluno A fica com a vaga confirmada
E o Aluno B recebe o aviso "Este horário acabou de ser reservado por outro usuário" e a cobrança dele é cancelada.
6. Cuidados Éticos, Regras e Privacidade
Em reuniões do grupo, levantamos alguns pontos importantes sobre como a plataforma deve funcionar sem ferir regras da faculdade e leis de privacidade:
Respeito à LGPD: Não vamos pedir dados desnecessários. O cadastro vai exigir apenas nome, e-mail da faculdade, telefone e a senha (que será salva criptografada no banco). Os dados de cartão de crédito não vão ficar salvos no nosso banco de dados; serão processados por um gateway seguro de pagamento.
Nada de fraude em trabalhos ou provas: A WebEducação serve estritamente para aulas particulares, explicações e tirada de dúvidas de conteúdo. Deixaremos bem claro nos termos de uso que é proibido usar a plataforma para contratar pessoas para fazerem trabalhos, trabalhos de conclusão ou provas por outros alunos.
Garantia do dinheiro: Para evitar que um aluno pague e o professor não apareça na aula (ou vice-versa), o dinheiro só é repassado para a conta do professor depois que a aula for marcada como realizada no sistema.
7. Conclusão do Grupo
Desenvolver este relatório de consolidação do 1º Bimestre foi fundamental para o nosso grupo entender como organizar um projeto de software desde a fase de ideias. Conseguimos estruturar um backlog coerente com a realidade do problema, definir o MVP e simular os testes práticos.
O uso do formato BDD ajudou a gente a enxergar como o sistema vai funcionar na visão do usuário final, evitando erros bobos de regra de negócio. O trabalho deixou a equipe alinhada e pronta para os próximos passos da disciplina, onde vamos começar a desenhar a arquitetura e os protótipos das telas.
