# 📚 WebEducação — Plataforma de Aulas Particulares
> **Projeto Integrador - Consolidação do 1º Bimestre**  
> *Curso de Engenharia de Software — UniCesumar*

---

## 👥 Informações do Grupo
* **Cenário Escolhido:** J — Plataforma de aulas particulares (professores autônomos e alunos)
* **Nome do Grupo:** *Grupo do Lucas Vinícius*
* **Integrantes:**
  * *Lucas Vinícius Strachulski* — **Líder**
  * *Jhuan Pablo Kobinski de Souza*
  * *Pedro Henrique Chaves*
  * *Felipe Fernandes Maximo*

---

## 📋 Sumário
- [1. Identificação e Visão Geral do Sistema](#1-identificação-e-visão-geral-do-sistema)
- [2. Modelo de Processo Adotado](#2-modelo-de-processo-adotado)
- [3. Backlog do Produto em User Stories](#3-backlog-do-produto-em-user-stories)
  - [3.1. Tabela do Backlog](#tabela-do-backlog)
  - [3.2. Planejamento e Execução da Sprint Simulada](#planejamento-e-execução-da-sprint-simulada)
- [4. Plano de Testes e Qualidade](#4-plano-de-testes-e-qualidade)
  - [4.1. Estratégia e Tipos de Teste Aplicados](#41-estratégia-e-tipos-de-teste-aplicados)
  - [4.2. Especificação dos Cenários de Teste (BDD / Gherkin)](#42-especificação-dos-cenários-de-teste-bdd--gherkin)
- [5. Análise Ética e Privacidade](#5-análise-ética-e-privacidade)
- [6. Considerações Finais](#6-considerações-finais)

---

## 1. Identificação e Visão Geral do Sistema

A **WebEducação** é uma plataforma web integrada ao ecossistema acadêmico (SUDEO) que intermedia a busca, o agendamento e a realização de aulas particulares entre alunos e professores autônomos do ambiente universitário (UniCesumar).

O sistema permite que professores divulguem suas especialidades, valores de hora/aula e disponibilidades na agenda pública, enquanto alunos localizam os profissionais adequados por meio de filtros dinâmicos de disciplina e preço. Para garantir a segurança transacional e prevenir fraudes, a própria plataforma gerencia o checkout e a confirmação financeira das aulas. O objetivo principal é proporcionar uma ferramenta centralizada, confiável e eficiente para a gestão do aprendizado particular.

---

## 2. Modelo de Processo Adotado

**Modelo Selecionado:** Desenvolvimento Incremental (Ágil)

* **Estabilidade dos Requisitos:** Plataformas de aprendizado e agendamento possuem requisitos dinâmicos. O feedback contínuo de alunos e professores exige adaptações constantes na plataforma, incompatíveis com abordagens rígidas como o Modelo em Cascata.
* **Mitigação de Riscos:** O principal risco do projeto é a rejeição inicial pelo público-alvo. O modelo Incremental reduz esse impacto ao permitir o lançamento de um MVP (*Minimum Viable Product*) focado no fluxo essencial de agendamento e pagamento, validando o mercado antes de investir em funcionalidades mais complexas.
* **Tempo de Lançamento (*Time-to-Market*):** O ciclo incremental garante entregas funcionais em curto prazo, oferecendo valor prático aos usuários a cada iteração finalizada.

---

## 3. Backlog do Produto em User Stories

### Tabela do Backlog

| ID | Persona | História de Usuário / Necessidade | Prioridade |
| :--- | :--- | :--- | :---: |
| **US01** | Aluno | Como aluno, quero achar um professor adequado à minha necessidade e orçamento, filtrando por disciplina e faixa de preço. | **Alta** |
| **US02** | Aluno | Como aluno, preciso agendar um horário e efetuar o pagamento da aula para garantir a minha reserva. | **Alta** |
| **US03** | Professor | Como professor, preciso cadastrar minha agenda de horários para evitar conflitos e reservas sobrepostas. | **Alta** |
| **US04** | Professor | Como professor, quero estruturar meu perfil público detalhando disciplinas, valores e qualificações para atrair alunos. | **Alta** |
| **US05** | Aluno | Como aluno, desejo avaliar a aula e o professor para compartilhar meu feedback com a comunidade acadêmica. | **Média** |
| **US06** | Professor | Como professor, desejo avaliar a pontualidade e conduta do aluno para manter o histórico de reputação. | **Média** |
| **US07** | Aluno | Como aluno, quero receber notificações de lembrete do horário da aula ou de eventuais cancelamentos. | **Média** |
| **US08** | Professor | Como professor, quero visualizar relatórios financeiros consolidados dos meus rendimentos mensais. | **Baixa** |
| **US09** | Aluno | Como aluno, quero utilizar um chat privado com o professor pós-aula para sanar dúvidas pontuais remanescentes. | **Baixa** |

### Planejamento e Execução da Sprint Simulada
* **Itens Selecionados do MVP:** `US01`, `US02` e `US03`
* **Sprint Goal:** *"Entregar a jornada completa do aluno desde a busca por professores até o agendamento pago com bloqueio definitivo de horário na agenda."*
* **Escopo do Trabalho:**
  * **US01 (Busca):** Interface com filtros combinados de matéria e preço máximo; rotas de consulta na API.
  * **US02 (Agendamento e Pagamento):** Módulo de checkout simulado com validação transacional e atualização do status da reserva.
  * **US03 (Gestão de Agenda):** Componente de grade de horários do professor e mecanismo de prevenção de reservas simultâneas (*double booking*).
* **Resultado da Mini Sprint Review:** Busca por parâmetros funcionais, visualização dinâmica de horários livres e confirmação transacional com reserva imediata na agenda.

---

## 4. Plano de Testes e Qualidade

O plano de testes busca validar o comportamento do sistema nos cenários principais e de exceção da Sprint Simulada, garantindo estabilidade, segurança transacional e consistência dos dados.

### 4.1. Estratégia e Tipos de Teste Aplicados
* 🔗 **Testes de Integração:** Validar a comunicação entre a interface (Frontend), rotas da API, Banco de Dados e o simulador do Gateway de Pagamento.
* 🌐 **Testes de Sistema / E2E (End-to-End):** Testar o fluxo completo do usuário desde a busca até o bloqueio do horário no calendário.
* 🛡️ **Testes de Concorrência e Regra de Negócio:** Garantir a consistência transacional e prevenir *double booking* sob acessos simultâneos.

---

### 4.2. Especificação dos Cenários de Teste (BDD / Gherkin)

#### 🔍 Módulo 1: Busca por Professores (US01)

##### 🧪 Cenário 1.1: Busca bem-sucedida com filtros válidos
```gherkin
Dado que o aluno está na tela inicial de busca
E digita "Estrutura de Dados" no campo de disciplina
E define o limite de preço máximo em "R$ 70,00/hora"
Quando ele clica no botão "Buscar"
Então o sistema deve listar apenas professores que lecionam "Estrutura de Dados" com valor menor ou igual a R$ 70,00.
