## 1. Identificação básica

### 1.1 Título do experimento
**Notação Gherkin vs. Linguagem Natural: Impactos na Acurácia e Retrabalho em Critérios de Aceite**

### 1.2 ID / código
**EXP-02**  

### 1.3 Versão do documento e histórico de revisão
**Versão atual:** v2.0  

**Histórico de revisão:**
- **v1.0 (21/11/2025):** rascunho inicial com tema, escopo e motivação.
- **v2.0 (24/11/2025):** entrega 2 + revisão da seção 2 

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

No ciclo de vida de desenvolvimento de software, a falha na engenharia de requisitos permanece como uma das principais causas de defeitos (bugs) e retrabalho. O problema torna-se crítico em interfaces de usuário (Front-end) de alta complexidade interativa, onde regras de validação dinâmica, gerenciamento de estados de componentes e feedbacks visuais precisam ser comunicados com precisão absoluta.

Atualmente, a indústria enfrenta um dilema na especificação desses critérios:

Linguagem Natural: permite detalhamento narrativo e contexto da experiência do usuário, mas sofre com ambiguidade sobre triggers de eventos e condições de exibição.

Notação Gherkin (BDD): busca remover a ambiguidade através de uma estrutura rígida (Dado/Quando/Então), mas impõe a fragmentação do comportamento da interface em múltiplos cenários desconectados.

A oportunidade deste estudo reside em investigar se, ao fragmentar regras de interface para atender ao formalismo do Gherkin, não se está introduzindo um “ponto cego” cognitivo: a perda de contexto sobre o ciclo de vida do componente, levando a erros de omissão. O objetivo é determinar empiricamente qual formato oferece maior segurança para a corretude do comportamento visual e eficiência na implementação de lógica de interface.

---

### 2.2 Contexto organizacional e técnico

O experimento será conduzido como um Estudo Controlado em Ambiente Acadêmico/Simulado.

Cenário: simulação de uma etapa de implementação de Front-end de uma funcionalidade crítica.

Participantes: o grupo amostral será composto por desenvolvedores front-end e QA, divididos aleatoriamente em dois grupos de tratamento.

Objeto de Estudo: serão utilizados critérios de aceite de um componente rico de interface, desenhados especificamente para conter desafios de gerenciamento de estado e validação condicional.

Instrumentação: a coleta de dados será realizada via formulários eletrônicos onde os participantes deverão escrever a lógica de controle do componente (pseudocódigo ou script). O foco não é a estilização, mas sim a lógica de eventos, manipulação de estados e a densidade de bugs funcionais de interface inseridos.

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

---

## 3. Objetivos e questões (Goal / Question / Metric)

### 3.1 Objetivo geral (Goal template)

Analisar a Notação Gherkin e a Linguagem Natural com o propósito de avaliação em relação ao tempo de desenvolvimento, à densidade de bugs de estado/validação e à corretude do comportamento, sob o ponto de vista de desenvolvedores de software, no contexto de uma tarefa simulada de codificação de um componente rico de interface com regras complexas.

### 3.2 Objetivos específicos

O1 (Eficiência): Comparar o tempo médio gasto para traduzir o requisito (Gherkin vs. Texto) em lógica de controle de interface funcional.

O2 (Corretude de Estados): Avaliar qual formato resulta em implementações mais fiéis ao ciclo de vida do componente (ex: loading, sucesso, erro).

O3 (Robustez/Bugs): Identificar qual formato induz a maior inserção de bugs em validações condicionais e tratamentos de exceção de interface.

O4 (Retrabalho): Mensurar a necessidade de correções posteriores baseada na qualidade da primeira entrega do código.  


### 3.3 Questões de pesquisa / de negócio

### Relacionadas ao O1 (Tempo/Eficiência)

**Q1.1:** Desenvolvedores levam menos tempo para estruturar a lógica do componente quando guiados por passos estruturados (Gherkin)?  

**Q1.2:** A leitura de texto corrido (Linguagem Natural) atrasa o início da codificação devido à necessidade de extrair as regras de interação?  

**Q1.3:** Existe diferença na produtividade (regras de interface codificadas por minuto) entre os grupos?  


### Relacionadas ao O2 (Corretude de Estados)

**Q2.1:** Qual grupo implementou o fluxo principal ("Happy Path" da interação) com maior taxa de sucesso?  

**Q2.2:** A estrutura do Gherkin garante que todas as transições de estado (ex: clicar -> carregar -> sucesso) sejam codificadas corretamente?  


### Relacionadas ao O3 (Bugs e Exceções)

**Q3.1:** Qual formato gerou mais bugs de omissão (ex: esquecer de bloquear um botão durante o envio ou esquecer de limpar uma mensagem de erro)?  

**Q3.2:** Qual formato gerou mais bugs de lógica condicional (ex: exibir mensagem de sucesso quando deveria exibir erro)?  


### Relacionadas ao O4 (Retrabalho)

**Q4.1:** Quantas submissões de código seriam reprovadas em um Code Review por falharem em critérios de usabilidade ou validação?  


### 3.4 Métricas associadas (GQM)

| Objetivo      | Questão            | Métricas (IDs) | O que se espera medir                                              |
|--------------|--------------------|----------------|---------------------------------------------------------------------|
| O1. Eficiência | Q1.1 (Tempo Total)  | M01, M02       | Tempo decorrido entre receber o requisito e finalizar a lógica.     |
|              | Q1.2 (Start-up)    | M01            | Impacto do formato na velocidade de entrega.                        |
|              | Q1.3 (Produtividade) | M03            | Relação agilidade vs. qualidade lógica.                             |
| O2. Corretude | Q2.1 (Happy Path)  | M04            | Se a interação básica funciona (clique e resposta).                 |
|              | Q2.2 (Estados)     | M05            | Se todos os estados visuais foram tratados no código.               |
| O3. Bugs     | Q3.1 (Omissão)     | M06, M08       | Regras de UI esquecidas (ex: não desabilitar botão).                |
|              | Q3.2 (Lógica UI)   | M07, M08       | Erros de fluxo (ex: mostrar msg errada).                            |
| O4. Retrabalho | Q4.1 (Reprovação)   | M09, M10       | Índice de código que precisaria ser refeito.                        |


| ID   | Nome da Métrica                   | Descrição da Métrica                                                                                                   | Unidade             |
|------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------|---------------------|
| M01  | Tempo de Implementação           | Tempo total gasto pelo desenvolvedor para ler o requisito e escrever a lógica do componente.                          | Minutos/Segundos    |
| M02  | Desvio Padrão do Tempo           | Variação do tempo dentro do mesmo grupo.                                                                              | Minutos             |
| M03  | Code Velocity (UI)               | Razão entre regras de interface atendidas corretamente e o tempo gasto.                                               | Regras/Minuto       |
| M04  | Acurácia do Caminho Feliz        | Se o código atende ao fluxo principal de interação corretamente.                                                      | Binária (0 ou 1)    |
| M05  | Cobertura de Estados (State Coverage) | Percentual de estados de interface (Loading, Error, Success, Disabled) descritos que foram tratados no código.   | Porcentagem (%)     |
| M06  | Bugs de Omissão (Missing UI Logic) | Contagem de comportamentos de interface exigidos (ex: resetar form) que não foram escritos.                        | Contagem Absoluta   |
| M07  | Bugs de Lógica de Fluxo          | Contagem de erros em condicionais de validação ou transições de estado incorretas.                                   | Contagem Absoluta   |
| M08  | Densidade de Defeitos            | Total de bugs encontrados (M06 + M07) dividido pela complexidade da solução.                                          | Bugs / Solução      |
| M09  | Taxa de Rejeição (Simulada)      | Classificação do código como "Aprovado" ou "Requer Ajustes" funcionalmente.                                           | Binária (Pass/Fail) |
| M10  | Esforço de Retrabalho Estimado   | Estimativa de tempo para corrigir os bugs de interface encontrados.                                                   | Minutos (Estimado)  |


## 4. Escopo e contexto do experimento

### 4.1 Escopo funcional / de processo (incluído e excluído)

**Incluído (Escopo do Experimento):**

- **Lógica de Interação do Usuário:** Interpretação de regras sobre eventos de interface (clique, foco, digitação, hover).
- **Gestão de Estados Visuais (State Management):** Definição de regras para alternância de estados dos componentes (Habilitado/Desabilitado, Carregando, Visível/Oculto, Sucesso/Erro).
- **Lógica de Validação no Cliente:** Implementação de regras de feedback imediato ao usuário (mensagens de erro, cores de validação) baseadas nos critérios de aceite.
- **Pseudocódigo de Componentes:** Escrita da lógica funcional (ex: funções JavaScript/TypeScript ou manipuladores de eventos) que controlam o comportamento da tela.

**Excluído (Fora do Escopo):**

- **Estilização Visual (CSS/Styles):** Não será avaliada a fidelidade de cores, fontes, espaçamentos ou layout responsivo (pixel-perfect).
- **Estrutura Semântica (HTML):** A hierarquia de tags não é objeto de avaliação, apenas a lógica atrelada a elas.
- **Integração com Backend:** Não será exigida a implementação real de chamadas de API (fetch/axios), apenas a simulação do tratamento de suas respostas (sucesso/falha).


### 4.2 Contexto do estudo (tipo de organização, projeto, experiência)

O estudo caracteriza-se como um experimento controlado simulando o desenvolvimento de Front-end em um ambiente corporativo moderno.

- **Tipo de Organização:** Acadêmica/Simulada.
- **Cenário do Projeto:** Implementação de um componente de interface crítico em uma aplicação Web (ex: Checkout ou Formulário de Registro Complexo), onde a experiência do usuário (UX) depende estritamente do cumprimento das regras de comportamento.
- **Perfil dos Participantes:** A amostragem é composta por indivíduos com conhecimentos em desenvolvimento Web (Front-end ou Fullstack) e garantia de qualidade.
- **Criticidade:** O cenário foca em "Usabilidade Crítica", onde falhas na lógica de interface (ex: botão habilitado na hora errada) podem bloquear o usuário ou induzi-lo ao erro.


### 4.3 Premissas

Para a validade do experimento, assume-se que:

- Os participantes compreendem o conceito de "Estados de Interface" (loading, disabled, error, etc).
- A complexidade do cenário está na interatividade.
- O tempo reportado inclui a leitura da regra e a escrita da lógica do script, ignorando o tempo de estilização.


### 4.4 Restrições

O desenho experimental respeita as seguintes limitações práticas:

- **Abstração Visual:** Como o experimento é via formulário de texto, não é possível validar o "look and feel" visualmente. A validação será feita sobre a descrição lógica do comportamento.
- **Independência de Framework:** O participante poderá escrever a solução pensando em React, Vue, Angular, desde que a lógica de controle de estado esteja clara.
- **Tempo de Execução:** Atividade limitada a 20–30 minutos para evitar fadiga cognitiva.


### 4.5 Limitações previstas

Fatores que podem ameaçar a validade externa:

- **Subjetividade de UX:** Diferente do backend, regras de interface em Linguagem Natural podem ser interpretadas de formas variadas dependendo da "bagagem de UX" do desenvolvedor, o que pode ser confundido com erro de interpretação.
- **Falta de Protótipo Visual:** A ausência de um layout (Figma) junto com o requisito textual pode aumentar a dificuldade artificialmente, já que no mundo real o Front-end quase sempre trabalha com requisitos + design visual.


## 5. Stakeholders, interesses e impactos

### 5.1 Stakeholders principais

- **Pesquisador responsável:** conduz o experimento, garante rigor metodológico e analisa os dados.
- **Desenvolvedores (Front-end/Fullstack):** público-alvo central; consomem os requisitos e são diretamente afetados por ambiguidade e carga cognitiva.
- **Product Owners (POs) / Business Analysts (BAs):** autores dos critérios de aceite; interessados em reduzir ruídos de comunicação com o time técnico.
- **Lideranças técnicas (Tech Leads / Engineering Managers):** interessadas em reduzir lead time e retrabalho decorrente de falhas de especificação.
- **Analistas de qualidade (QA):** interessados na consistência entre o que foi especificado, implementado e testado.

### 5.2 Interesses e expectativas dos stakeholders
- **Desenvolvedores:** identificar o formato que melhor equilibra rapidez de leitura e clareza das regras de interface, reduzindo inferências/“guesswork”.
- **POs/BAs:** avaliar se o custo adicional de escrever em Gherkin se traduz em menos bugs; caso contrário, sustentar formatos híbridos ou mais leves.
- **Gestão técnica:** obter evidências para padronizar a escrita de user stories, aumentando eficiência do fluxo (throughput) e reduzindo rework churn.

### 5.3 Impactos potenciais no processo / produto

**Impacto no processo de refinamento:**
- Se o **Gherkin** reduzir bugs de estado/validação em cenários complexos, recomenda-se seu uso obrigatório nesses casos, mesmo com maior esforço inicial.
- Se a **linguagem natural** reduzir omissões por manter melhor contexto, recomenda-se seu uso como fonte primária de compreensão do desenvolvedor, deixando o Gherkin como apoio à automação de testes.

**Impacto na qualidade do produto (Front-end):**
- **Menos bugs de interface crítica:** menor incidência de falhas de usabilidade (ex.: botão habilitado fora de hora, loading infinito).
- **Menos retrabalho:** redução de rejeições em code review e de retornos de QA para desenvolvimento.
  

## 6. Riscos de alto nível, premissas e critérios de sucesso

## 6. Riscos e critérios de sucesso

### 6.1 Riscos de alto nível (negócio, técnicos, etc.)

- **Baixa adesão (amostragem insuficiente):** risco de não atingir as 100 respostas válidas necessárias para conseguir realizar o cálculo estatístico planejado.  

- **Heterogeneidade técnica:** risco de discrepância forte de senioridade distorcer tempo e qualidade.  

- **Fadiga ou abandono (drop-out):** risco de o cenário ser longo/complexo, aumentando desistência.
- 
- **Contaminação por IA generativa:** risco de uso de modelos de inteligência artificial para gerar solução, invalidando a medida de esforço cognitivo humano.  

- **Viés de Design:** risco de erro ocorrer por preferência pessoal do participante, e não por leitura do requisito.  


---

### 6.2 Critérios de sucesso globais (go / no-go)

- **Tamanho da amostra (mínimo):**  
  - **GO:** obter ≥ 60 respostas válidas.  
  - **NO-GO:** obter menos de 60 respostas válidas.  

- **Qualidade dos dados:**  
  - **GO:** pelo menos 80% das submissões contêm código inteligível.  
  - **NO-GO:** menos de 70% das submissões contêm código inteligível.  

- **Balanceamento dos grupos:**  
  - **GO:** distribuição equilibrada entre Grupo A (Linguagem Natural) e Grupo B (Gherkin) em termos de senioridade e familiaridade com Gherkin.  
  - **NO-GO:** desequilíbrio relevante entre os grupos em senioridade ou familiaridade com Gherkin, indicando viés técnico.  

---

### 6.3 Critérios de parada antecipada (pré-execução)

- **Falha no teste piloto:** se participantes do piloto reportarem cenário incompreensível ou levarem > 40 minutos, os requisitos devem ser reescritos.

- **Inviabilidade técnica da ferramenta:** se o formulário não suportar bem blocos de código, inviabilizando análise posterior.

- **Desvio crítico de interpretação:** se os primeiros 5 participantes errarem o “caminho feliz”, indica má formulação do enunciado e o requisito deve ser revisado antes de continuar a divulgação.

## 7. Modelo conceitual e hipóteses

### 7.1 Modelo conceitual do experimento

Explique, em texto ou esquema, como você acredita que os fatores influenciam as respostas (por exemplo, “técnica A reduz defeitos em relação a B”).

### 7.2 Hipóteses formais (H0, H1)

Formule explicitamente as hipóteses nulas e alternativas para cada questão principal, incluindo a direção esperada do efeito quando fizer sentido.

### 7.3 Nível de significância e considerações de poder

Defina o nível de significância (por exemplo, α = 0,05) e comente o que se espera em termos de poder estatístico, relacionando-o ao tamanho de amostra planejado.

---

## 8. Variáveis, fatores, tratamentos e objetos de estudo

### 8.1 Objetos de estudo

Descreva o que será efetivamente manipulado ou analisado (módulos de código, requisitos, tarefas, casos de teste, issues, etc.).

### 8.2 Sujeitos / participantes (visão geral)

Caracterize em alto nível quem serão os participantes (desenvolvedores, testadores, estudantes, etc.), sem ainda entrar em detalhes de seleção.

### 8.3 Variáveis independentes (fatores) e seus níveis

Liste os fatores que serão manipulados (por exemplo, técnica, ferramenta, processo) e indique os níveis de cada um (A/B, X/Y, alto/baixo).

### 8.4 Tratamentos (condições experimentais)

Descreva claramente cada condição de experimento (grupo controle, tratamento 1, tratamento 2, etc.) e o que distingue uma da outra.

### 8.5 Variáveis dependentes (respostas)

Informe as medidas de resultado que você observará (por exemplo, número de defeitos, esforço em horas, tempo de conclusão, satisfação).

### 8.6 Variáveis de controle / bloqueio

Liste fatores que você não está estudando diretamente, mas que serão mantidos constantes ou usados para formar blocos (por exemplo, experiência, tipo de tarefa).

### 8.7 Possíveis variáveis de confusão conhecidas

Identifique fatores que podem distorcer os resultados (como diferenças de contexto, motivação ou carga de trabalho) e que você pretende monitorar.

---

## 9. Desenho experimental

### 9.1 Tipo de desenho (completamente randomizado, blocos, fatorial, etc.)

Indique qual tipo de desenho será utilizado e justifique brevemente por que ele é adequado ao problema e às restrições.

### 9.2 Randomização e alocação

Explique o que será randomizado (sujeitos, tarefas, ordem de tratamentos) e como a randomização será feita na prática (ferramentas, procedimentos).

### 9.3 Balanceamento e contrabalanço

Descreva como você garantirá que os grupos fiquem comparáveis (balanceamento) e como lidará com efeitos de ordem ou aprendizagem (contrabalanço).

### 9.4 Número de grupos e sessões

Informe quantos grupos existirão e quantas sessões ou rodadas cada sujeito ou grupo irá executar, com uma breve justificativa.

---

## 10. População, sujeitos e amostragem

### 10.1 População-alvo

Descreva qual é a população real que você deseja representar com o experimento (por exemplo, “desenvolvedores Java de times de produto web”).

### 10.2 Critérios de inclusão de sujeitos

Especifique os requisitos mínimos para um participante ser elegível (experiência, conhecimento, papel, disponibilidade, etc.).

### 10.3 Critérios de exclusão de sujeitos

Liste condições que impedem participação (conflitos de interesse, falta de skills essenciais, restrições legais ou éticas).

### 10.4 Tamanho da amostra planejado (por grupo)

Defina quantos participantes você pretende ter no total e em cada grupo, relacionando a decisão com poder, recursos e contexto.

### 10.5 Método de seleção / recrutamento

Explique como os participantes serão escolhidos (amostra de conveniência, sorteio, convite aberto, turma de disciplina, time específico).

### 10.6 Treinamento e preparação dos sujeitos

Descreva qual treinamento ou material preparatório será fornecido para nivelar entendimento e reduzir vieses por falta de conhecimento.

---

## 11. Instrumentação e protocolo operacional

### 11.1 Instrumentos de coleta (questionários, logs, planilhas, etc.)

Liste todos os instrumentos que serão usados para coletar dados (arquivos, formulários, scripts, ferramentas), com uma breve descrição do papel de cada um.

### 11.2 Materiais de suporte (instruções, guias)

Descreva as instruções escritas, guias rápidos, slides ou outros materiais que serão fornecidos a participantes e administradores do experimento.

### 11.3 Procedimento experimental (protocolo – visão passo a passo)

Escreva, em ordem, o que acontecerá na operação (do convite ao encerramento), de modo que alguém consiga executar o experimento seguindo esse roteiro.

### 11.4 Plano de piloto (se haverá piloto, escopo e critérios de ajuste)

Indique se um piloto será realizado, com que participantes e objetivos, e defina que tipo de ajuste do protocolo poderá ser feito com base nesse piloto.

---

## 12. Plano de análise de dados (pré-execução)

### 12.1 Estratégia geral de análise (como responderá às questões)

Explique, em alto nível, como os dados coletados serão usados para responder cada questão de pesquisa ou de negócio.

### 12.2 Métodos estatísticos planejados

Liste os principais testes ou técnicas estatísticas que pretende usar (por exemplo, t-teste, ANOVA, testes não paramétricos, regressão).

### 12.3 Tratamento de dados faltantes e outliers

Defina previamente as regras para lidar com dados ausentes e valores extremos, evitando decisões oportunistas após ver os resultados.

### 12.4 Plano de análise para dados qualitativos (se houver)

Descreva como você tratará dados qualitativos (entrevistas, comentários, observações), especificando a técnica de análise (codificação, categorias, etc.).

---

## 13. Avaliação de validade (ameaças e mitigação)

### 13.1 Validade de conclusão

Liste ameaças que podem comprometer a robustez das conclusões estatísticas (baixo poder, violação de suposições, erros de medida) e como pretende mitigá-las.

### 13.2 Validade interna

Identifique ameaças relacionadas a causas alternativas para os efeitos observados (history, maturation, selection, etc.) e explique suas estratégias de controle.

### 13.3 Validade de constructo

Refleta se as medidas escolhidas realmente representam os conceitos de interesse e descreva como você reduzirá ambiguidades de interpretação.

### 13.4 Validade externa

Discuta em que contextos os resultados podem ser generalizados e quais diferenças de cenário podem limitar essa generalização.

### 13.5 Resumo das principais ameaças e estratégias de mitigação

Faça uma síntese das ameaças mais críticas e das ações planejadas, de preferência em forma de lista ou tabela simples.

---

## 14. Ética, privacidade e conformidade

### 14.1 Questões éticas (uso de sujeitos, incentivos, etc.)

Descreva potenciais questões éticas (pressão para participar, uso de estudantes, incentivos, riscos de exposição) e como serão tratadas.

### 14.2 Consentimento informado

Explique como os participantes serão informados sobre objetivos, riscos, benefícios e como registrarão seu consentimento.

### 14.3 Privacidade e proteção de dados

Indique que dados pessoais serão coletados, como serão protegidos (anonimização, pseudoanonimização, controle de acesso) e por quanto tempo serão mantidos.

### 14.4 Aprovações necessárias (comitê de ética, jurídico, DPO, etc.)

Liste órgãos ou pessoas que precisam aprovar o experimento (comitê de ética, jurídico, DPO, gestores) e o status atual dessas aprovações.

---

## 15. Recursos, infraestrutura e orçamento

### 15.1 Recursos humanos e papéis

Identifique os membros da equipe do experimento e descreva brevemente o papel e responsabilidade de cada um.

### 15.2 Infraestrutura técnica necessária

Liste ambientes, servidores, ferramentas, repositórios e integrações que devem estar disponíveis para executar o experimento.

### 15.3 Materiais e insumos

Relacione materiais físicos ou digitais necessários (máquinas, licenças, formulários, dispositivos) que precisam estar prontos antes da operação.

### 15.4 Orçamento e custos estimados

Faça uma estimativa dos principais custos envolvidos (horas de pessoas, serviços, licenças, infraestrutura) e a fonte de financiamento.

---

## 16. Cronograma, marcos e riscos operacionais

### 16.1 Macrocronograma (até o início da execução)

Defina as principais datas e marcos (conclusão do plano, piloto, revisão, início da operação) com uma visão de tempo realista.

### 16.2 Dependências entre atividades

Indique quais atividades dependem de outras para começar (por exemplo, treinamento após aprovação ética), deixando essas dependências claras.

### 16.3 Riscos operacionais e plano de contingência

Liste riscos ligados a cronograma, disponibilidade de pessoas ou recursos, e descreva ações de contingência caso esses riscos se materializem.

---

## 17. Governança do experimento

### 17.1 Papéis e responsabilidades formais

Defina quem decide, quem executa, quem revisa e quem apenas deve ser informado, deixando claro o fluxo de responsabilidade.

### 17.2 Ritos de acompanhamento pré-execução

Descreva as reuniões, checkpoints e revisões previstos antes da execução, incluindo frequência e participantes.

### 17.3 Processo de controle de mudanças no plano

Explique como mudanças no desenho ou no escopo do experimento serão propostas, analisadas, aprovadas e registradas.

---

## 18. Plano de documentação e reprodutibilidade

### 18.1 Repositórios e convenções de nomeação

Indique onde o plano, instrumentos, scripts e dados (futuros) serão armazenados e quais convenções de nomes serão usadas.

### 18.2 Templates e artefatos padrão

Liste os modelos (questionários, formulários, checklists, scripts) que serão usados e onde podem ser encontrados.

### 18.3 Plano de empacotamento para replicação futura

Descreva o que será organizado desde já (documentos, scripts, instruções) para facilitar a replicação do experimento por outras equipes ou no futuro.

---

## 19. Plano de comunicação

### 19.1 Públicos e mensagens-chave pré-execução

Liste os grupos que precisam ser comunicados e quais mensagens principais devem receber (objetivos, escopo, datas, impactos esperados).

### 19.2 Canais e frequência de comunicação

Defina por quais canais (e-mail, reuniões, Slack/Teams, etc.) e com que frequência as comunicações serão feitas.

### 19.3 Pontos de comunicação obrigatórios

Especifique os eventos que exigem comunicação formal (aprovação do plano, mudanças relevantes, adiamentos, cancelamentos).

---

## 20. Critérios de prontidão para execução (Definition of Ready)

### 20.1 Checklist de prontidão (itens que devem estar completos)

Liste os itens que precisam estar finalizados e aprovados (plano, instrumentos, aprovação ética, recursos, comunicação) para autorizar o início da operação.

### 20.2 Aprovações finais para iniciar a operação

Indique quem precisa dar o “ok final” (nomes ou cargos) e como esse aceite será registrado antes da execução começar.

