# 📚 WebEducação — Plataforma de Aulas Particulares
> **Projeto Integrador - Consolidação do 1º Bimestre**  
> *Engenharia de Software*

---

## 👥 Informações do Grupo
* **Cenário Escolhido:** J — Plataforma de aulas particulares (professores autônomos e alunos)
* **Nome do Grupo:** *Grupo do Lucas Vinícius*
* **Integrantes:**
  * *Lucas Vinícius Strachulski -- Líder*
  * *Jhuan Pablo Kobinski de Souza*
  * *Pedro Henrique Chaves*
  * *Felipe Fernandes Maximo*

---

## 📄 Documento do Projeto

### 1. Identificação e Visão Geral do Sistema
A **WebEducação** é uma plataforma integrada com o **SUDEO** onde intermedia a busca de aulas, o agendamento e a realização de aulas particulares entre os professores e alunos da própria Faculdade (UniCesumar). O sistema permite em que os professores de cada curso divulguem suas especificações, horários livres e os valores das aulas. Enquanto os alunos buscam os profissionais adequados por meio de filtros. Além disso, para não ter golpes, o próprio sistema gerencia o pagamento das aulas, deixando mais confiável e seguro. O objetivo principal é oferecer uma ferramenta eficiente de gestão de agenda para os educadores.

---

### 2. Modelo de Processo Adotado
**Modelo Selecionado:** Desenvolvimento Incremental (Ágil)

* **Estabilidade dos Requisitos:** As plataformas de aprendizado virtual possuem requisitos dinâmicos. O feedback contínuo dos alunos e professores vai exigir ajustes frequentes que não seriam suportados pelo Modelo em Cascata.
* **Nível de Risco:** O principal risco do projeto é a rejeição por parte do público. O modelo Incremental reduz esse risco ao permitir o lançamento de um MVP focado no agendamento básico, testando o mercado antes de investir em funcionalidades mais elaboradas.
* **Prazo Esperado:** O mercado exige entregas rápidas. O modelo Incremental garante que partes funcionais do sistema sejam entregues em ciclos curtos, acelerando o tempo de lançamento no mercado.

---

### 3. Backlog do Produto em User Stories

#### Tabela do Backlog

| ID | User Story | Prioridade |
| :--- | :--- | :---: |
| **US01** | Como aluno, quero achar um professor bom e que caiba na minha renda, de acordo também com as disciplinas que preciso. | **Alta** |
| **US02** | Como aluno, preciso agendar e fazer um pagamento de uma aula. | **Alta** |
| **US03** | Como professor, preciso cadastrar minha agenda de horários para que não tenha conflitos de horários. | **Alta** |
| **US04** | Como professor, quero fazer um perfil adequado para chamar alunos, contendo valores e minha matéria especificada. | **Alta** |
| **US05** | Como aluno, desejo realizar a avaliação do meu professor, para deixar um feedback aos que também realizarão alguma aula com ele. | **Média** |
| **US06** | Como professor, desejo realizar um feedback sobre o aluno, para ele ter uma nota, ver se ele foi educado, respeitou etc. | **Média** |
| **US07** | Como aluno, quero receber notificações sobre a aula para ver se ela foi cancelada ou sobre o horário para não me atrasar. | **Média** |
| **US08** | Como professor, quero ver o tanto que as aulas me renderam ao fim do mês. | **Baixa** |
| **US09** | Como aluno, quero um chat privado com o professor após a aula para poder tirar algumas dúvidas que ficaram. | **Baixa** |

#### Planejamento e Execução da Sprint Simulada (Aula 4)
* **Itens Selecionados:** `US01`, `US02` e `US03`
* **Sprint Goal:** *"Entregar a jornada do aluno desde a busca do professor até a reserva paga e bloqueada na agenda."*
* **Escopo do Trabalho:**
  * **US01 (Busca):** Interface com filtros de matéria e preço; API de busca integrada ao banco de dados.
  * **US02 (Grade de Horários):** Componente visual de calendário; API de consulta de disponibilidade do professor.
  * **US03 (Agendamento e Pagamento):** Checkout integrado a um simulador de gateway e rotina no banco para evitar conflitos de horários (*double booking*).
* **Resultado da Mini Sprint Review:** Busca filtrada funcional, exibição dinâmica da agenda do professor e confirmação de pagamento com bloqueio em tempo real da agenda.

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
