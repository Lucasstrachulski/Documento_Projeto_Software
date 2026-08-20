# 📚 EduConecta — Plataforma de Aulas Particulares
> **Projeto Integrador - Consolidação do 1º Bimestre**  
> *Engenharia de Software*

---

## 👥 Informações do Grupo
* **Cenário Escolhido:** J — Plataforma de aulas particulares (professores autônomos e alunos)
* **Nome do Grupo:** *[Insira o Nome do Seu Grupo]*
* **Integrantes:**
  * *[Nome do Integrante 1]*
  * *[Nome do Integrante 2]*
  * *[Nome do Integrante 3]*
  * *[Nome do Integrante 4]*

---

## 📄 Documento do Projeto

### 1. Identificação e Visão Geral do Sistema
A **EduConecta** é uma plataforma web e mobile desenvolvida para intermediar a busca, o agendamento e a realização de aulas particulares entre professores autônomos e alunos de diversas áreas do conhecimento. O sistema permite que professores divulguem suas qualificações, horários e valores, enquanto alunos encontram profissionais qualificados por meio de filtros de matéria e avaliação. Além disso, a plataforma gerencia o pagamento seguro e disponibiliza ambiente ou links para as aulas. O objetivo principal é facilitar o acesso ao ensino personalizado e oferecer uma ferramenta eficiente de gestão de agenda para os educadores.

---

### 2. Modelo de Processo Adotado
**Modelo Selecionado:** Desenvolvimento Incremental (Ágil)

* **Estabilidade dos Requisitos:** As plataformas de e-learning possuem requisitos dinâmicos. O feedback contínuo dos alunos e professores exigirá ajustes frequentes que não seriam suportados pelo Modelo em Cascata.
* **Nível de Risco:** O principal risco do projeto é a rejeição por parte do público-alvo (baixo engajamento ou interface confusa). O modelo Incremental reduz esse risco ao permitir o lançamento de um MVP focado no agendamento básico, testando o mercado antes de investir em funcionalidades mais complexas.
* **Prazo Esperado:** O mercado exige entregas rápidas. O modelo Incremental garante que partes funcionais do sistema sejam entregues em ciclos curtos (Sprints), acelerando o tempo de lançamento no mercado (*time-to-market*).

---

### 3. Backlog do Produto em User Stories

#### Tabela do Backlog

| ID | User Story | Prioridade |
| :--- | :--- | :---: |
| **US01** | Como aluno, quero buscar professores por disciplina e preço, para encontrar o profissional ideal dentro do meu orçamento. | **Alta** |
| **US02** | Como aluno, quero agendar e pagar uma aula individual pela plataforma, para garantir minha reserva de forma rápida e segura. | **Alta** |
| **US03** | Como professor, quero cadastrar minha agenda de horários disponíveis, para evitar conflitos de horários com os alunos. | **Alta** |
| **US04** | Como professor, quero criar e personalizar meu perfil profissional com currículo e valores, para atrair mais alunos. | **Alta** |
| **US05** | Como aluno, quero avaliar o professor após a realização da aula, para ajudar outros estudantes na escolha do profissional. | **Média** |
| **US06** | Como aluno, quero receber notificações sobre o status da aula agendada, para não perder o horário do compromisso. | **Média** |
| **US07** | Como professor, quero visualizar o relatório financeiro de aulas realizadas no mês, para ter controle da minha renda autônoma. | **Baixa** |
| **US08** | Como aluno, quero ter um chat interno direto com o professor antes do agendamento, para tirar dúvidas sobre o conteúdo. | **Baixa** |

#### Planejamento e Execução da Sprint Simulada (Aula 4)
* **Itens Selecionados:** `US01`, `US02` e `US03`
* **Sprint Goal:** *"Permitir que o aluno busque um professor, visualize seus horários disponíveis e realize o agendamento de uma aula com pagamento."*
* **Resultado da Mini Sprint Review:** Foram validadas a tela de busca com filtros por disciplina e preço, a exibição da grade de horários no perfil do professor e o fluxo completo de agendamento integrado a uma simulação de gateway de pagamento com bloqueio imediato na agenda.

---

### 4. Plano de Testes e Qualidade

#### Testes da US01 — Busca por disciplina e preço
* **Tipos de Teste Aplicáveis:** Integração e Sistema.

```gherkin
Cenário 1: Busca com resultados válidos
  Dado que o aluno digitou "Matemática" no campo de busca e definiu o valor máximo de R$ 80,00/hora,
  Quando ele clica no botão "Buscar",
  Então o sistema deve exibir apenas perfis de professores de Matemática cujas horas de aula sejam menores ou iguais a R$ 80,00.

Cenário 2: Busca sem resultados correspondentes
  Dado que o aluno buscou por uma disciplina não cadastrada no sistema,
  Quando a busca for processada,
  Então o sistema deve exibir a mensagem "Nenhum professor encontrado para esta busca" e sugerir matérias correlatas.
