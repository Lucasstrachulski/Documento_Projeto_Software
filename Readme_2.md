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


### 3.2. Detalhamento e Critérios de Aceite (Sprint Simulada)

#### 🔍 US01 — Busca por Disciplina e Preço
**Descrição:** Permite ao aluno filtrar a lista de professores disponíveis de acordo com a matéria desejada e o valor limite por hora/aula.

**Critérios de Aceite:**
- [ ] **CA01.1 — Filtros Múltiplos:** O sistema deve fornecer filtros por disciplina (ex.: Cálculo, Programação, Física) e por valor máximo (R$/h).
- [ ] **CA01.2 — Ordenação de Resultados:** Os resultados devem ser ordenados por padrão pela menor tarifa ou por melhor avaliação.
- [ ] **CA01.3 — Sugestão Inteligente:** Caso nenhum professor atenda aos critérios exatos, o sistema deve sugerir matérias correlatas ou faixas de preço aproximadas.

---

#### 💳 US02 — Agendamento e Pagamento de Aula
**Descrição:** Permite ao aluno selecionar um horário vago no calendário do professor, revisar os dados da aula e efetuar o pagamento via gateway integrado (PIX ou Cartão).

**Critérios de Aceite:**
- [ ] **CA02.1 — Bloqueio Temporário:** Ao selecionar o horário, o sistema deve temporariamente "bloquear" o slot por 10 minutos para conclusão do pagamento.
- [ ] **CA02.2 — Confirmação via Gateway:** A confirmação da reserva só ocorre mediante aprovação da transação pelo gateway simulado.
- [ ] **CA02.3 — Notificação Instantânea:** O aluno e o professor devem receber a confirmação por e-mail e na plataforma imediatamente após o pagamento.

---

#### 📅 US03 — Gestão da Agenda do Professor
**Descrição:** O professor visualiza um calendário semanal/mensal para cadastrar seus horários de atendimento livres e bloquear horários indisponíveis.

**Critérios de Aceite:**
- [ ] **CA03.1 — Flexibilidade de Horários:** O professor pode definir horários recorrentes (ex.: toda terça-feira das 14h às 16h) ou horários avulsos.
- [ ] **CA03.2 — Proteção de Aulas Agendadas:** Horários com aulas já pagas não podem ser excluídos ou alterados sem passar pelo fluxo de cancelamento.
- [ ] **CA03.3 — Prevenção de Conflitos:** A agenda deve impedir automaticamente qualquer tentativa de cadastro de horários sobrepostos (*double booking*).


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
