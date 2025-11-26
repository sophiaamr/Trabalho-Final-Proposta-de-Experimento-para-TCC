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
- **v3.0 (26/11/2025):** seções 7,8,9

### 1.4 Datas (criação, última atualização)
- **Data de criação:** 21/11/2025  
- **Última atualização:** 26/11/2025

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

**Q1.3:** Existe diferença na produtividade entre os grupos?  


### Relacionadas ao O2 (Corretude de Estados)

**Q2.1:** Qual grupo implementou o fluxo principal com maior taxa de sucesso?  

**Q2.2:** A estrutura do Gherkin garante que todas as transições de estado  sejam codificadas corretamente?  

**Q2.3:** Existe diferença significativa na implementação de estados de exceção entre os grupos?

### Relacionadas ao O3 (Bugs e Exceções)

**Q3.1:** Qual formato gerou mais bugs de omissão?  

**Q3.2:** Qual formato gerou mais bugs de lógica condicional?  

**Q3.3:**: Há diferença significativa entre os formatos na taxa de falhas de validação de entrada em edge cases?

### Relacionadas ao O4 (Retrabalho)

**Q4.1:** Quantas submissões de código seriam reprovadas em um Code Review por falharem em critérios de usabilidade ou validação?  

**Q4.2**: Existe diferença significativa no esforço estimado (tempo) para corrigir os bugs gerados por cada formato?

**Q4.3**: Os defeitos encontrados tendem a ser de qual severidade dependendo do formato utilizado?

### 3.4 Métricas associadas (GQM)

| Objetivo      | Questão | Métricas (IDs) | O que se espera medir                                                                                |
|---------------|---------|----------------|-------------------------------------------------------------------------------------------------------|
| O1. Eficiência| Q1.1    | M01, M02       | Tempo total e variação para implementar a lógica a partir do requisito.                              |
|               | Q1.2    | M01a           | Tempo até iniciar a codificação e efeito do formato na largada.                           |
|               | Q1.3    | M03            | Produtividade: regras corretas por minuto.                                                           |
| O2. Corretude | Q2.1    | M04            | Sucesso no fluxo principal (“caminho feliz”).                                                        |
|               | Q2.2    | M05            | Cobertura das transições/estados descritos no requisito.                                            |
|               | Q2.3    | M05, M06, M07  | Implementação correta de estados de exceção; omissões e erros de lógica.                             |
| O3. Bugs      | Q3.1    | M06, M08       | Omissões de regras de UI e sua densidade relativa.                                                   |
|               | Q3.2    | M07, M08       | Erros de lógica de fluxo e sua densidade relativa.                                                   |
|               | Q3.3    | M11            | Falhas em validações de entrada em casos de borda.                                                   |
| O4. Retrabalho| Q4.1    | M09, M10       | Taxa de reprovação em code review e esforço associado para correção.                                 |
|               | Q4.2    | M10            | Esforço de retrabalho estimado (tempo) para corrigir os bugs gerados.                                |
|               | Q4.3    | M12            | Severidade predominante dos defeitos por formato.                                                    |



| ID   | Nome da Métrica                | Descrição da Métrica                                                                                                              | Unidade             |
|------|--------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|---------------------|
| M01  | Tempo de Implementação         | Tempo total gasto pelo desenvolvedor para ler o requisito e escrever a lógica do componente.                                     | Minutos/Segundos    |
| M01a | Tempo de Start-up              | Tempo desde a abertura do requisito até a primeira linha de código.                                                              | Minutos/Segundos    |
| M02  | Desvio Padrão do Tempo         | Variação do tempo dentro do mesmo grupo.                                                                                         | Minutos             |
| M03  | Code Velocity (UI)             | Razão entre o número de regras de interface atendidas corretamente e o tempo gasto (M01).                                        | Regras/Minuto       |
| M04  | Acurácia do Caminho Feliz      | Indicador binário de que o fluxo principal de interação funciona corretamente.                                                   | Binária (0 ou 1)    |
| M05  | Cobertura de Estados           | Percentual de estados de interface descritos que foram tratados no código.                                                       | Porcentagem (%)     |
| M06  | Bugs de Omissão                | Contagem de comportamentos de interface exigidos que não foram implementados.                                                    | Contagem Absoluta   |
| M07  | Bugs de Lógica de Fluxo        | Contagem de erros em condicionais de validação ou transições de estado incorretas.                                               | Contagem Absoluta   |
| M08  | Densidade de Defeitos          | (M06 + M07) dividido pelo número de regras/transições previstas no checklist de referência.                                      | Bugs/Regra Prevista |
| M09  | Taxa de Rejeição (Simulada)    | Classificação do código como "Aprovado" ou "Requer Ajustes" funcionalmente.                                                      | Binária (Pass/Fail) |
| M10  | Esforço de Retrabalho Estimado | Estimativa de tempo para corrigir os bugs encontrados.                                                                           | Minutos (Estimado)  |
| M11  | Falhas em Casos de Borda       | Contagem de falhas especificamente em validações de entrada e casos de borda. M11 é um recorte temático de M06/M07.             | Contagem Absoluta   |
| M12  | Classificação de Severidade    | Categorização do impacto do bug em níveis (Baixo, Médio, Alto, Bloqueante) pode ser tratada como escala ordinal na análise.| Categórica (Ordinal) |



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
- **Menos bugs de interface crítica:** menor incidência de falhas de usabilidade.
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
  - **GO:** obter ≥ 80 respostas válidas.  
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

O formato dos critérios de aceite (Gherkin vs. Linguagem Natural) altera como o desenvolvedor lê, extrai e organiza regras de interface. Essa mudança afeta a carga cognitiva, a manutenção do contexto do ciclo de vida do componente e a chance de ambiguidade ou omissão, influenciando diretamente tempo, corretude de estados, bugs e retrabalho

### 7.2 Hipóteses formais (H0, H1)

| Objetivo                  | Questão                                | Métrica(s)           | Hipótese Nula (H0)                                                                                            | Hipótese Alternativa (H1)                                                                      | Cauda     |
| ------------------------- | -------------------------------------- | -------------------- | ------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| O1 – Eficiência           | Q1.1 – Tempo total                     | M01                  | Não há diferença no tempo total médio de implementação entre LN (A) e GH (B).                                 | O tempo total médio de implementação é menor em GH (B) do que em LN (A).                       | Unicaudal |
| O1 – Eficiência           | Q1.2 – Start-up                        | M01a                 | Não há diferença no tempo médio até a primeira linha de código entre LN (A) e GH (B).                         | O tempo médio até a primeira linha de código é menor em GH (B) do que em LN (A).               | Unicaudal |
| O1 – Eficiência           | Q1.3 – Produtividade                   | M03                  | Não há diferença na produtividade média (regras corretas por minuto) entre LN (A) e GH (B).                   | A produtividade média difere entre LN (A) e GH (B).                                            | Bicaudal  |
| O2 – Corretude de Estados | Q2.1 – Caminho feliz                   | M04                  | A taxa de sucesso do “caminho feliz” é igual entre LN (A) e GH (B).                                           | A taxa de sucesso do “caminho feliz” é maior em GH (B) do que em LN (A).                       | Unicaudal |
| O2 – Corretude de Estados | Q2.2 – Cobertura de estados/transições | M05                  | A cobertura média de estados e transições é igual entre LN (A) e GH (B).                                      | A cobertura média de estados e transições é maior em LN (A) do que em GH (B).                  | Unicaudal |
| O2 – Corretude de Estados | Q2.3 – Estados de exceção              | M05, M06, M07        | Não há diferença entre LN (A) e GH (B) na implementação de estados de exceção (cobertura, omissões e lógica). | LN (A) apresenta maior cobertura de estados de exceção e menor taxa de omissões do que GH (B). | Unicaudal |
| O3 – Bugs e Exceções      | Q3.1 – Bugs de omissão                 | M06 (impacto em M08) | A média de bugs de omissão é igual entre LN (A) e GH (B).                                                     | A média de bugs de omissão é maior em GH (B) do que em LN (A).                                 | Unicaudal |
| O3 – Bugs e Exceções      | Q3.2 – Bugs de lógica de fluxo         | M07 (impacto em M08) | A média de bugs de lógica de fluxo é igual entre LN (A) e GH (B).                                             | A média de bugs de lógica de fluxo é menor em GH (B) do que em LN (A).                         | Unicaudal |
| O3 – Bugs e Exceções      | Q3.3 – Edge cases de input             | M11                  | A taxa média de falhas em casos de borda de entrada é igual entre LN (A) e GH (B).                            | A taxa média de falhas em casos de borda de entrada difere entre LN (A) e GH (B).              | Bicaudal  |
| O4 – Retrabalho           | Q4.1 – Taxa de rejeição simulada       | M09                  | A taxa de rejeição simulada em code review é igual entre LN (A) e GH (B).                                     | A taxa de rejeição simulada (“Requer Ajustes”) é maior em GH (B) do que em LN (A).             | Unicaudal |
| O4 – Retrabalho           | Q4.2 – Esforço de retrabalho           | M10                  | O esforço médio de retrabalho (tempo) é igual entre LN (A) e GH (B).                                          | O esforço médio de retrabalho (tempo) é menor em LN (A) do que em GH (B).                      | Unicaudal |
| O4 – Retrabalho           | Q4.3 – Severidade dos defeitos         | M12                  | A distribuição de severidade dos defeitos é igual entre LN (A) e GH (B).                                      | A proporção de defeitos de severidade Maior/Bloqueante é menor em LN (A) do que em GH (B).     | Unicaudal |

### 7.3 Nível de significância e considerações de poder

Será adotado nível de significância α = 0,05, aceitando até 5% de chance de erro Tipo I

Poder estatístico:

**Meta ideal:** ~100 respostas válidas (≈ 50 por grupo) → poder esperado próximo de 80% para detectar efeitos moderados.

**Mínimo aceitável (GO):** ≥ 80 respostas válidas (≈ 40 por grupo) → poder ainda razoável, mas um pouco menor.

**Abaixo de 60 respostas (NO-GO):** poder muito baixo, com alto risco de erro Tipo II, exigindo replanejamento ou nova coleta.

---

## 8. Variáveis, fatores, tratamentos e objetos de estudo

## 8. Variáveis, fatores, tratamentos e objetos de estudo

### 8.1 Objetos de estudo

Os principais objetos de estudo deste experimento são:

- **Critérios de aceite de um componente rico de interface**, preparados em dois formatos:
  - **Linguagem Natural (LN):** texto corrido, narrativo, descrevendo o comportamento esperado da tela.
  - **Notação Gherkin (GH):** mesmos critérios de aceite reescritos em cenários estruturados (Dado/Quando/Então).

- **Submissões de solução dos participantes**, compostas por:
  - **Pseudocódigo ou trechos de script** (JavaScript/TypeScript ou similar) representando a lógica de controle de interface.
  - **Respostas a perguntas complementares**, quando houver (por exemplo, percepção de dificuldade ou familiaridade com o formato).

É sobre esses artefatos (requisito em formatos distintos + código/pseudocódigo produzido) que serão calculadas as métricas **M01–M12**.

---

### 8.2 Sujeitos / participantes (visão geral)

Os participantes serão:

- **Desenvolvedores Web** com conhecimento em **Front-end** ou **Fullstack**; e
- **Profissionais/estudantes de QA** com experiência em criticar/compreender critérios de aceite.

Em termos de perfil:

- Podem ser **estudantes de graduação** em Computação/Engenharia de Software ou **profissionais em início/meio de carreira**.
- Espera-se que tenham **familiaridade básica com desenvolvimento Web** (eventos, estados, validação no cliente).
- O **nível de experiência** (júnior, pleno, sênior) será coletado, mas **não faz parte do fator principal** do estudo.

---

### 8.3 Variáveis independentes (fatores) e seus níveis

O experimento possui um fator principal manipulado:

- **Fator F1 – Formato dos critérios de aceite (Requisito de Interface)**
  - **Nível A – Linguagem Natural (LN)**
  - **Nível B – Gherkin (GH)**

---

### 8.4 Tratamentos (condições experimentais)

O experimento adota um desenho entre-sujeitos, onde cada participante vê apenas um formato de requisito:

- **Tratamento T1 – Grupo A: Linguagem Natural (LN)**
  - O participante recebe a descrição da funcionalidade em **texto corrido**.
  - Deve ler o enunciado e escrever a lógica de controle da interface.
  - Todas as métricas M01–M12 são calculadas com base na solução produzida a partir desse formato.

- **Tratamento T2 – Grupo B: Gherkin (GH)**
  - O participante recebe o mesmo conjunto de regras, reescrito em cenários Gherkin (Dado/Quando/Então).
  - Deve ler os cenários e escrever a lógica de controle da interface.
  - As mesmas métricas M01–M12 são calculadas, permitindo comparação direta com o Grupo A.

A tarefa funcional  é equivalente entre os grupos. A única diferença experimental é o formato de apresentação do requisito.

---

### 8.5 Variáveis dependentes (respostas)

As variáveis dependentes são as **métricas de resultado já definidas na Seção 3.4**, derivadas das soluções submetidas:

**Tempo / eficiência**
- **M01** – Tempo total de implementação.  
- **M01a** – Tempo até a primeira linha de código.  
- **M02** – Desvio padrão do tempo.  
- **M03** – Code Velocity.  

**Corretude / cobertura de estados**
- **M04** – Acurácia do caminho feliz.  
- **M05** – Cobertura de estados/transições.  

**Bugs e defeitos de lógica**
- **M06** – Bugs de omissão .  
- **M07** – Bugs de lógica de fluxo.  
- **M08** – Densidade de defeitos.  
- **M11** – Falhas em casos de borda.  

**Retrabalho / impacto**
- **M09** – Taxa de rejeição simulada em code review.  
- **M10** – Esforço de retrabalho estimado.  
- **M12** – Classificação de severidade dos defeitos.  

---

### 8.6 Variáveis de controle / bloqueio

- **Tipo de tarefa / componente:**
  - Todos os participantes implementam o mesmo cenário de interface, ou seja, mesmos estados, mesmas regras, mesmo nível de complexidade.

- **Ambiente de resposta:**
  - Uso do mesmo formulário eletrônico, com instruções idênticas, campos iguais para todos e limite de tempo semelhante.

- **Idioma e contexto do enunciado:**
  - Requisitos fornecidos em português, com vocabulário compatível com o público-alvo.

---

### 8.7 Possíveis variáveis de confusão conhecidas

Alguns fatores podem influenciar os resultados sem fazer parte do fator principal:

- **Motivação e engajamento do participante:**
  - Pessoas mais motivadas tendem a ler com mais atenção e codar com mais cuidado, reduzindo bugs independentemente do formato do requisito.

- **Fadiga e contexto de execução:**
  - Participantes fazendo o experimento após um dia cheio de trabalho/aula podem estar mais cansados, afetando tempo e qualidade de implementação.

- **Uso de ferramentas externas:**
  - Se o participante recorrer a modelos de IA ou copiar código pronto, isso distorce as medidas de esforço cognitivo e de omissão.
  - Será necessário inibir explicitamente sobre o uso de tais ferramentas.

- **Multitarefa e interrupções:**
  - O participante pode alternar entre janelas ou ser interrompido durante a tarefa, inflando artificialmente o tempo medido.

- **Variedade de dispositivos e ambiente físico:**
  - Diferenças entre usar notebook, monitor grande ou celular, bem como ambiente barulhento vs silencioso, podem impactar a fluidez de leitura e codificação.
    
---
## 9. Desenho experimental

### 9.1 Tipo de desenho (completamente randomizado, blocos, fatorial, etc.)

O estudo adotará um desenho experimental completamente randomizado entre sujeitos, em que cada participante é exposto a apenas um dos formatos de requisito (Linguagem Natural ou Gherkin), compondo dois grupos independentes: Grupo A (LN) e Grupo B (GH). A comparação entre os grupos será feita a partir das métricas M01–M12, tratadas como respostas às diferentes condições experimentais.

Esse tipo de desenho é adequado ao problema porque evita efeitos de aprendizagem, o participante não resolve a mesma tarefa duas vezes em formatos distintos e reduz o risco de contaminação, ou seja, de o entendimento construído em um formato influenciar a leitura do outro. Além disso, ele se encaixa bem nas restrições práticas do estudo, especialmente o fato de a coleta ser online, com participantes entrando em momentos distintos e realizando a tarefa em uma única sessão.

### 9.2 Randomização e alocação

A randomização será aplicada aos sujeitos, definindo em qual formato de requisito cada participante irá trabalhar. Cada pessoa receberá um identificador e, a partir desse identificador, um pequeno script de “sorteio” fará a alocação para um dos dois grupos: Grupo A (Linguagem Natural) ou Grupo B (Gherkin). Essa alocação será registrada em uma planilha ou base simples, associando o ID do participante ao grupo e ao link do formulário correspondente.

### 9.3 Balanceamento e contrabalanço

O balanceamento entre os grupos será feito acompanhando o número de respostas em LN e GH e ajustando a randomização, se necessário, para que os tamanhos fiquem semelhantes. Também serão coletados dados de perfil (experiência em desenvolvimento Web e familiaridade com Gherkin/BDD) para verificar se houve desequilíbrio de senioridade. E caso isso ocorra, podem ser feitas análises estratificadas ou ajustes estatísticos usando essas variáveis.

Em relação ao contrabalanço, ele não é necessário neste estudo, pois o desenho é entre sujeitos e cada participante realiza apenas uma tarefa em um único formato. Não há efeito de ordem entre tratamentos.

### 9.4 Número de grupos e sessões

- **Número de grupos:** 2 grupos independentes  
  - **Grupo A:** Linguagem Natural (LN)  
  - **Grupo B:** Gherkin (GH)

Cada participante participa de apenas uma sessão e resolve uma tarefa principal, sempre em um único formato de requisito, de acordo com o grupo em que foi alocado. Esse arranjo reduz o esforço individual, diminui o risco de fadiga e evita efeitos de aprendizagem cruzada, já que o participante não repete a mesma tarefa em outro formato.

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

