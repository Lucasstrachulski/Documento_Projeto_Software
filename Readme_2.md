# 📚 WebEducação — Plataforma de Aulas Particulares
> **(Continuação do Documento do Projeto Integrador — Parte 2)**

---

## 3. Backlog do Produto em User Stories (Versão Expandida)

### 3.1. Tabela Geral do Backlog com Estimativa de Esforço

| ID | User Story | Prioridade | Esforço (Story Points) |
| :--- | :--- | :---: | :---: |
| **US01** | Como aluno, quero buscar professores por disciplina e faixa de preço, para encontrar um educador compatível com meu orçamento e necessidade. | **Alta** | 5 |
| **US02** | Como aluno, quero agendar e realizar o pagamento de uma aula online, para garantir a reserva do meu horário com segurança. | **Alta** | 8 |
| **US03** | Como professor, quero cadastrar minha grade de disponibilidade de horários, para evitar conflitos de agenda (*double booking*). | **Alta** | 5 |
| **US04** | Como professor, quero estruturar um perfil completo com matérias, histórico e valores, para atrair mais alunos da faculdade. | **Alta** | 3 |
| **US05** | Como aluno, quero avaliar o professor após a aula, para ajudar outros estudantes na escolha de bons profissionais. | **Média** | 3 |
| **US06** | Como professor, quero registrar um feedback sobre o aluno, para manter o histórico de conduta e comprometimento. | **Média** | 3 |
| **US07** | Como aluno, quero receber notificações sobre confirmações, cancelamentos e lembretes de aula, para não perder os horários agendados. | **Média** | 5 |
| **US08** | Como professor, quero visualizar o relatório mensal dos rendimentos das minhas aulas, para ter controle financeiro dos meus ganhos. | **Baixa** | 3 |
| **US09** | Como aluno, quero utilizar um chat privado temporário pós-aula com o professor, para tirar dúvidas pontuais que tenham restado. | **Baixa** | 5 |

---

### 📊 Métrica e Resumo do Backlog

- **Total de User Stories:** 9
- **Pontuação Total (Story Points):** 40 SP
- **Distribuição por Prioridade:**
  - 🔴 **Alta:** 4 Histórias (21 SP) — *MVP / Sprint Inicial*
  - 🟡 **Média:** 3 Histórias (11 SP) — *Melhorias de Engajamento*
  - 🟢 **Baixa:** 2 Histórias (8 SP) — *Funcionalidades Complementares*


## 📋 3.2 Backlog do Produto (US05 a US09)

Abaixo estão descritas as histórias de usuário do backlog:

* *US05:* Aluno avalia o professor com método de estrelas (como o da Uber por exemplo) e comentários.
* *US06:* O professor avalia a pontualidade do horário do aluno.
* *US07:* Avisar no email e na plataforma sobre a aula 1 hora antes.
* *US08:* Mostra um relatório de quanto o professor ganhou no total no mês.
* *US09:* Um chat temporário de 24 horas após a aula.

---

## 🏃 3.3 Planejamento e Execução da Sprint Simulada

* *Sprint Goal:* Entregar toda a jornada do aluno desde a procura do professor até o agendamento e pagamento da aula.

* *Itens do Backlog:* US01, US02, US03.

* *Detalhamento das funcionalidades do sprint:*
  * *US01: Busca por disciplina e Preço:*
    * O aluno pode filtrar os professores por matéria, valor ou avaliação.
    * O sistema deve fornecer filtros por disciplina e por valor.
    * Os resultados devem ser ordenados por valor e avaliação.
    * Caso nenhum professor atenda os critérios, mostrar matérias parecidas e/ou de interesse do aluno.
  
  * *US02: Agendamento e pagamento da aula:*
    * O aluno pode selecionar um horário livre e pagar via gateway integrado como PIX ou cartão.
    * Ao selecionar o horário, o sistema deve bloquear o horário por 10 minutos para realizar o pagamento.
    * A confirmação só ocorre após a aprovação do pagamento.
    * Tanto o aluno quanto o professor devem receber a confirmação via e-mail.
  
  * *US03: Gestão de agenda do professor:*
    * O professor tem um calendário semanal para colocar seus horários disponíveis de aula.
    * Horários com aulas já pagas não podem ser excluídos ou alterados sem passar por cancelamento.
    * A agenda deve impedir qualquer tentativa de agendamento em horários já confirmados para evitar o chamado double booking.

* *Resultado:* Retornou todos os dados de forma correta, o calendário exibiu as datas de forma correta com os horários disponíveis e também foi feito o bloqueio no horário escolhido na agenda do professor.

## 4. Plano de Testes e Qualidade
O plano de testes busca validar o comportamento do sistema nos cenários principais e de exceção da
Sprint Simulada, garantindo estabilidade, segurança transacional e boa experiência do usuário.
### 4.1. Estratégia e Tipos de Teste Aplicados
* **Testes de Integração:** Validar a comunicação entre a interface do usuário (Frontend), as
rotas da API, o Banco de Dados e a simulação do Gateway de Pagamento.
* **Testes de Sistema / E2E (End-to-End):** Testar o fluxo completo do usuário desde a busca até o
bloqueio definitivo do horário no calendário.
* **Testes de Regra de Negócio / Concorrência:** Garantir a consistência dos dados em acessos
simultâneos (prevenção de *double booking*).
---
### 4.2. Especificação dos Cenários de Teste (Estilo BDD / Given-When-Then)
#### Módulo 1: Busca por Professores (US01)
##### Cenário 1.1: Busca bem-sucedida com filtros válidos
```gherkin
Dado que o aluno está na tela inicial de busca
E digita "Estrutura de Dados" no campo de disciplina
E define o limite de preço máximo em "R$ 70,00/hora"
Quando ele clica no botão "Buscar"
Então o sistema deve listar apenas professores que lecionam "Estrutura de Dados" com valor de hora/
aula menor ou igual a R$ 70,00.
```
##### Cenário 1.2: Busca sem correspondência exata
```gherkin
Dado que o aluno busca por uma disciplina inexistente (ex: "Física Quântica Avançada II")
Quando a busca é executada
Então o sistema deve retornar a mensagem: "Nenhum professor encontrado para esta busca"
E exibir sugestões de disciplinas da mesma área (ex: "Física I").
```
---
#### Módulo 2: Agendamento e Pagamento (US02)
##### Cenário 2.1: Agendamento e pagamento concluídos com sucesso
```gherkin
Dado que o aluno escolheu o horário das 15h no perfil do Professor X (Valor: R$ 50,00)
E preencheu os dados válidos do cartão de crédito no simulador de checkout
Quando clica em "Confirmar e Pagar"
Então a transação deve ser aprovada
E o sistema deve alterar o status da aula para "Confirmada"
E o horário das 15h deve ser marcado como "Indisponível" na agenda pública do professor.
```
##### Cenário 2.2: Falha no pagamento por falta de saldo/cartão recusado
```gherkin
Dado que o aluno tentou realizar o checkout com um cartão recusado pelo simulador de gateway

WebEducação — Documentação Completa do Projeto Página 2 de 3

Quando clica em "Confirmar e Pagar"
Então o sistema deve exibir o erro "Pagamento recusado pela operadora"
E o horário selecionado deve retornar ao estado "Disponível" após o tempo limite de retenção (10
minutos).
```
---
#### Módulo 3: Gestão de Agenda e Prevenção de Concorrência (US03)
##### Cenário 3.1: Cadastro de horários sem conflitos
```gherkin
Dado que o professor está na sua tela de gestão de agenda
Quando ele adiciona o bloco de horário "Quarta-feira, 10:00 às 11:00"
Então a grade deve salvar o novo horário e torná-lo visível para buscas de alunos.
```
##### Cenário 3.2: Prevenção de reserva simultânea (Double Booking)
```gherkin
Dado que o Aluno A e o Aluno B tentam confirmar o agendamento no mesmo horário (Sexta-feira às 14h)
do mesmo professor com fração de segundos de diferença
Quando o Aluno A conclui a requisição de pagamento primeiro
Então o sistema deve confirmar o agendamento do Aluno A
E deve rejeitar a requisição do Aluno B com a mensagem: "Este horário acabou de ser reservado por
outro usuário. Por favor, escolha outro horário."


### 4.3. Matriz de Rastreabilidade de Qualidade

*US01 – Busca por Disciplina e Preço:*
Tipo de teste: Sistema e Interface (UI).
Critério principal validado: precisão dos filtros utilizados na busca e ordenação dos resultados de acordo com o valor das aulas.

*US02 – Agendamento e Pagamento:*
Tipo de teste: Integração entre API e Gateway de pagamento.
Critério principal validado: atualização correta do status da transação e verificação do tempo de retenção do horário selecionado durante o processo de pagamento.

*US03 – Cadastro de Agenda:*
Tipo de teste: Regras de negócio e concorrência.
Critério principal validado: bloqueio da sobreposição de horários, evitando que dois agendamentos sejam realizados para o mesmo período (Double Booking).
