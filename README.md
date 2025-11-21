## 1. Identificação básica

### 1.1 Título do experimento
**Notação Gherkin vs. Linguagem Natural: Impactos na Acurácia e Retrabalho em Critérios de Aceite**

### 1.2 ID / código
**EXP-01**  

### 1.3 Versão do documento e histórico de revisão
**Versão atual:** v1.0  

**Histórico de revisão:**
- **v1.0 (21/11/2025):** rascunho inicial com tema, escopo e motivação.  

### 1.4 Datas (criação, última atualização)
- **Data de criação:** 21/11/2025  
- **Última atualização:** 21/11/2025

### 1.5 Autores (nome, área, contato)
**Sophia Mendes Rabelo** — Engenharia de Software — contato: sophiamendesrabelo@gmail.com

### 1.6 Responsável principal (PI / dono do experimento)
**Sophia Mendes Rabelo**

### 1.7 Projeto / produto / iniciativa relacionada
Atividade acadêmica de Experimentação em Engenharia de Requisitos / Processos Ágeis.  
O experimento está ligado ao estudo de técnicas de escrita de critérios de aceite e seus impactos na implementação.

## 2. Contexto e problema

### 2.1 Descrição do problema / oportunidade
No ciclo de vida de desenvolvimento de software, a falha na engenharia de requisitos permanece como uma das principais causas de defeitos (bugs) e retrabalho. O problema torna-se crítico em funcionalidades de alta complexidade lógica, onde regras de negócio interdependentes, exceções e cálculos de fronteira precisam ser comunicados com precisão absoluta.

Atualmente, a indústria enfrenta um dilema na especificação desses critérios:

- **Linguagem Natural:** permite detalhamento narrativo e contexto (“Big Picture”), mas sofre com ambiguidade léxica e sintática, induzindo a erros de interpretação de valores e condições.  
- **Notação Gherkin (BDD):** busca remover a ambiguidade através de uma estrutura rígida (Dado/Quando/Então), mas impõe a fragmentação da regra em múltiplos cenários atômicos.

A oportunidade deste estudo reside em investigar se, ao fragmentar regras complexas para atender ao formalismo do Gherkin, não se está introduzindo um “ponto cego” cognitivo: a perda de contexto que leva a erros de omissão. O objetivo é determinar empiricamente qual formato oferece maior segurança (menor taxa de defeitos e retrabalho) para a compreensão humana antes da codificação.

---

### 2.2 Contexto organizacional e técnico
O experimento será conduzido como um **Estudo Controlado em Ambiente Acadêmico/Simulado**.

- **Cenário:** simulação de uma etapa de Refinamento Técnico ou análise pré-implementação.  
- **Participantes:** o grupo amostral será composto por indivíduos com vivência técnica (estudantes de engenharia de software, desenvolvedores e analistas de QA), divididos aleatoriamente em dois grupos de tratamento.  
- **Objeto de Estudo:** serão utilizados critérios de aceite de uma funcionalidade de alta complexidade cognitiva (ex.: sistema de elegibilidade com regras cruzadas), desenhados especificamente para conter desafios lógicos e de fronteira.  
- **Instrumentação:** a coleta de dados será realizada via formulários eletrônicos de validação lógica (*teste de mesa*), sem dependência de IDEs ou linguagens de programação específicas, focando puramente na capacidade de interpretação do requisito.

---

### 2.3 Trabalhos e evidências prévias (internos e externos)
A fundamentação deste experimento combina teorias clássicas com evidências recentes do cenário Ágil e de Automação:

- **Persistência do Problema em Ágil:** dados recentes do *17th State of Agile Report (2024)* indicam que “requisitos pouco claros” continuam entre as principais causas de falha em projetos, refutando a ideia de que processos ágeis eliminaram o problema da especificação. Estudos de Mendes & Silva (2023) corroboram que a ambiguidade gera um volume significativo de *Rework Churn* (taxa de retrabalho) mesmo em ciclos curtos.  

- **Ambiguidade em User Stories:** pesquisas recentes sobre Processamento de Linguagem Natural (PLN), como as de Dalpiaz et al. (2021), apontam que User Stories escritas puramente em linguagem natural apresentam “ambiguidade nociva” em cerca de 45% dos casos industriais, validando a necessidade de formalismos.  

- **O “Gap” Humano na Literatura de BDD:** revisões sistemáticas recentes, como Zampetti et al. (2021) e Rahman (2023), demonstram que a pesquisa acadêmica sobre Gherkin está massivamente focada na geração automática de testes (muitas vezes via IA). Existe uma escassez crítica de estudos experimentais atuais que avaliem a leiturabilidade cognitiva da notação para o ser humano. Este trabalho preenche essa lacuna ao questionar se o desenvolvedor consegue compreender regras complexas “escondidas” atrás da estrutura rígida do Gherkin.

---

### 2.4 Referencial teórico e empírico essencial

- **Behavior Driven Development (BDD):** metodologia que utiliza a notação estruturada Gherkin para descrever comportamentos. O estudo foca no Gherkin como ferramenta de documentação para humanos, não apenas para máquinas.

**Taxonomia de Erros (Métricas):**
- **Erros de Comissão (Precisão):** o desenvolvedor implementa algo errado por má interpretação de valores ou operadores (hipótese: maior incidência na Linguagem Natural).  
- **Erros de Omissão (Contexto):** o desenvolvedor deixa de implementar uma regra ou exceção por não visualizá-la na fragmentação dos cenários (hipótese: maior incidência no Gherkin em cenários complexos).
