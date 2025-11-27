## 1. Identificação básica

### 1.1 Título do experimento
Notação Gherkin vs. Linguagem Natural: Impactos na Acurácia e Retrabalho em Critérios de Aceite

### 1.2 ID / código
GHLN-02  

### 1.3 Versão do documento e histórico de revisão
Versão atual: v3.0  

Histórico de revisão:
- v1.0 (21/11/2025): rascunho inicial com tema, escopo e motivação.
- v2.0 (24/11/2025): entrega 2 + revisão da seção 2.
- v3.0 (26/11/2025): seções 7, 8, 9, 10, 11 e 12.

### 1.4 Datas (criação, última atualização)
- Data de criação: 21/11/2025  
- Última atualização: 26/11/2025

### 1.5 Autores (nome, área, contato)
Sophia Mendes Rabelo — Engenharia de Software — contato: sophiamendesrabelo@gmail.com

### 1.6 Responsável principal (PI / dono do experimento)
Sophia Mendes Rabelo

### 1.7 Projeto / produto / iniciativa relacionada
Atividade acadêmica de Experimentação em Engenharia de Requisitos / Processos Ágeis.  
O experimento está ligado ao estudo de técnicas de escrita de critérios de aceite e seus impactos na implementação.

---

## 2. Contexto e problema

### 2.1 Descrição do problema / oportunidade

No ciclo de vida de desenvolvimento de software, a falha na engenharia de requisitos permanece como uma das principais causas de defeitos (bugs) e retrabalho. O problema torna-se crítico em interfaces de usuário (Front-end) de alta complexidade interativa, onde regras de validação dinâmica, gerenciamento de estados de componentes e feedbacks visuais precisam ser comunicados com precisão absoluta.

Atualmente, a indústria enfrenta um dilema na especificação desses critérios:

Linguagem Natural: permite detalhamento narrativo e contexto da experiência do usuário, mas sofre com ambiguidade sobre triggers de eventos e condições de exibição.

Notação Gherkin (BDD): busca remover a ambiguidade através de uma estrutura rígida (Dado/Quando/Então), mas impõe a fragmentação do comportamento da interface em múltiplos cenários desconectados.

A oportunidade deste estudo reside em investigar se, ao fragmentar regras de interface para atender ao formalismo do Gherkin, não se está introduzindo um “ponto cego” cognitivo: a perda de contexto sobre o ciclo de vida do componente, levando a erros de omissão. O objetivo é determinar empiricamente qual formato oferece maior segurança para a corretude do comportamento visual e eficiência na implementação de lógica de interface.

---

### 2.2 Contexto organizacional e técnico

O experimento será conduzido como um estudo controlado em ambiente acadêmico/simulado.

Cenário: simulação de uma etapa de implementação de front-end de uma funcionalidade crítica.

Participantes: o grupo amostral será composto por desenvolvedores front-end e QA, divididos aleatoriamente em dois grupos de tratamento.

Objeto de estudo: serão utilizados critérios de aceite de um componente rico de interface, desenhados especificamente para conter desafios de gerenciamento de estado e validação condicional.

Instrumentação: a coleta de dados será realizada via formulários eletrônicos onde os participantes deverão escrever a lógica de controle do componente (pseudocódigo ou script). O foco não é a estilização, mas sim a lógica de eventos, manipulação de estados e a densidade de bugs funcionais de interface inseridos.

---

### 2.3 Trabalhos e evidências prévias (internos e externos)

A fundamentação deste experimento combina teorias clássicas com evidências recentes do cenário ágil e de automação:

- Persistência do problema em ágil: dados recentes do 17th State of Agile Report (2024) indicam que “requisitos pouco claros” continuam entre as principais causas de falha em projetos, refutando a ideia de que processos ágeis eliminaram o problema da especificação. Estudos de Mendes & Silva (2023) corroboram que a ambiguidade gera um volume significativo de rework churn (taxa de retrabalho) mesmo em ciclos curtos.  

- Ambiguidade em user stories: pesquisas recentes sobre Processamento de Linguagem Natural (PLN), como as de Dalpiaz et al. (2021), apontam que user stories escritas puramente em linguagem natural apresentam “ambiguidade nociva” em cerca de 45% dos casos industriais, validando a necessidade de formalismos.  

- O “gap” humano na literatura de BDD: revisões sistemáticas recentes, como Zampetti et al. (2021) e Rahman (2023), demonstram que a pesquisa acadêmica sobre Gherkin está massivamente focada na geração automática de testes (muitas vezes via IA). Existe uma escassez crítica de estudos experimentais atuais que avaliem a leiturabilidade cognitiva da notação para o ser humano. Este trabalho preenche essa lacuna ao questionar se o desenvolvedor consegue compreender regras complexas “escondidas” atrás da estrutura rígida do Gherkin.

---

### 2.4 Referencial teórico e empírico essencial

- Behavior Driven Development (BDD): metodologia que utiliza a notação estruturada Gherkin para descrever comportamentos. O estudo foca no Gherkin como ferramenta de documentação para humanos, não apenas para máquinas.

Taxonomia de erros (métricas):  
- Erros de comissão (precisão): o desenvolvedor implementa algo errado por má interpretação de valores ou operadores (hipótese: maior incidência na linguagem natural).  
- Erros de omissão (contexto): o desenvolvedor deixa de implementar uma regra ou exceção por não visualizá-la na fragmentação dos cenários (hipótese: maior incidência no Gherkin em cenários complexos).

---

## 3. Objetivos e questões (Goal / Question / Metric)

### 3.1 Objetivo geral (goal template)

Analisar a notação Gherkin e a linguagem natural com o propósito de avaliação em relação ao tempo de desenvolvimento, à densidade de bugs de estado/validação e à corretude do comportamento, sob o ponto de vista de desenvolvedores de software, no contexto de uma tarefa simulada de codificação de um componente rico de interface com regras complexas.

### 3.2 Objetivos específicos

O1 (eficiência): comparar o tempo médio gasto para traduzir o requisito (Gherkin vs. texto) em lógica de controle de interface funcional.

O2 (corretude de estados): avaliar qual formato resulta em implementações mais fiéis ao ciclo de vida do componente (por exemplo, loading, sucesso, erro).

O3 (robustez/bugs): identificar qual formato induz a maior inserção de bugs em validações condicionais e tratamentos de exceção de interface.

O4 (retrabalho): mensurar a necessidade de correções posteriores baseada na qualidade da primeira entrega do código.  

---

### 3.3 Questões de pesquisa / de negócio

Relacionadas ao O1 (tempo/eficiência)

- Q1.1: desenvolvedores levam menos tempo para estruturar a lógica do componente quando guiados por passos estruturados (Gherkin)?  
- Q1.2: a leitura de texto corrido (linguagem natural) atrasa o início da codificação devido à necessidade de extrair as regras de interação?  
- Q1.3: existe diferença na produtividade entre os grupos?  

Relacionadas ao O2 (corretude de estados)

- Q2.1: qual grupo implementou o fluxo principal com maior taxa de sucesso?  
- Q2.2: a estrutura do Gherkin garante que todas as transições de estado sejam codificadas corretamente?  
- Q2.3: existe diferença significativa na implementação de estados de exceção entre os grupos?

Relacionadas ao O3 (bugs e exceções)

- Q3.1: qual formato gerou mais bugs de omissão?  
- Q3.2: qual formato gerou mais bugs de lógica de fluxo?  
- Q3.3: há diferença significativa entre os formatos na taxa de falhas de validação de entrada em edge cases?

Relacionadas ao O4 (retrabalho)

- Q4.1: quantas submissões de código seriam reprovadas em um code review por falharem em critérios de usabilidade ou validação?  
- Q4.2: existe diferença significativa no esforço estimado (tempo) para corrigir os bugs gerados por cada formato?  
- Q4.3: os defeitos encontrados tendem a ser de qual severidade dependendo do formato utilizado?

---

### 3.4 Métricas associadas (GQM)

| Objetivo       | Questão | Métricas (IDs) | O que se espera medir                                                                                |
|----------------|---------|----------------|-------------------------------------------------------------------------------------------------------|
| O1. Eficiência | Q1.1    | M01, M02       | Tempo total e variação para implementar a lógica a partir do requisito.                              |
|                | Q1.2    | M01a           | Tempo até iniciar a codificação e efeito do formato na largada.                                      |
|                | Q1.3    | M03            | Produtividade: regras corretas por minuto.                                                           |
| O2. Corretude  | Q2.1    | M04            | Sucesso no fluxo principal (“caminho feliz”).                                                        |
|                | Q2.2    | M05            | Cobertura das transições/estados descritos no requisito.                                             |
|                | Q2.3    | M05, M06, M07  | Implementação correta de estados de exceção; omissões e erros de lógica.                             |
| O3. Bugs       | Q3.1    | M06, M08       | Omissões de regras de interface e sua densidade relativa.                                            |
|                | Q3.2    | M07, M08       | Erros de lógica de fluxo e sua densidade relativa.                                                   |
|                | Q3.3    | M11            | Falhas em validações de entrada em casos de borda.                                                   |
| O4. Retrabalho | Q4.1    | M09, M10       | Taxa de reprovação em code review e esforço associado para correção.                                 |
|                | Q4.2    | M10            | Esforço de retrabalho estimado (tempo) para corrigir os bugs gerados.                                |
|                | Q4.3    | M12            | Severidade predominante dos defeitos por formato.                                                    |

---

| ID   | Nome da métrica                | Descrição da métrica                                                                                                              | Unidade             |
|------|--------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|---------------------|
| M01  | Tempo de implementação         | Tempo total gasto pelo desenvolvedor para ler o requisito e escrever a lógica do componente.                                     | Minutos/segundos    |
| M01a | Tempo de start-up              | Tempo desde a abertura do requisito até a primeira linha de código.                                                              | Minutos/segundos    |
| M02  | Desvio padrão do tempo         | Variação do tempo dentro do mesmo grupo.                                                                                         | Minutos             |
| M03  | Code velocity (interface)      | Razão entre o número de regras de interface atendidas corretamente e o tempo gasto (M01).                                        | Regras/minuto       |
| M04  | Acurácia do caminho feliz      | Indicador binário de que o fluxo principal de interação funciona corretamente.                                                   | Binária (0 ou 1)    |
| M05  | Cobertura de estados           | Percentual de estados de interface descritos que foram tratados no código.                                                       | Porcentagem (%)     |
| M06  | Bugs de omissão                | Contagem de comportamentos de interface exigidos que não foram implementados.                                                    | Contagem absoluta   |
| M07  | Bugs de lógica de fluxo        | Contagem de erros em condicionais de validação ou transições de estado incorretas.                                               | Contagem absoluta   |
| M08  | Densidade de defeitos          | (M06 + M07) dividido pelo número de regras/transições previstas no checklist de referência.                                      | Bugs/regra prevista |
| M09  | Taxa de rejeição (simulada)    | Classificação do código como "aprovado" ou "requer ajustes" funcionalmente.                                                      | Binária (pass/fail) |
| M10  | Esforço de retrabalho estimado | Estimativa de tempo para corrigir os bugs encontrados.                                                                           | Minutos (estimado)  |
| M11  | Falhas em casos de borda       | Contagem de falhas especificamente em validações de entrada e casos de borda; recorte temático de M06/M07.                      | Contagem absoluta   |
| M12  | Classificação de severidade    | Categorização do impacto do bug em níveis (baixo, médio, alto, bloqueante), tratada como escala ordinal na análise.             | Categórica (ordinal)|

---

## 4. Escopo e contexto do experimento

### 4.1 Escopo funcional / de processo (incluído e excluído)

Incluído (escopo do experimento):

- Lógica de interação do usuário: interpretação de regras sobre eventos de interface (clique, foco, digitação, hover).
- Gestão de estados visuais (state management): definição de regras para alternância de estados dos componentes (habilitado/desabilitado, carregando, visível/oculto, sucesso/erro).
- Lógica de validação no cliente: implementação de regras de feedback imediato ao usuário (mensagens de erro, cores de validação) baseadas nos critérios de aceite.
- Pseudocódigo de componentes: escrita da lógica funcional (por exemplo, funções JavaScript/TypeScript ou manipuladores de eventos) que controlam o comportamento da tela.

Excluído (fora do escopo):

- Estilização visual (CSS/styles): não será avaliada a fidelidade de cores, fontes, espaçamentos ou layout responsivo (pixel-perfect).
- Estrutura semântica (HTML): a hierarquia de tags não é objeto de avaliação, apenas a lógica atrelada a elas.
- Integração com backend: não será exigida a implementação real de chamadas de API (fetch/axios), apenas a simulação do tratamento de suas respostas (sucesso/falha).

---

### 4.2 Contexto do estudo (tipo de organização, projeto, experiência)

O estudo caracteriza-se como um experimento controlado simulando o desenvolvimento de front-end em um ambiente corporativo moderno.

- Tipo de organização: acadêmica/simulada.  
- Cenário do projeto: implementação de um componente de interface crítico em uma aplicação web (por exemplo, checkout ou formulário de registro complexo), onde a experiência do usuário depende estritamente do cumprimento das regras de comportamento.  
- Perfil dos participantes: amostragem composta por indivíduos com conhecimentos em desenvolvimento web (front-end ou fullstack) e garantia de qualidade.  
- Criticidade: o cenário foca em “usabilidade crítica”, onde falhas na lógica de interface (por exemplo, botão habilitado na hora errada) podem bloquear o usuário ou induzi-lo ao erro.

---

### 4.3 Premissas

Para a validade do experimento, assume-se que:

- Os participantes compreendem o conceito de “estados de interface” (loading, disabled, error etc.).  
- A complexidade do cenário está na interatividade.  
- O tempo reportado inclui a leitura da regra e a escrita da lógica do script, ignorando o tempo de estilização.

---

### 4.4 Restrições

O desenho experimental respeita as seguintes limitações práticas:

- Abstração visual: como o experimento é via formulário de texto, não é possível validar o “look and feel” visualmente. A validação será feita sobre a descrição lógica do comportamento.
- Independência de framework: o participante poderá escrever a solução pensando em React, Vue, Angular etc., desde que a lógica de controle de estado esteja clara.
- Tempo de execução: atividade limitada a 20–30 minutos para evitar fadiga cognitiva.

---

### 4.5 Limitações previstas

Fatores que podem ameaçar a validade externa:

- Subjetividade de UX: diferente do backend, regras de interface em linguagem natural podem ser interpretadas de formas variadas dependendo da bagagem de UX do desenvolvedor, o que pode ser confundido com erro de interpretação.  
- Falta de protótipo visual: a ausência de um layout (por exemplo, Figma) junto com o requisito textual pode aumentar a dificuldade artificialmente, já que no mundo real o front-end quase sempre trabalha com requisitos mais design visual.

---

## 5. Stakeholders, interesses e impactos

### 5.1 Stakeholders principais

- Pesquisador responsável: conduz o experimento, garante rigor metodológico e analisa os dados.
- Desenvolvedores (front-end/fullstack): público-alvo central; consomem os requisitos e são diretamente afetados por ambiguidade e carga cognitiva.
- Product owners (POs) / business analysts (BAs): autores dos critérios de aceite; interessados em reduzir ruídos de comunicação com o time técnico.
- Lideranças técnicas (tech leads / engineering managers): interessadas em reduzir lead time e retrabalho decorrente de falhas de especificação.
- Analistas de qualidade (QA): interessados na consistência entre o que foi especificado, implementado e testado.

### 5.2 Interesses e expectativas dos stakeholders

- Desenvolvedores: identificar o formato que melhor equilibra rapidez de leitura e clareza das regras de interface, reduzindo inferências e “adivinhações”.  
- POs/BAs: avaliar se o custo adicional de escrever em Gherkin se traduz em menos bugs; caso contrário, sustentar formatos híbridos ou mais leves.  
- Gestão técnica: obter evidências para padronizar a escrita de user stories, aumentando eficiência do fluxo e reduzindo retrabalho.

### 5.3 Impactos potenciais no processo / produto

Impacto no processo de refinamento:

- Se o Gherkin reduzir bugs de estado/validação em cenários complexos, recomenda-se seu uso obrigatório nesses casos, mesmo com maior esforço inicial.  
- Se a linguagem natural reduzir omissões por manter melhor contexto, recomenda-se seu uso como fonte primária de compreensão do desenvolvedor, deixando o Gherkin como apoio à automação de testes.

Impacto na qualidade do produto (front-end):

- Menos bugs de interface crítica: menor incidência de falhas de usabilidade.  
- Menos retrabalho: redução de rejeições em code review e de retornos de QA para desenvolvimento.  

---

## 6. Riscos de alto nível, premissas e critérios de sucesso

### 6.1 Riscos de alto nível (negócio, técnicos, etc.)

- Baixa adesão (amostragem insuficiente): risco de não atingir as 100 respostas válidas necessárias para conseguir realizar o cálculo estatístico planejado.  
- Heterogeneidade técnica: risco de discrepância forte de senioridade distorcer tempo e qualidade.  
- Fadiga ou abandono (drop-out): risco de o cenário ser longo/complexo, aumentando desistência.  
- Contaminação por IA generativa: risco de uso de modelos de inteligência artificial para gerar solução, invalidando a medida de esforço cognitivo humano.  
- Viés de design: risco de o erro ocorrer por preferência pessoal do participante, e não por leitura do requisito.  

---

### 6.2 Critérios de sucesso globais (go / no-go)

- Tamanho da amostra (mínimo):  
  - GO: obter 80 ou mais respostas válidas.  
  - NO-GO: obter menos de 60 respostas válidas.  

- Qualidade dos dados:  
  - GO: pelo menos 80% das submissões contêm código inteligível.  
  - NO-GO: menos de 70% das submissões contêm código inteligível.  

- Balanceamento dos grupos:  
  - GO: distribuição equilibrada entre Grupo A (linguagem natural) e Grupo B (Gherkin) em termos de senioridade e familiaridade com Gherkin.  
  - NO-GO: desequilíbrio relevante entre os grupos em senioridade ou familiaridade com Gherkin, indicando viés técnico.  

---

### 6.3 Critérios de parada antecipada (pré-execução)

- Falha no teste piloto: se participantes do piloto reportarem cenário incompreensível ou levarem mais de 40 minutos, os requisitos devem ser reescritos.  
- Inviabilidade técnica da ferramenta: se o formulário não suportar bem blocos de código, inviabilizando análise posterior.  
- Desvio crítico de interpretação: se os primeiros cinco participantes errarem o “caminho feliz”, isso indica má formulação do enunciado e o requisito deve ser revisado antes de continuar a divulgação.

---

## 7. Modelo conceitual e hipóteses

### 7.1 Modelo conceitual do experimento

O formato dos critérios de aceite (Gherkin vs. linguagem natural) altera como o desenvolvedor lê, extrai e organiza regras de interface. Essa mudança afeta a carga cognitiva, a manutenção do contexto do ciclo de vida do componente e a chance de ambiguidade ou omissão, influenciando diretamente tempo, corretude de estados, bugs e retrabalho.

### 7.2 Hipóteses formais (H0, H1)

| Objetivo                  | Questão                                | Métrica(s)           | Hipótese nula (H0)                                                                                            | Hipótese alternativa (H1)                                                                      | Cauda     |
|---------------------------|----------------------------------------|----------------------|---------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|-----------|
| O1 – Eficiência           | Q1.1 – Tempo total                     | M01                  | Não há diferença no tempo total médio de implementação entre LN (A) e GH (B).                                 | O tempo total médio de implementação é menor em GH (B) do que em LN (A).                      | Unicaudal |
| O1 – Eficiência           | Q1.2 – Start-up                        | M01a                 | Não há diferença no tempo médio até a primeira linha de código entre LN (A) e GH (B).                         | O tempo médio até a primeira linha de código é menor em GH (B) do que em LN (A).              | Unicaudal |
| O1 – Eficiência           | Q1.3 – Produtividade                   | M03                  | Não há diferença na produtividade média (regras corretas por minuto) entre LN (A) e GH (B).                   | A produtividade média difere entre LN (A) e GH (B).                                           | Bicaudal  |
| O2 – Corretude de estados | Q2.1 – Caminho feliz                   | M04                  | A taxa de sucesso do “caminho feliz” é igual entre LN (A) e GH (B).                                           | A taxa de sucesso do “caminho feliz” é maior em GH (B) do que em LN (A).                      | Unicaudal |
| O2 – Corretude de estados | Q2.2 – Cobertura de estados/transições | M05                  | A cobertura média de estados e transições é igual entre LN (A) e GH (B).                                      | A cobertura média de estados e transições é maior em LN (A) do que em GH (B).                 | Unicaudal |
| O2 – Corretude de estados | Q2.3 – Estados de exceção              | M05, M06, M07        | Não há diferença entre LN (A) e GH (B) na implementação de estados de exceção (cobertura, omissões e lógica). | LN (A) apresenta maior cobertura de estados de exceção e menor taxa de omissões do que GH (B).| Unicaudal |
| O3 – Bugs e exceções      | Q3.1 – Bugs de omissão                 | M06 (impacto em M08) | A média de bugs de omissão é igual entre LN (A) e GH (B).                                                     | A média de bugs de omissão é maior em GH (B) do que em LN (A).                                | Unicaudal |
| O3 – Bugs e exceções      | Q3.2 – Bugs de lógica de fluxo         | M07 (impacto em M08) | A média de bugs de lógica de fluxo é igual entre LN (A) e GH (B).                                             | A média de bugs de lógica de fluxo é menor em GH (B) do que em LN (A).                        | Unicaudal |
| O3 – Bugs e exceções      | Q3.3 – Edge cases de input             | M11                  | A taxa média de falhas em casos de borda de entrada é igual entre LN (A) e GH (B).                            | A taxa média de falhas em casos de borda de entrada difere entre LN (A) e GH (B).             | Bicaudal  |
| O4 – Retrabalho           | Q4.1 – Taxa de rejeição simulada       | M09                  | A taxa de rejeição simulada em code review é igual entre LN (A) e GH (B).                                     | A taxa de rejeição simulada (“requer ajustes”) é maior em GH (B) do que em LN (A).            | Unicaudal |
| O4 – Retrabalho           | Q4.2 – Esforço de retrabalho           | M10                  | O esforço médio de retrabalho (tempo) é igual entre LN (A) e GH (B).                                          | O esforço médio de retrabalho (tempo) é menor em LN (A) do que em GH (B).                     | Unicaudal |
| O4 – Retrabalho           | Q4.3 – Severidade dos defeitos         | M12                  | A distribuição de severidade dos defeitos é igual entre LN (A) e GH (B).                                      | A proporção de defeitos de severidade maior/bloqueante é menor em LN (A) do que em GH (B).    | Unicaudal |

### 7.3 Nível de significância e considerações de poder

Será adotado nível de significância α = 0,05, aceitando até 5% de chance de erro tipo I.

Poder estatístico:

- Meta ideal: cerca de 100 respostas válidas (aproximadamente 50 por grupo), com poder esperado próximo de 80% para detectar efeitos moderados.  
- Mínimo aceitável (GO): 80 ou mais respostas válidas (aproximadamente 40 por grupo), ainda com poder razoável, mas um pouco menor.  
- Abaixo de 60 respostas (NO-GO): poder muito baixo, com alto risco de erro tipo II, exigindo replanejamento ou nova coleta.

---

## 8. Variáveis, fatores, tratamentos e objetos de estudo

### 8.1 Objetos de estudo

Os principais objetos de estudo deste experimento são:

- Critérios de aceite de um componente rico de interface, preparados em dois formatos:
  - Linguagem natural (LN): texto corrido, narrativo, descrevendo o comportamento esperado da tela.
  - Notação Gherkin (GH): mesmos critérios de aceite reescritos em cenários estruturados (dado/quando/então).
- Submissões de solução dos participantes, compostas por:
  - Pseudocódigo ou trechos de script (JavaScript/TypeScript ou similar) representando a lógica de controle de interface.
  - Respostas a perguntas complementares, quando houver (por exemplo, percepção de dificuldade ou familiaridade com o formato).

É sobre esses artefatos (requisito em formatos distintos mais código/pseudocódigo produzido) que serão calculadas as métricas M01–M12.

---

### 8.2 Sujeitos / participantes (visão geral)

Os participantes serão:

- Desenvolvedores web com conhecimento em front-end ou fullstack; e  
- Profissionais/estudantes de QA com experiência em criticar/compreender critérios de aceite.

Em termos de perfil:

- Podem ser estudantes de graduação em computação/engenharia de software ou profissionais em início/meio de carreira.  
- Espera-se que tenham familiaridade básica com desenvolvimento web (eventos, estados, validação no cliente).  
- O nível de experiência (júnior, pleno, sênior) será coletado, mas não faz parte do fator principal do estudo.

---

### 8.3 Variáveis independentes (fatores) e seus níveis

O experimento possui um fator principal manipulado:

- Fator F1 – formato dos critérios de aceite (requisito de interface)  
  - Nível A – linguagem natural (LN)  
  - Nível B – Gherkin (GH)  

---

### 8.4 Tratamentos (condições experimentais)

O experimento adota um desenho entre sujeitos, em que cada participante vê apenas um formato de requisito:

- Tratamento T1 – Grupo A: linguagem natural (LN)  
  - O participante recebe a descrição da funcionalidade em texto corrido.  
  - Deve ler o enunciado e escrever a lógica de controle da interface.  
  - Todas as métricas M01–M12 são calculadas com base na solução produzida a partir desse formato.

- Tratamento T2 – Grupo B: Gherkin (GH)  
  - O participante recebe o mesmo conjunto de regras, reescrito em cenários Gherkin (dado/quando/então).  
  - Deve ler os cenários e escrever a lógica de controle da interface.  
  - As mesmas métricas M01–M12 são calculadas, permitindo comparação direta com o Grupo A.

A tarefa funcional é equivalente entre os grupos; a única diferença experimental é o formato de apresentação do requisito.

---

### 8.5 Variáveis dependentes (respostas)

As variáveis dependentes são as métricas de resultado já definidas na seção 3.4, derivadas das soluções submetidas:

Tempo / eficiência  
- M01 – tempo total de implementação.  
- M01a – tempo até a primeira linha de código.  
- M02 – desvio padrão do tempo.  
- M03 – code velocity.  

Corretude / cobertura de estados  
- M04 – acurácia do caminho feliz.  
- M05 – cobertura de estados/transições.  

Bugs e defeitos de lógica  
- M06 – bugs de omissão.  
- M07 – bugs de lógica de fluxo.  
- M08 – densidade de defeitos.  
- M11 – falhas em casos de borda.  

Retrabalho / impacto  
- M09 – taxa de rejeição simulada em code review.  
- M10 – esforço de retrabalho estimado.  
- M12 – classificação de severidade dos defeitos.  

---

### 8.6 Variáveis de controle / bloqueio

- Tipo de tarefa/componente: todos os participantes implementam o mesmo cenário de interface, com os mesmos estados, regras e nível de complexidade.  
- Ambiente de resposta: uso do mesmo formulário eletrônico, com instruções idênticas, campos iguais para todos e limite de tempo semelhante.  
- Idioma e contexto do enunciado: requisitos fornecidos em português, com vocabulário compatível com o público-alvo.  

---

### 8.7 Possíveis variáveis de confusão conhecidas

Alguns fatores podem influenciar os resultados sem fazer parte do fator principal:

- Motivação e engajamento do participante: pessoas mais motivadas tendem a ler com mais atenção e codar com mais cuidado, reduzindo bugs independentemente do formato do requisito.  
- Fadiga e contexto de execução: participantes fazendo o experimento após um dia cheio de trabalho/aula podem estar mais cansados, afetando tempo e qualidade de implementação.  
- Uso de ferramentas externas: se o participante recorrer a modelos de IA ou copiar código pronto, isso distorce as medidas de esforço cognitivo e de omissão. Será necessário inibir explicitamente o uso dessas ferramentas.  
- Multitarefa e interrupções: o participante pode alternar entre janelas ou ser interrompido durante a tarefa, inflando artificialmente o tempo medido.  
- Variedade de dispositivos e ambiente físico: diferenças entre usar notebook, monitor grande ou celular, bem como ambiente barulhento versus silencioso, podem impactar a fluidez de leitura e codificação.  

---

## 9. Desenho experimental

### 9.1 Tipo de desenho (completamente randomizado, blocos, fatorial, etc.)

O estudo adotará um desenho experimental completamente randomizado entre sujeitos, em que cada participante é exposto a apenas um dos formatos de requisito (linguagem natural ou Gherkin), compondo dois grupos independentes: Grupo A (LN) e Grupo B (GH). A comparação entre os grupos será feita a partir das métricas M01–M12, tratadas como respostas às diferentes condições experimentais.

Esse tipo de desenho é adequado ao problema porque evita efeitos de aprendizagem (o participante não resolve a mesma tarefa duas vezes em formatos distintos) e reduz o risco de contaminação, ou seja, de o entendimento construído em um formato influenciar a leitura do outro. Além disso, ele se encaixa bem nas restrições práticas do estudo, especialmente o fato de a coleta ser online, com participantes entrando em momentos distintos e realizando a tarefa em uma única sessão.

### 9.2 Randomização e alocação

A randomização será aplicada aos sujeitos, definindo em qual formato de requisito cada participante irá trabalhar. Cada pessoa receberá um identificador e, a partir desse identificador, um pequeno script de sorteio fará a alocação para um dos dois grupos: Grupo A (linguagem natural) ou Grupo B (Gherkin). Essa alocação será registrada em uma planilha ou base simples, associando o ID do participante ao grupo e ao link do formulário correspondente.

### 9.3 Balanceamento e contrabalanço

O balanceamento entre os grupos será feito acompanhando o número de respostas em LN e GH e ajustando a randomização, se necessário, para que os tamanhos fiquem semelhantes. Também serão coletados dados de perfil (experiência em desenvolvimento web e familiaridade com Gherkin/BDD) para verificar se houve desequilíbrio de senioridade. Caso isso ocorra, podem ser feitas análises estratificadas ou ajustes estatísticos usando essas variáveis.

Em relação ao contrabalanço, ele não é necessário neste estudo, pois o desenho é entre sujeitos e cada participante realiza apenas uma tarefa em um único formato. Não há efeito de ordem entre tratamentos.

### 9.4 Número de grupos e sessões

- Número de grupos: 2 grupos independentes  
  - Grupo A: linguagem natural (LN)  
  - Grupo B: Gherkin (GH)  

Cada participante participa de apenas uma sessão e resolve uma tarefa principal, sempre em um único formato de requisito, de acordo com o grupo em que foi alocado. Esse arranjo reduz o esforço individual, diminui o risco de fadiga e evita efeitos de aprendizagem cruzada, já que o participante não repete a mesma tarefa em outro formato.

---

## 10. População, sujeitos e amostragem

### 10.1 População-alvo

A população-alvo deste experimento são profissionais e estudantes que atuam ou se preparam para atuar com desenvolvimento web, em especial:

- Desenvolvedores front-end ou fullstack que lidam com user stories, critérios de aceite e implementação de componentes de interface em aplicações web modernas.  
- Profissionais e estudantes de QA que tenham familiaridade com leitura de critérios de aceite e verificação de comportamento de interface.  

Em termos de contexto real, o experimento busca representar principalmente desenvolvedores que trabalham em times de produto web com práticas inspiradas em métodos ágeis (user stories, critérios de aceite, BDD opcional).

### 10.2 Critérios de inclusão de sujeitos

Serão incluídos no experimento participantes que atendam, cumulativamente, aos seguintes requisitos mínimos:

- Ter 18 anos ou mais.  
- Ter experiência prévia com desenvolvimento web, ainda que em nível iniciante (por exemplo, já ter implementado telas com HTML/CSS/JavaScript ou frameworks como React, Vue ou Angular).  
- Conseguir ler e compreender critérios de aceite em português.  
- Ter disponibilidade de aproximadamente 20–30 minutos contínuos para realizar a tarefa sem interrupções significativas.  
- Aceitar participar voluntariamente do estudo, conforme apresentação dos objetivos e termos do experimento.  

### 10.3 Critérios de exclusão de sujeitos

Serão excluídos da análise (ou não convidados a prosseguir) participantes que:

- Declararem não ter qualquer experiência prévia com desenvolvimento web (por exemplo, nunca terem implementado uma tela ou lógica de interface).  
- Não completarem a tarefa principal (ausência de código/pseudocódigo ou submissão claramente em branco ou aleatória).  
- Declararem ter utilizado ferramentas automáticas de geração de código (por exemplo, IA generativa) para produzir a solução, comprometendo a observação do esforço cognitivo individual.  
- Apresentarem conflito direto de interesse (por exemplo, serem coautores do experimento ou terem acesso prévio às respostas esperadas).  

### 10.4 Tamanho da amostra planejado (por grupo)

O tamanho de amostra planejado considera tanto a viabilidade prática de recrutamento quanto as necessidades de poder estatístico:

- Meta ideal: aproximadamente 100 participantes válidos, distribuídos em torno de 50 por grupo (LN e GH).  
- Mínimo aceitável (GO): pelo menos 80 participantes válidos, com cerca de 40 por grupo, conforme critérios definidos na seção 6.2.  
- Limite de alerta (NO-GO): menos de 60 participantes válidos (cerca de 30 por grupo), situação em que o estudo passa a ter alto risco de erro do tipo II e pode demandar replanejamento.  

Esse tamanho é considerado suficiente para detectar efeitos moderados nas principais métricas (tempo, omissão de regras, cobertura de estados, taxa de rejeição simulada), mantendo um equilíbrio entre rigor estatístico e esforço de coleta.

### 10.5 Método de seleção / recrutamento

Os participantes serão recrutados por amostragem de conveniência, a partir de:

- Turmas de graduação em computação/engenharia de software de instituição acadêmica relacionada ao projeto.  
- Comunidades de tecnologia (por exemplo, grupos em redes sociais, Discord, Slack ou listas de e-mail de desenvolvedores).  
- Contatos em redes profissionais (LinkedIn, grupos de ex-alunos etc.), quando pertinente.  

O convite explicará o objetivo do estudo, o tempo estimado de participação e esclarecerá que se trata de uma pesquisa acadêmica, sem avaliação individual de desempenho. Não haverá seleção probabilística formal; porém, a diversidade de canais de divulgação ajuda a obter uma amostra heterogênea em termos de experiência.

### 10.6 Treinamento e preparação dos sujeitos

Não será oferecido um treinamento técnico aprofundado, pois o objetivo é observar como os participantes lidam com critérios de aceite em condições próximas da prática real. Entretanto, serão fornecidas:

- Instruções claras no início do formulário, explicando o objetivo geral da atividade, o tipo de solução esperada (pseudocódigo ou script focado na lógica de interface, não em estilização) e a recomendação de não usar IA generativa ou copiar código pronto.  
- Um exemplo simples ilustrativo (não relacionado à tarefa principal), apenas para deixar claro o formato de resposta desejado, como um pequeno trecho de pseudocódigo de validação padrão.  

Esse material tem como finalidade nivelar expectativas mínimas sobre o tipo de entrega, sem ensinar a resolver o problema em si, reduzindo viés de interpretação associado apenas ao formato do requisito.

---

## 11. Instrumentação e protocolo operacional

### 11.1 Instrumentos de coleta (questionários, logs, planilhas, etc.)

- Formulário eletrônico principal:  
  - Contendo termos de participação, instruções, perguntas de perfil (experiência, familiaridade com Gherkin) e o enunciado da tarefa (LN ou GH, conforme grupo).  
  - Incluindo campos para inserção de código/pseudocódigo da solução.  

- Planilha de consolidação de dados:  
  - Para registrar identificadores dos participantes, grupo de tratamento (LN/GH), tempos, métricas derivadas e variáveis de perfil.  

- Scripts de apoio à análise:  
  - Para extração, limpeza e cálculo das métricas M01–M12 a partir das respostas textuais e anotações de avaliação.  

- Checklist de avaliação da solução:  
  - Documento estruturado com a lista de regras de interface, estados e casos de borda esperados, utilizado pelos avaliadores para contabilizar M04–M08, M11 e M12.  

- Questionário final opcional:  
  - Para coletar impressões subjetivas (percepção de dificuldade, clareza do requisito), a serem analisadas qualitativamente e, eventualmente, de forma descritiva.  

### 11.2 Materiais de suporte (instruções, guias)

Para apoiar a execução do experimento, serão preparados:

- Um texto de instruções iniciais explicando o contexto geral da tarefa, deixando claro que o foco está na lógica de estados, validações e comportamento da interface, informando o tempo estimado de realização (em torno de 20–30 minutos) e descrevendo as regras para não uso de IA generativa, bem como a recomendação de evitar interrupções prolongadas durante a execução.

- Um guia rápido para avaliadores, descrevendo como aplicar o checklist de avaliação, como interpretar cada tipo de bug (omissão, lógica de fluxo e edge case) e como registrar as métricas em planilha de forma consistente.

Esses materiais têm o objetivo de reduzir variações de interpretação tanto por parte dos participantes quanto por parte de quem avalia as respostas.

### 11.3 Procedimento experimental (protocolo – visão passo a passo)

![fluxograma operacional do experimento](fluxogramaTCC.png)

### 11.4 Plano de piloto (se haverá piloto, escopo e critérios de ajuste)

Antes da coleta principal, será realizado um piloto de pequeno porte com aproximadamente 5 a 10 participantes da mesma população-alvo (por exemplo, colegas de curso ou desenvolvedores próximos). Esse piloto terá como objetivos verificar se o enunciado da tarefa está claro e compreensível em ambos os formatos (LN e GH), validar se o tempo estimado de 20–30 minutos é realista e não causa fadiga excessiva, e testar o fluxo técnico do formulário, incluindo a inserção de código e a coleta de tempos e perfis.

Após o piloto, serão realizados ajustes sempre que necessário: se a maioria dos participantes relatar dificuldade para entender o cenário ou levar mais de 40 minutos, o requisito será reescrito ou simplificado; se o formulário apresentar problemas técnicos (por exemplo, campos que não aceitam bem código), a ferramenta ou o formato será ajustado; e pequenos ajustes de texto poderão ser feitos para melhorar a clareza das instruções, desde que não alterem o conteúdo lógico do requisito. Caso sejam feitas mudanças substanciais no enunciado ou no protocolo após o piloto, os dados coletados nessa fase não serão incluídos na análise final.

---

## 12. Plano de análise de dados (pré-execução)

### 12.1 Estratégia geral de análise (como responderá às questões)

A estratégia geral de análise será guiada pelos objetivos O1–O4 e pelas questões Q1.1–Q4.3, utilizando as métricas M01–M12 como variáveis dependentes. Em linhas gerais, serão realizadas:

- Análises descritivas iniciais (médias, medianas, desvios, distribuições) para caracterizar os grupos LN e GH em termos de tempo, bugs, cobertura de estados e retrabalho.  
- Comparações entre grupos (LN vs. GH) para cada métrica relevante, a fim de testar as hipóteses H0/H1 definidas na seção 7.2.  
- Análises estratificadas ou com controle de covariáveis, quando necessário, para verificar se padrões se mantêm ao considerar níveis de experiência (ExpDev) e familiaridade com Gherkin (FamGH).  
- Integração de evidências quantitativas com comentários qualitativos dos participantes, quando disponíveis, para interpretar melhor o “ponto cego” potencial do Gherkin em cenários complexos.  

### 12.2 Métodos estatísticos planejados

Considerando que os dados podem não seguir distribuição normal e que algumas métricas são ordinais ou binárias, a análise deverá priorizar testes não paramétricos ou adequados ao tipo de variável:

- Para métricas contínuas ou quase contínuas (M01, M01a, M02, M03, M05, M08, M10):  
  - Testes de comparação entre dois grupos independentes, como Mann–Whitney U.  

- Para métricas binárias (M04, M09):  
  - Comparação de proporções entre LN e GH usando teste qui-quadrado de independência ou teste exato de Fisher, conforme o tamanho das células.  

- Para métricas ordinais/categóricas ordinais (M12 – severidade):  
  - Uso de testes como Mann–Whitney U ou qui-quadrado para tendência, conforme o formato dos dados.  

- Quando houver interesse em controlar efeitos de covariáveis (experiência, familiaridade com Gherkin), poderão ser explorados modelos simples de regressão, com o grupo (LN/GH) como variável explicativa e as covariáveis de perfil como controles.

Em todos os casos, será adotado nível de significância α = 0,05, e serão reportados não apenas p-valores, mas também tamanhos de efeito e interpretações práticas dos resultados.

### 12.3 Tratamento de dados faltantes e outliers

- Dados faltantes críticos: submissões sem código/pseudocódigo ou sem tempo registrado de execução serão classificadas como inválidas para análise das métricas principais e poderão ser excluídas do conjunto principal de análise.  

- Dados parcialmente faltantes: se faltarem apenas respostas de perfil ou de questionário final, mas o código e o tempo estiverem presentes, a submissão poderá ser utilizada nas análises que não dependam dessas variáveis ausentes.  

- Outliers de tempo: tempos extremamente altos ou baixos serão inspecionados caso a caso, considerando possíveis interrupções, erros de registro ou comportamento não engajado.  

Em relatórios e interpretações, será sempre indicado quantos participantes foram excluídos por problemas de dados e por quais critérios.

### 12.4 Plano de análise para dados qualitativos (se houver)

Caso sejam coletados dados qualitativos, será feita uma análise de caráter descritivo e categorial, com foco em entender percepções sobre clareza, esforço e possíveis “pontos cegos” dos formatos de requisito.

Os principais passos serão:

- Leitura exploratória dos comentários para familiarização com o conteúdo.  
- Codificação inicial dos trechos em temas recorrentes.  
- Agrupamento dos códigos em categorias mais amplas, como:
  - clareza percebida  
  - esforço cognitivo  
  - facilidade de encontrar exceções/estados  
  - frustração ou satisfação com o formato  
- Contagem de frequências por categoria, comparando, quando possível, padrões entre participantes de LN e GH.  
- Uso de exemplos ilustrativos anonimizados para reforçar a interpretação dos resultados.

Essas análises não terão peso estatístico formal, mas servirão para interpretar e contextualizar os resultados numéricos.

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

