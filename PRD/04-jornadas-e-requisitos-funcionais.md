# Foot Fanatics — Jornadas e Requisitos Funcionais

**Versão:** 1.0  
**Data:** 6 de outubro de 2026  
**Status:** Draft para validação  
**Escopo:** Jornadas das personas e requisitos funcionais do produto, sem escolha de tecnologia.

## 1. Objetivo e convenções

Este documento detalha como Admin, Investidor e Torcedor realizam seus objetivos na aplicação e traduz essas jornadas em requisitos funcionais rastreáveis. “Front-end” descreve o que a pessoa vê e faz; “sistema” descreve respostas, regras, validações e persistência esperadas, sem definir arquitetura, linguagem, framework, banco de dados ou fornecedor.

Os requisitos marcados como **Fase 2** não fazem parte do MVP conforme o escopo atual do PRD. Questões em aberto são destacadas ao final e não devem ser interpretadas como decisões já aprovadas.

## 2. Jornada do Administrador

**Objetivo:** manter os dados íntegros e atualizados, controlar acessos e acompanhar a operação do Foot Fanatics.

| Etapa | Front-end — interação e feedback | Sistema — comportamento esperado |
|---|---|---|
| 1. Acessar a área administrativa | O Admin inicia uma sessão e abre a área administrativa. | Identifica o perfil associado à sessão. Só permite acesso às funções administrativas ao perfil Admin; método de autenticação ainda está em aberto. |
| 2. Ver o estado do sistema | O painel apresenta o estado de atualização dos dados, temporada ativa e alertas operacionais disponíveis. | Consulta o estado conhecido da sincronização, a data da última atualização e as informações de temporada configuradas. Se não houver informação, apresenta estado indisponível em vez de indicar sucesso. |
| 3. Localizar temporada, clube e dados | O Admin escolhe a temporada ativa, o clube e a seção de dados ou jogadores que deseja manter. | Retorna os registros da temporada e do clube selecionados. A criação, troca ou encerramento de temporadas segue regras de produto ainda a confirmar. |
| 4. Preparar atualização de desempenho | O Admin informa ou revisa posição, pontos, jogos, vitórias, empates, derrotas, gols pró e gols contra; pode revisar alterações em lote antes de confirmá-las. | Valida os valores e as relações entre eles. Calcula saldo de gols a partir de gols pró e gols contra; não aceita valores incoerentes sem indicar o erro. |
| 5. Confirmar e publicar dados | O Admin revisa o resumo das mudanças e confirma ou descarta a atualização. A interface informa o resultado da operação. | Persiste apenas mudanças confirmadas. Registra quem alterou, quando, o que mudou e o resultado. Os dados atualizados ficam disponíveis aos perfis autorizados. |
| 6. Manter dados de jogadores | O Admin consulta, adiciona, edita ou remove registros de jogadores associados a um clube. | Valida a associação com o clube e aplica as alterações confirmadas, preservando o histórico de auditoria. |
| 7. Atualizar destaques de jogadores | O Admin associa os destaques de melhor e pior jogador ao clube e consulta ou informa o critério e o período quando disponíveis. | Guarda o critério/período informado. Não inventa nem calcula um ranking enquanto o método de avaliação não estiver definido. |
| 8. Gerenciar usuários e papéis | O Admin consulta uma conta e executa uma ação de gestão permitida, como atribuir papel, alterar permissões ou suspender acesso. | Aplica as regras de autorização, persiste a alteração e registra a ação para auditoria. |
| 9. Consultar histórico e sincronização | O Admin filtra ou consulta os registros de auditoria e pode solicitar sincronização manual quando necessário. | Retorna eventos com usuário, data/hora, ação e resultado. Para sincronização, informa início, conclusão ou falha e a data da última execução; não sinaliza conclusão antes de confirmar o resultado. |

### Exceções que a jornada deve cobrir

- Perfil sem autorização para a área ou ação: negar a operação sem revelar dados administrativos.
- Dados inválidos ou inconsistentes: indicar os campos e regras que falharam; não publicar a atualização.
- Falha ao salvar ou sincronizar: informar que a operação falhou e manter visível o estado anterior confirmado.
- Critério/período do ranking ainda não definido: exibir que a informação está pendente, sem apresentar um ranking como se fosse calculado.

## 3. Jornada do Investidor

**Objetivo:** analisar o desempenho dos clubes da Série A e usar os dados para identificar oportunidades de investimento.

| Etapa | Front-end — interação e feedback | Sistema — comportamento esperado |
|---|---|---|
| 1. Acessar a visão geral | O Investidor abre a área de análise. | Confirma o perfil Investidor e autoriza leitura dos dados dos clubes; não permite operações administrativas ou alterações. |
| 2. Examinar a Série A | A tela apresenta os 20 clubes da temporada ativa em tabela, com classificação e indicadores disponíveis, além da data da última atualização. | Retorna dados consistentes para a temporada selecionada, respeitando a classificação vigente e indicando ausência ou defasagem dos dados quando aplicável. |
| 3. Encontrar clubes relevantes | O Investidor aplica filtros ou ordena a tabela por critérios apresentados pela interface, como posição, vitórias, saldo de gols e tendência. | Aplica os critérios aos dados disponíveis e mantém os valores exibidos coerentes com a ordenação/filtro escolhidos. |
| 4. Investigar um clube | O Investidor abre o detalhe de um clube para consultar indicadores de desempenho e destaques de jogadores. | Retorna dados do clube e contexto disponível. Exibe o período e o critério dos destaques quando conhecidos; não apresenta informação pendente como fato. |
| 5. Comparar alternativas | **Fase 2:** o Investidor seleciona dois ou mais clubes e consulta indicadores lado a lado. | Compara os clubes selecionados usando os mesmos indicadores, temporada e períodos; informa quando um valor não está disponível. |
| 6. Acompanhar após uma rodada | O Investidor retorna à visão geral ou ao detalhe para verificar os dados mais recentes. | Usa a última atualização confirmada e informa sua data. Se a atualização esperada estiver atrasada, comunica a defasagem em vez de sugerir que os números são atuais. |
| 7. Exportar ou receber alertas | **Fase 2:** o Investidor exporta dados ou configura alertas, se aprovados para o produto. | Produz somente os dados autorizados e informa sucesso ou falha da operação. |

### Exceções que a jornada deve cobrir

- Dados de um clube ou indicador indisponíveis: identificar a ausência, sem substituir por zero ou dado inventado.
- Dados ainda não atualizados após uma rodada: mostrar a data da última atualização e o estado de defasagem.
- Tentativa de editar dados ou acessar funções administrativas: negar a operação.

## 4. Jornada do Torcedor

**Objetivo:** acompanhar de forma rápida e clara o desempenho do clube que torce, incluindo sua posição e os destaques de jogadores.

| Etapa | Front-end — interação e feedback | Sistema — comportamento esperado |
|---|---|---|
| 1. Acessar a experiência de torcedor | O Torcedor entra na área correspondente ao seu perfil. | Identifica o perfil e aplica o limite de acesso definido para a experiência de torcedor. O método de autenticação permanece em aberto. |
| 2. Escolher o clube | Na primeira utilização, o Torcedor procura, seleciona e confirma seu clube favorito. | Confirma que o clube pertence à Série A da temporada ativa e associa a seleção ao contexto do Torcedor conforme a política de conta que vier a ser definida. |
| 3. Consultar o painel do clube | O painel destaca posição, vitórias, derrotas, saldo de gols e os destaques de melhor/pior jogador disponíveis. | Retorna somente os dados do clube selecionado para essa experiência, com a data da última atualização e contexto dos destaques quando definido. |
| 4. Entender os números | O Torcedor consulta rótulos, período e explicações apresentados junto aos indicadores. | Mantém os indicadores coerentes com os dados registrados; sinaliza métricas ou critérios ainda não definidos ou indisponíveis. |
| 5. Acompanhar resultados recentes | **Fase 2:** o Torcedor consulta histórico das últimas cinco rodadas. | Retorna os resultados ordenados cronologicamente e associados à temporada correta, quando esse escopo for aprovado e os dados estiverem disponíveis. |

### Exceções que a jornada deve cobrir

- Nenhum clube selecionado: orientar a seleção antes de exibir o painel.
- Dados do clube indisponíveis ou desatualizados: mostrar a situação e a data da última atualização conhecida.
- Tentativa de editar dados, acessar o painel Admin ou visualizar informações de outros Torcedores: negar a operação.
- Alteração do clube favorito: comportamento ainda não definido; ver decisões em aberto.

## 5. Requisitos funcionais derivados

Cada requisito abaixo deve ser verificável pela resposta observável da aplicação. Os requisitos funcionais complementam a visão geral do PRD; “Fase 2” indica explicitamente escopo posterior ao MVP.

### Acesso e limites por perfil

- **FR1:** O sistema deve distinguir os perfis Admin, Investidor e Torcedor e aplicar a cada sessão as permissões correspondentes: Admin pode acessar as funções administrativas; Investidor pode consultar todos os clubes; Torcedor pode consultar o clube associado à sua experiência.
- **FR2:** O sistema deve negar ações não autorizadas pelo perfil e não deve expor dados administrativos a Investidores ou Torcedores.

### Administração

- **FR3:** O Admin deve poder consultar e manter os dados de desempenho dos clubes da temporada ativa, incluindo classificação, jogos, vitórias, empates, derrotas, gols pró e gols contra.
- **FR4:** O sistema deve validar os dados de desempenho antes de confirmá-los, incluindo a regra jogos disputados = vitórias + empates + derrotas e o cálculo de saldo de gols = gols pró - gols contra.
- **FR5:** O Admin deve poder revisar uma atualização antes de confirmá-la ou descartá-la; alterações não confirmadas não devem ser publicadas.
- **FR6:** O Admin deve poder consultar, adicionar, editar e remover registros de jogadores associados aos clubes, conforme as regras de validação e auditoria.
- **FR7:** O Admin deve poder associar os destaques de melhor e pior jogador a um clube e registrar o critério e período quando definidos. A apresentação do destaque deve deixar claro quando esses dados não estiverem definidos ou disponíveis.
- **FR8:** O Admin deve poder consultar e gerenciar contas e papéis de usuários, conforme as ações permitidas ao perfil Admin.
- **FR9:** O sistema deve registrar ações administrativas com, no mínimo, usuário, data/hora, ação e resultado, e permitir ao Admin consultar esse histórico.
- **FR10:** O Admin deve poder consultar o estado e a data da última sincronização e solicitar uma sincronização manual; o sistema deve informar o resultado da execução.
- **FR11:** O sistema deve atualizar os dados do campeonato após as rodadas dentro da janela de até 24 horas definida no PRD e indicar a data da última atualização confirmada.
- **FR12:** O Admin deve poder consultar e configurar a temporada ativa; as regras para criar, encerrar ou reiniciar uma temporada devem ser definidas antes da implementação dessas operações.

### Investidor

- **FR13:** O Investidor deve poder consultar os 20 clubes da Série A na temporada ativa em uma visão geral com classificação e indicadores disponíveis, incluindo vitórias, derrotas, saldo de gols e data da atualização.
- **FR14:** O Investidor deve poder filtrar e ordenar clubes pelos critérios disponíveis na interface, incluindo posição, tendência e vitórias.
- **FR15:** O Investidor deve poder abrir a visão detalhada de um clube e consultar seus indicadores, evolução de desempenho disponível e destaques de jogadores, com período e critério dos destaques quando definidos.
- **FR16 (Fase 2):** O Investidor deve poder selecionar múltiplos clubes e comparar seus indicadores lado a lado.
- **FR17 (Fase 2):** O Investidor deve poder exportar relatórios comparativos nos formatos aprovados para essa fase.
- **FR18 (Fase 2):** O Investidor deve poder configurar alertas de variação de desempenho quando o escopo e as regras de alerta forem definidos.
- **FR19:** O Investidor não deve poder alterar dados, gerenciar contas ou acessar funções administrativas.

### Torcedor

- **FR20:** O Torcedor deve poder selecionar e confirmar um clube favorito dentre os clubes da Série A da temporada ativa antes de consultar seu painel dedicado.
- **FR21:** O painel do Torcedor deve exibir dados do clube selecionado, incluindo posição, vitórias, derrotas, saldo de gols e os destaques de melhor e pior jogador quando disponíveis.
- **FR22:** O painel deve indicar a data da última atualização dos dados e identificar indicadores indisponíveis ou desatualizados sem apresentar valores fictícios.
- **FR23 (Fase 2):** O Torcedor deve poder consultar o histórico dos resultados das últimas cinco rodadas do clube selecionado.
- **FR24:** O Torcedor não deve poder editar dados, acessar funções administrativas, consultar dados de outros Torcedores ou usar essa experiência para navegar livremente pelos dados de outros clubes.

## 6. Decisões ainda necessárias

Estas decisões impactam o detalhe das jornadas ou a testabilidade de alguns requisitos e continuam abertas no PRD:

| Decisão | Impacto |
|---|---|
| Autenticação, criação de conta e acesso de cada perfil no MVP | Define como a sessão é iniciada e como o perfil é associado ao usuário; não define tecnologia neste documento. |
| Fonte de dados e política de atualização | Define disponibilidade, atualização automática e validação dos dados do campeonato. |
| Critério, período e fonte dos destaques de melhor/pior jogador | Necessário para calcular ou atribuir e explicar os destaques sem ambiguidade. |
| Alteração do clube favorito pelo Torcedor | Define se a seleção é permanente, editável ou limitada por regras. |
| Dados detalhados de evolução/histórico disponíveis no MVP | Define o que pode ser exibido no detalhe do Investidor; o histórico de cinco rodadas do Torcedor permanece Fase 2. |
| Escopo de temporada e acesso do Torcedor a outros clubes | Confirma a restrição de um clube por Torcedor e como ela se aplica fora do painel dedicado. |

## 7. Rastreabilidade resumida

| Jornada | Requisitos relacionados |
|---|---|
| Administrador | FR1–FR12 |
| Investidor | FR1–FR2, FR13–FR19 |
| Torcedor | FR1–FR2, FR20–FR24 |

---

**Documento relacionado:** [PRD principal](00-foot-fanatics-prd.md), seções 2, 4 e 7.
