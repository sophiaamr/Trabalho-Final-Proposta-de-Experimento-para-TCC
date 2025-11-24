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

Linguagem Natural: permite detalhamento narrativo e contexto (“Big Picture”) da experiência do usuário, mas sofre com ambiguidade sobre triggers de eventos e condições de exibição.

Notação Gherkin (BDD): busca remover a ambiguidade através de uma estrutura rígida (Dado/Quando/Então), mas impõe a fragmentação do comportamento da interface em múltiplos cenários desconectados.

A oportunidade deste estudo reside em investigar se, ao fragmentar regras de interface para atender ao formalismo do Gherkin, não se está introduzindo um “ponto cego” cognitivo: a perda de contexto sobre o ciclo de vida do componente, levando a erros de omissão (ex.: esquecer de resetar um estado). O objetivo é determinar empiricamente qual formato oferece maior segurança para a corretude do comportamento visual e eficiência na implementação de lógica de interface.

---

### 2.2 Contexto organizacional e técnico

O experimento será conduzido como um Estudo Controlado em Ambiente Acadêmico/Simulado.

Cenário: simulação de uma etapa de implementação de Front-end de uma funcionalidade crítica.

Participantes: o grupo amostral será composto por indivíduos com vivência técnica em desenvolvimento web (estudantes, desenvolvedores Front-end/Fullstack e QAs), divididos aleatoriamente em dois grupos de tratamento.

Objeto de Estudo: serão utilizados critérios de aceite de um Componente Rico de Interface (ex.: Formulário de Cadastro Dinâmico ou Checkout), desenhados especificamente para conter desafios de gerenciamento de estado (loading, error, success, disabled) e validação condicional.

Instrumentação: a coleta de dados será realizada via formulários eletrônicos onde os participantes deverão escrever a lógica de controle do componente (pseudocódigo ou script). O foco não é a estilização (CSS), mas sim a lógica de eventos, manipulação de estados e a densidade de bugs funcionais de interface inseridos.

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

Analisar a implementação de lógica de interface (Front-end) baseada em requisitos escritos em Notação Gherkin e Linguagem Natural, Com o propósito de avaliar o tempo de desenvolvimento, a densidade de bugs de estado/validação e a corretude do comportamento do componente, Sob o ponto de vista de desenvolvedores de software, No contexto de uma tarefa simulada de codificação de um componente rico de interface com regras complexas.

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

O experimento delimita suas fronteiras para avaliar a lógica de interação e estados de interface, excluindo aspectos estéticos puramente visuais:

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

- Os participantes compreendem o conceito de "Estados de Interface" (ex: loading, disabled, error).
- A complexidade do cenário está na interatividade (o que acontece quando o usuário clica), e não na matemática.
- O tempo reportado inclui a leitura da regra e a escrita da lógica do script (JS/TS/Pseudocódigo), ignorando o tempo de estilização.


### 4.4 Restrições

O desenho experimental respeita as seguintes limitações práticas:

- **Abstração Visual:** Como o experimento é via formulário de texto, não é possível validar o "look and feel" visualmente. A validação será feita sobre a descrição lógica do comportamento (ex: "Se usuário clicar, então setar estado X").
- **Independência de Framework:** O participante poderá escrever a solução pensando em React, Vue, Angular ou Vanilla JS, desde que a lógica de controle de estado esteja clara.
- **Tempo de Execução:** Atividade limitada a 20–30 minutos para evitar fadiga cognitiva.


### 4.5 Limitações previstas

Fatores que podem ameaçar a validade externa:

- **Subjetividade de UX:** Diferente do backend (onde 2+2=4), regras de interface em Linguagem Natural podem ser interpretadas de formas variadas dependendo da "bagagem de UX" do desenvolvedor, o que pode ser confundido com erro de interpretação.
- **Falta de Protótipo Visual:** A ausência de um layout (Figma/Mockup) junto com o requisito textual pode aumentar a dificuldade artificialmente, já que no mundo real o Front-end quase sempre trabalha com requisitos + design visual.


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

- **Baixa adesão (amostragem insuficiente):** risco de não obter o número mínimo de participantes voluntários para gerar relevância estatística/qualitativa.  
  **Mitigação:** divulgação em múltiplas comunidades/redes sociais.   
  **Meta desejável:** buscar 30–40 respostas válidas para aumentar poder estatístico, mantendo 20 como mínimo go/no-go.

- **Heterogeneidade técnica:** risco de discrepância forte de experiência (ex.: sênior vs. iniciante) distorcer tempo e qualidade.  
  **Mitigação:** coletar senioridade e familiaridade prévia com Gherkin/BDD e frameworks de front-end no formulário para permitir normalização dos dados, análise segregada por perfil e uso como covariáveis.

- **Fadiga ou abandono (drop-out):** risco de o cenário ser longo/complexo, aumentando desistência.  
  **Mitigação:** teste piloto para calibrar tamanho/clareza do enunciado e garantir duração média ≤ 20 minutos.

- **Contaminação por IA generativa:** risco de uso de ChatGPT/Copilot para gerar solução, invalidando a medida de esforço cognitivo humano.  
  **Mitigação:** 
  1. aviso explícito solicitando não usar IA;  
  2. **checkbox de declaração de não uso** antes de iniciar;  
  3. campo final pedindo breve justificativa textual (1–3 frases) sobre a lógica implementada, auxiliando detecção de inconsistências típicas de geração automática;  

- **Viés de Design:** risco de erro ocorrer por preferência pessoal do participante, e não por leitura do requisito.  
  **Mitigação:** instrução clara: “considere o requisito como verdade do produto; siga estritamente o que está escrito, mesmo que discorde do comportamento”, com exemplo curto no enunciado reforçando que o objetivo é obedecer às regras, não redesenhar UX.

---

### 6.2 Critérios de sucesso globais (go / no-go)

- **Tamanho da amostra (mínimo):** obter ≥ 20 respostas válidas (10 por grupo) completas.  
  **Meta ideal:** ≥ 30 respostas válidas.

- **Qualidade dos dados:** pelo menos 80% das submissões devem conter código ou pseudocódigo inteligível, permitindo avaliar lógica de eventos/estados; respostas em branco ou incoerentes serão descartadas.

- **Balanceamento dos grupos:** distribuição equilibrada entre Grupo A (Linguagem Natural) e Grupo B (Gherkin), evitando viés demográfico/técnico (ex.: concentração de participantes muito experientes em um grupo).  
  **Operacionalização:** checagem periódica da composição por senioridade e familiaridade com BDD durante a coleta.

- **Conclusividade:** os dados devem permitir responder às RQs (RQ1 a RQ3), seja evidenciando diferença entre formatos ou ausência de diferença estatística (resultado válido).

---

### 6.3 Critérios de parada antecipada (pré-execução)

- **Falha no teste piloto:** se participantes do piloto reportarem cenário incompreensível ou levarem > 40 minutos, o objeto de estudo (requisitos) deve ser reescrito/simplificado.

- **Inviabilidade técnica da ferramenta:** se o formulário não suportar bem blocos de código (ex.: quebra de identação/formatação), inviabilizando leitura/análise posterior.

- **Desvio crítico de interpretação:** se 100% dos primeiros 5 participantes errarem o “caminho feliz”, indica má formulação do enunciado; o requisito deve ser revisado imediatamente antes de continuar a divulgação.

