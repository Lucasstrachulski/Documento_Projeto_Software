PROJETO INTEGRADOR — CONSOLIDAÇÃO DO 1º BIMESTRE

Curso: Engenharia de Software — UniCesumar  
Tema / Sistema: WebEducação — Plataforma de Aulas Particulares  
Cenário Escolhido: Cenário J (Aulas particulares entre alunos e professores autônomos)  

---

1. Integrantes do Grupo
 Lucas Vinícius Strachulski (Líder do Grupo)
 Jhuan Pablo Kobinski de Souza
 Pedro Henrique Chaves
 Felipe Fernandes Maximo

---

 2. Apresentação do Sistema
A ideia da WebEducação surgiu para resolver um problema bem comum no campus da UniCesumar: a dificuldade que muitos alunos têm para encontrar monitores ou professores particulares de matérias específicas (como Cálculo, Estrutura de Dados ou Física) e, do outro lado, a falta de uma forma simples para os alunos que querem dar aula organizarem seus horários e receberem pelo serviço.

A plataforma vai funcionar como um ponto de encontro simples e direto. O professor entra, cadastra as matérias que domina, coloca o valor da sua hora/aula e marca na agenda quais dias e horários está livre. O aluno entra, pesquisa pela matéria que está precisando de ajuda, ajusta o filtro de preço de acordo com o bolso dele, escolhe o melhor horário e faz a reserva. Para que ninguém leve calote ou reserve horário e não apareça, o pagamento é intermediado pela própria plataforma.

---

 3. Por que escolhemos o Desenvolvimento Incremental?
Conversando sobre como poderíamos tocar o projeto, decidimos seguir o modelo Incremental (Ágil). Não faria sentido usar um modelo tradicional e engessado (como o Cascata) pelos seguintes motivos práticos que vimos durante as discussões do grupo:

Mudanças constantes de ideias:** Conforme desenhávamos os fluxos do sistema, percebemos que a forma de agendar aulas mudava toda hora. Se fôssemos fechar todos os requisitos no papel antes de codificar, teríamos que refazer o projeto inteiro mais tarde.
Foco no que importa de verdade (MVP):** Preferimos concentrar o primeiro ciclo naquilo que o sistema precisa ter para funcionar o básico: achar o professor, agendar o horário e validar o pagamento. Tendo isso pronto, o resto (como chat ou relatórios) a gente adiciona nas entregas seguintes.
Validação rápida com outros alunos:** Com entregas menores em ciclos curtos, conseguimos mostrar telas funcionais mais rápido para os próprios colegas de curso e ver se a usabilidade está boa antes de avançar.

---

4. Backlog do Produto e Divisão das Tarefas

4.1. Histórias de Usuário (User Stories)
Abaixo estão detalhadas as histórias de usuário levantadas pelo grupo para o desenvolvimento da plataforma:

US01 (Prioridade Alta) — Filtro de Busca por Matéria e Preço**  
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
Como:Professor  
Eu quero: Cadastrar e editar meus horários de aula da semana.  
Para que: Organizar minha rotina de estudos e não ter duas aulas marcadas no mesmo horário.  
O que precisa ter: Não permitir salvar horários que se sobrepõem no mesmo dia.

US04 (Prioridade Alta) — Perfil do Professor 
Como: Professor  
Eu quero: Montar meu perfil com minhas matérias, preços e formação.  
Para que: Passar confiança pros alunos e atrair mais interessados.  
O que precisa ter: Campos de foto, biografia curta e lista de matérias lecionadas.

US05 Prioridade Média) — Avaliação do Professor pelo Aluno 
Como:Aluno  
Eu quero: Deixar uma nota e um comentário depois da aula.  
Para que: Ajudar outros alunos a saberem se o professor explica bem.  
O que precisa ter: Liberar a opção de avaliar somente após o horário da aula ter terminado.

US06 (Prioridade Média) — Avaliação do Aluno pelo Professor
Como:Professor  
Eu quero:Dar uma nota de presença pro aluno.  
Para que: Registrar se o aluno foi pontual e respeitoso durante a aula.  
O que precisa ter: Campo simples de nota de 1 a 5 no histórico de aulas do professor.

US07 (Prioridade Média) — Lembretes e Notificações por E-mail
Como:Aluno  
Eu quero:Receber e-mails confirmando a aula e lembrando do horário.  
Para que: Não esquecer do compromisso no dia da aula.  
O que precisa ter: Envio de e-mail na hora que agenda e 2 horas antes de começar.

* **US08 (Prioridade Baixa) — Painel Financeiro do Professor**  
  * **Como:** Professor  
  * **Eu quero:** Ver um resumo de quanto ganhei no mês.  
  * **Para que:** Saber quanto tenho para sacar das aulas que já dei.  
  * **O que precisa ter:** Tela mostrando o total líquido acumulado e histórico de aulas pagas.

* **US09 (Prioridade Baixa) — Chat de Dúvidas Pós-Aula**  
  * **Como:** Aluno  
  * **Eu quero:** Mandar mensagem pro professor depois que a aula acabar.  
  * **Para que:** Tirar alguma dúvida rápida sobre o que foi visto.  
  * **O que precisa ter:** Caixa de mensagem simples vinculada àquela aula específica.

### 4.2. O que fizemos na Sprint Simulada
Para simular o primeiro ciclo de entrega (Sprint), pegamos as três histórias mais importantes do sistema (**US01**, **US02** e **US03**), que formam o fluxo completo de uso da plataforma.

* **Meta da Sprint:** Deixar o fluxo principal funcionando: desde a busca da aula pelo aluno até a confirmação do pagamento com bloqueio do horário na agenda.
* **O que foi desenvolvido e testado no grupo:**
  * Desenhamos a tela de busca onde o aluno digita a matéria (ex: "Algoritmos") e limita o valor máximo (ex: até R$ 60).
  * Montamos a lógica do calendário do professor para permitir cadastrar horários e impedir que ele marque dois compromissos no mesmo horário.
  * Criamos a tela de checkout simulada, que recebe os dados do cartão, valida se a compra deu certo e muda o status da aula de "Pendente" para "Confirmada".
* **Resultado do teste interno:** Conseguimos simular todo o caminho de um aluno reservando uma aula de um professor de teste sem dar erro de conflito de horário na agenda.

---

## 5. Testes do Sistema (Escritos em Gherkin / BDD)
Para ter certeza de que o sistema vai se comportar do jeito certo na prática, escrevemos os cenários de teste pensando nas situações do dia a dia do aluno e do professor.

### Módulo 1: Busca de Professores (US01)

**Cenário 1.1: Busca comum funcionando com filtros**
```gherkin
Dado que estou na tela de busca de professores
E digito "Estrutura de Dados" na caixa de pesquisa
E coloco o valor máximo de "R$ 70,00"
Quando clico em "Buscar"
Então o sistema deve me mostrar a lista com os professores de Estrutura de Dados que cobram R$ 70,00 ou menos por hora.
