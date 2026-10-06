# Foot Fanatics — Product Requirements Document (PRD)

**Versão:** 1.1  
**Data:** Outubro 6, 2026  
**Responsável:** Morgan (PM)  
**Status:** Draft para Validação

### Histórico de alterações

| Data | Versão | Alteração | Responsável |
|------|--------|-----------|-------------|
| 6 de outubro de 2026 | 1.1 | Jornadas detalhadas por camada e requisitos funcionais derivados das jornadas. | Morgan (PM) |

---

## 📊 Sumário Executivo

**Foot Fanatics** é um site de futebol que centraliza informações dos 20 clubes que disputam a Série A do Campeonato Brasileiro, oferecendo três experiências distintas:

- **Administrador:** Acesso total ao sistema, gestão de dados e permissões
- **Investidor:** Análise e comparação de desempenho de todos os clubes
- **Torcedor:** Acompanhamento focado no clube favorito escolhido

O MVP entrega a visão completa para os três perfis, com dados atualizados semanalmente, tabela de classificação, histórico de vitórias/derrotas, saldo de gols, e destaque de melhor/pior jogador do momento (critério a ser definido).

---

## 1. Objetivos e Contexto

### 1.1 Objetivos do Produto

1. **Centralizar Informações:** Oferecer um único ponto de verdade para dados de clubes da Série A
2. **Oportunidades de Investimento:** Permitir que investidores analisem e comparem desempenho dos times
3. **Engajamento de Torcedores:** Facilitar que fãs acompanhem seu time favorito com clareza e emoção
4. **Gestão Eficiente:** Manter sistema operacional com dados íntegros e seguro

### 1.2 Problema Sendo Resolvido

- Investidores gastam tempo coletando dados dispersos sobre clubes de futebol
- Torcedores querem um único lugar para acompanhar seu time, sem confundir com dados de outros
- Administração de dados de futebol é manual e propensa a inconsistências
- Falta de transparência sobre métricas de desempenho (ex: como "melhor jogador" é definido)

### 1.3 Contexto de Negócio

- Produto inicial focado em Série A do Campeonato Brasileiro (20 clubes)
- Temporada: Foco na edição 2026 em andamento
- Potencial expansão futura para séries B/C e outros mercados
- Público: Brasileiros com interesse em futebol, foco em perfis de investidor e torcedor

### 1.4 Restrições e Limitações (MVP)

| Limitação | Descrição | Decisão |
|-----------|-----------|---------|
| **Fonte de Dados** | Fornecedor de dados ainda não definido | A definir em fase de arquitetura |
| **Critério Jogador** | "Melhor/pior no momento" = critério indefinido | Definir período, métrica (estatística vs avaliação) |
| **Frequência Update** | Sincronização planejada para semanal | Aceitar delay de até 24h após rodada |
| **Autenticação e perfis** | Método de autenticação e fluxo de cadastro ainda não foram definidos | Definir se login/cadastro integram o MVP; o sistema ainda precisa aplicar permissões por perfil |
| **Comparação Investidor** | Comparação lado-a-lado não está no MVP | Expandir em fase 2 |

---

## 2. Personas e Jornadas

### 2.1 Persona 1: Administrador

**Acesso:** Sistema inteiro  
**Responsabilidade:** Manutenção, dados, segurança, operações  
**Frequência:** Diário, conforme necessário  
**Objetivo Principal:** Garantir que Foot Fanatics funcione sem interrupções

**Jornada:** Acessar área administrativa → verificar estado dos dados → manter dados de clubes e jogadores → gerenciar usuários e permissões → consultar auditoria e sincronização.

**Funcionalidades-Chave:**
- ✓ Atualizar dados de clubes (vitórias, derrotas, saldo de gols, posição)
- ✓ Gerenciar dados de jogadores e rankings
- ✓ Atribuir permissões (admin, investidor, torcedor)
- ✓ Acessar logs e auditoria
- ✓ Configurar temporada e critério de rankings

Veja documento completo: [01-persona-admin.md](01-persona-admin.md)

---

### 2.2 Persona 2: Investidor

**Acesso:** Visualização de todos os clubes  
**Responsabilidade:** Análise, pesquisa, decisão de investimento  
**Frequência:** 2-3 vezes por semana  
**Objetivo Principal:** Comparar e analisar desempenho de clubes para decisão de investimento

**Jornada:** Acessar visão geral → examinar os clubes → filtrar/ordenar → analisar um clube e seus destaques → acompanhar dados atualizados. Comparação lado a lado e exportação permanecem na Fase 2.

**Funcionalidades-Chave:**
- ✓ Ver tabela de todos os 20 clubes (posição, vitórias, derrotas, saldo)
- ✓ Filtrar e ordenar por critérios (posição, tendência, vitórias)
- ✓ Visualizar dados detalhados de cada clube
- ✓ Comparar múltiplos clubes (fase 2)
- ✓ Exportar relatórios (fase 2)
- ✗ Editar ou modificar dados

Veja documento completo: [02-persona-investidor.md](02-persona-investidor.md)

---

### 2.3 Persona 3: Torcedor

**Acesso:** Dados do clube favorito escolhido  
**Responsabilidade:** Acompanhamento emocional e casual  
**Frequência:** Diariamente, especialmente dias de jogo  
**Objetivo Principal:** Acompanhar seu time com clareza e emoção

**Jornada:** Acessar experiência de torcedor → selecionar e confirmar o clube favorito → consultar painel dedicado com classificação, desempenho e destaques de jogadores.

**Funcionalidades-Chave:**
- ✓ Selecionar e confirmar clube favorito
- ✓ Ver posição na tabela
- ✓ Ver vitórias e derrotas totais
- ✓ Ver saldo de gols
- ✓ Ver melhor e pior jogador do momento
- ✓ Histórico de últimas rodadas (fase 2)
- ✓ Compartilhar resultados (fase 2)
- ✗ Editar qualquer informação
- ✗ Ver dados de administração

Veja documento completo: [03-persona-torcedor.md](03-persona-torcedor.md)

As jornadas detalhadas, incluindo interações de front-end, respostas e validações do sistema, exceções e rastreabilidade dos requisitos, estão em [04-jornadas-e-requisitos-funcionais.md](04-jornadas-e-requisitos-funcionais.md). Nenhuma tecnologia é definida por esse detalhamento.

---

## 3. Análise de Dados e Indicadores

### 3.1 Dados de Clubes

Cada clube do Brasileirão A terá os seguintes atributos:

| Atributo | Tipo | Frequência Atualização | Descrição |
|----------|------|----------------------|-----------|
| **Nome do Clube** | String | Não muda | Ex: Flamengo, São Paulo, Botafogo |
| **Sigla/Código** | String | Não muda | Ex: FLA, SP, BOT |
| **Posição na Tabela** | Integer (1-20) | Semanal (pós-rodada) | Colocação atual no Brasileirão |
| **Vitórias** | Integer | Semanal | Total de vitórias na temporada |
| **Derrotas** | Integer | Semanal | Total de derrotas na temporada |
| **Empates** | Integer | Semanal | Total de empates na temporada (opcional para display) |
| **Gols Pró (marcados)** | Integer | Semanal | Total de gols marcados |
| **Gols Contra (sofridos)** | Integer | Semanal | Total de gols sofridos |
| **Saldo de Gols** | Integer (calculado) | Semanal | Gols Pró - Gols Contra |
| **Pontos** | Integer | Semanal | Pontos acumulados (3=vitória, 1=empate, 0=derrota) |
| **Jogos Disputados** | Integer | Semanal | Número total de partidas jogadas |
| **Logo/Badge** | Image URL | Não muda | Emblema do clube para interface |
| **Tendência** | Enum [↗ Melhora, → Estável, ↘ Queda] | Semanal (calculada) | Performance nos últimos 5 jogos |

**Fonte:** A definir (CBF, ESPN, Sofascore, API proprietária, etc.)  
**Sincronização:** Semanal, máximo 24h após rodada oficial

---

### 3.2 Dados de Jogadores

Cada clube terá um registro de "Melhor" e "Pior" jogador no momento. Estrutura:

| Atributo | Tipo | Frequência Atualização | Descrição |
|----------|------|----------------------|-----------|
| **Nome do Jogador** | String | Variável | Nome do atleta |
| **Posição** | Enum [Goleiro, Defesa, Meia, Atacante] | Não muda | Posição em campo |
| **Número da Camisa** | Integer | Não muda | Número da camisa |
| **Rating/Score** | Float (0-10) | Periódica* | Desempenho no período (ex: 8.5/10) |
| **Período de Avaliação** | Enum | Periódica* | Últimas 3 rodadas? Últimas 5 rodadas? Temporada inteira? |
| **Métrica de Avaliação** | Enum | Periódica* | Estatísticas (gols, assistências, interceptações) vs Avaliação subjetiva |
| **Status** | Enum [Melhor, Pior] | Periódica* | Designação no período |

**\*Frequência a ser definida:** Semanal? Após cada rodada? Baseado em últimas N partidas?

**Critério a ser Definido:** Precisamos validar como "Melhor Jogador" será calculado/atribuído:

- **Opção A (Automática - Estatística):** Algoritmo calcula score com base em gols, assistências, passes certos, interceptações, etc.
- **Opção B (Automática - Rating Externo):** Integração com plataforma de ratings (Sofascore, Kicker, etc.)
- **Opção C (Manual):** Admin define semanalmente baseado em desempenho observado
- **Opção D (Híbrida):** Combinação de automático + validação manual

**Recomendação MVP:** Opção A ou B (automática) + Opção C (admin pode override) para validação posterior

---

### 3.3 Indicadores de Análise para Investidor

O investidor pode analisar/comparar clubes usando:

1. **Posição Atual:** Colocação (1-20) na tabela
2. **Percentual de Vitória:** Vitórias / Jogos Disputados
3. **Média de Gols:** Gols Pró / Jogos Disputados
4. **Fragilidade em Defesa:** Gols Contra / Jogos Disputados
5. **Saldo de Gols:** Indicador de superioridade
6. **Pontos Acumulados:** Métrica oficial de performance
7. **Tendência:** Melhora ou queda nos últimos 5 jogos
8. **Phaseout Potencial:** Clubes em zona de rebaixamento vs liderança

**MVP:** Display de 1, 2, 3, 5, 7  
**Fase 2:** Gráficos comparativos, histórico de temporada anterior, projeções

---

### 3.4 Desafios de Integridade de Dados

| Desafio | Impacto | Mitigação |
|---------|--------|-----------|
| **Dados Desatualizados** | Alto | Sincronização automática 24h pós-rodada; alerta se > 7 dias sem atualização |
| **Inconsistência entre Fontes** | Médio | Usar única fonte confiável; validação de soma (V+D+E = Jogos) |
| **Ranking Manual Indefinido** | Alto | Definir critério claro e documentado; admin pode override com justificativa |
| **Jogador Transferido/Aposentado** | Baixo/MVP | MVP: Congelar dados históricos; Fase 2: Gestão de transferências |
| **Dados Históricos Perdidos** | Alto | Backup diário de banco de dados |

---

## 4. Requisitos Funcionais

Os requisitos funcionais derivados das jornadas estão detalhados e numerados em [04-jornadas-e-requisitos-funcionais.md](04-jornadas-e-requisitos-funcionais.md). Essa seção do PRD adota aqueles requisitos como referência para evitar versões divergentes; sua numeração e as fases indicadas no documento complementar são a base para validação e criação futura de histórias.

---

## 5. Requisitos Não-Funcionais

### NFR1: Performance

- **NFR1.1** Dashboard deve carregar em < 3 segundos (conexão 4G)
- **NFR1.2** Tabela de clubes deve renderizar com até 20 itens sem lag
- **NFR1.3** Buscas/filtros devem responder em < 1 segundo

### NFR2: Disponibilidade

- **NFR2.1** Sistema deve estar disponível 99%+ da semana (manutenção permitida)
- **NFR2.2** Backup de dados deve ocorrer diariamente
- **NFR2.3** Plano de recuperação em caso de falha deve estar documentado

### NFR3: Confiabilidade

- **NFR3.1** Dados de classificação devem estar 100% sincronizados com fonte oficial dentro de 24h
- **NFR3.2** Nenhum dado deve ser perdido; auditoria completa de alterações
- **NFR3.3** Rankings de jogadores devem ser calculados/validados com zero erros

### NFR4: Usabilidade

- **NFR4.1** Interface deve ser responsiva e funcionar em dispositivos móveis (mobile-first)
- **NFR4.2** Texto e cores devem atender WCAG AA (acessibilidade)
- **NFR4.3** Ações comuns (selecionar clube, ver posição) devem exigir max 2 cliques
- **NFR4.4** Torcedor deve entender interface sem treinamento

### NFR5: Escalabilidade

- **NFR5.1** Sistema deve suportar até 10.000 usuários simultâneos
- **NFR5.2** Banco de dados deve permitir crescimento de dados históricos (múltiplas temporadas)
- **NFR5.3** Arquitetura deve permitir expansão para outras séries (B, C) sem reengenharia

### NFR6: Manutenibilidade

- **NFR6.1** Código deve seguir padrões estabelecidos (linting, testes automatizados)
- **NFR6.2** Documentação de API e schema de dados deve estar atualizada
- **NFR6.3** Processo de deploy deve ser automatizado

---

## 6. Epics e Estrutura de Desenvolvimento

### 6.1 Visão de Epics

```
Epic 1: Foundation & Infrastructure
└─ Setup inicial, autenticação, estrutura de banco de dados

Epic 2: Core Data & Admin Panel
└─ Gestão de dados de clubes, jogadores, rankings, permissões

Epic 3: Investor Dashboard
└─ Visualização e análise de todos os clubes

Epic 4: Torcedor Dashboard & Fan Experience
└─ Seleção de clube, visualização dedicada, histórico

Epic 5: Sync & Reliability
└─ Sincronização de dados, backups, monitoramento
```

---

### 6.2 Epic 1: Foundation & Infrastructure

**Objetivo:** Estabelecer infraestrutura base, autenticação e modelo de dados

**Histórias:**

| Story | Descrição | Tamanho |
|-------|-----------|--------|
| 1.1 | Setup project, repos, CI/CD | M |
| 1.2 | Design banco de dados (clubs, players, users, permissions) | M |
| 1.3 | Implementar sistema de autenticação (login, roles) | L |
| 1.4 | Criar seeds com 20 clubes da Série A | S |
| 1.5 | Setup ambiente de teste (local, staging) | M |

---

### 6.3 Epic 2: Core Data & Admin Panel

**Objetivo:** Permitir admin gerenciar todos os dados do sistema

**Histórias:**

| Story | Descrição | Tamanho |
|-------|-----------|--------|
| 2.1 | CRUD para dados de clubes (vitórias, derrotas, saldo) | M |
| 2.2 | Validação de integridade de dados (V+D+E=J) | S |
| 2.3 | Gestão de jogadores (Melhor/Pior por clube) | M |
| 2.4 | Admin Panel UI (dashboard, forms, logs) | L |
| 2.5 | Auditoria (histórico de ações, reverter mudanças) | M |
| 2.6 | Sincronização manual de dados | S |

---

### 6.4 Epic 3: Investor Dashboard

**Objetivo:** Permitir investidor analisar e comparar clubes

**Histórias:**

| Story | Descrição | Tamanho |
|-------|-----------|--------|
| 3.1 | Tabela de todos os clubes (20) com dados essenciais | M |
| 3.2 | Filtros e ordenação (posição, tendência, vitórias) | M |
| 3.3 | View detalhada de cada clube (histórico recente) | M |
| 3.4 | Indicadores de análise (% vitória, média de gols) | S |
| 3.5 | Display de Melhor/Pior Jogador por clube | S |
| 3.6 | Exportar comparação de clubes (PDF/CSV) — Fase 2 | M |

---

### 6.5 Epic 4: Torcedor Dashboard & Fan Experience

**Objetivo:** Permitir torcedor selecionar e acompanhar seu time

**Histórias:**

| Story | Descrição | Tamanho |
|-------|-----------|--------|
| 4.1 | Seleção de clube favorito (modal/flow) | S |
| 4.2 | Dashboard dedicado do torcedor | L |
| 4.3 | Display de Posição, Vitórias, Derrotas, Saldo (destaques) | M |
| 4.4 | Display de Melhor/Pior Jogador | S |
| 4.5 | Histórico de últimas 5 rodadas — Fase 2 | M |
| 4.6 | Compartilhar resultado em redes sociais — Fase 2 | S |

---

### 6.6 Epic 5: Sync & Reliability

**Objetivo:** Manter dados atualizados e confiáveis

**Histórias:**

| Story | Descrição | Tamanho |
|-------|-----------|--------|
| 5.1 | Integração com fonte de dados (CB, ESPN, API) | L |
| 5.2 | Job de sincronização automática (semanal) | M |
| 5.3 | Alertas de dados desatualizados | S |
| 5.4 | Backup diário e plano de recuperação | M |
| 5.5 | Monitoramento de saúde do sistema (logs, métricas) | M |

---

## 7. Definições Críticas em Aberto

| Decisão | Impacto | Próximos Passos |
|---------|--------|-----------------|
| **Fonte de Dados** | CRÍTICO | Pesquisar CBF, ESPN, Sofascore, ou API proprietária; validar licenciamento e confiabilidade |
| **Critério Melhor/Pior Jogador** | CRÍTICO | Definir período (semanal, últimas 5 rodadas, temporada); escolher métrica (automática vs manual) |
| **Autenticação e perfis** | ALTO | Definir se login/cadastro integram o MVP e como cada sessão será associada a um perfil; sem definir tecnologia neste PRD |
| **Responsividade Mobile** | MÉDIO | Confirmar se MVP deve ser mobile-first ou web-first |
| **Histórico de Temporadas** | MÉDIO | MVP foca em 2026; futura: suportar múltiplas temporadas? |
| **Comparação Lado-a-Lado** | BAIXO | Feature solicitada por investidor; considerar fase 2 |

---

## 8. Métricas de Sucesso

### Métricas de Negócio

| Métrica | Meta MVP | Target |
|---------|----------|--------|
| **Registros (Investidores)** | 100+ | 500+ em 3 meses |
| **Registros (Torcedores)** | 500+ | 5.000+ em 3 meses |
| **DAU (Daily Active Users)** | 10%+ dos registrados | 30%+ |
| **Retenção (7-dia)** | 60%+ | 75%+ |
| **Taxa de Compartilhamento** | 20%+ (torcedores) | 40%+ |

### Métricas de Qualidade

| Métrica | Meta |
|---------|------|
| **Uptime** | 99%+ |
| **Tempo de Carregamento** | < 3s (P95) |
| **Dados Desatualizados** | < 24h após rodada |
| **Satisfação (NPS)** | 50+ |
| **Taxa de Erro** | < 0.1% |

---

## 9. Plano de Próximas Fases (Roadmap)

### Fase 2 (T+3 meses)

- [ ] Histórico de temporadas anteriores
- [ ] Comparação lado-a-lado de clubes
- [ ] Exportação de relatórios (PDF/CSV)
- [ ] Notificações (alerta pós-jogo, ranking de jogador)
- [ ] Integração com redes sociais (compartilhamento)
- [ ] Suporte para Série B

### Fase 3 (T+6 meses)

- [ ] Community de torcedores (fórum, discussões)
- [ ] Análises estatísticas avançadas
- [ ] Mercado de mercadorias (NFT, merchandise)
- [ ] Integração com fantasy football
- [ ] API pública para terceiros

---

## 10. Equipe e Responsabilidades

| Papel | Responsabilidade |
|-------|-----------------|
| **PM (Morgan)** | Visão, requisitos, validação com stakeholders |
| **@Architect** | Arquitetura técnica, escolha de stack, design de banco de dados |
| **@Data-Engineer** | Schema, migrations, otimização de queries, RLS policies |
| **@Dev** | Implementação de features, integração de APIs |
| **@QA** | Testes de funcionalidade, regressão, performance |
| **@DevOps** | CI/CD, deploy, monitoramento, backups |
| **@UX-Design-Expert** | Design de interfaces, acessibilidade, user research |

---

## 11. Análise de Risco e Mitigação

| Risco | Probabilidade | Impacto | Mitigação |
|------|---------------|--------|-----------|
| Fonte de dados indisponível/inadequada | Alta | Crítico | Avaliar múltiplas fontes em paralelo; ter backup |
| Inconsistência de dados (rankings indefinidos) | Média | Alto | Documentar critério claro; validação manual initial |
| Performance inadequada com N usuários | Baixa | Alto | Testes de carga; cache strategy; CDN para assets |
| Atraso em autenticação/login | Média | Médio | Desacoplar de MVP; usar mock auth se necessário |
| Ambigüidade em requisitos do investidor | Média | Médio | Validar com stakeholder investidor antes de dev |

---

## 12. Sucesso do MVP

**O MVP é considerado bem-sucedido quando:**

1. ✓ Admin consegue atualizar dados de clubes em < 5 min
2. ✓ Investidor visualiza tabela de 20 clubes com dados principais < 3s
3. ✓ Torcedor seleciona clube e vê posição, vitórias, derrotas, saldo < 2 cliques
4. ✓ Dados estão sincronizados com fonte dentro de 24h de rodada
5. ✓ Melhor/Pior jogador é exibido com critério transparente
6. ✓ Nenhuma violação de permissões (admin/investidor/torcedor isolados)
7. ✓ 100+ registros de investidor, 500+ de torcedor na primeira semana
8. ✓ Taxa de retenção 7-dia: 60%+

---

## Anexos

### A. Documentação de Personas

- [01-persona-admin.md](01-persona-admin.md) — Admin: Jornada, permissões, necessidades
- [02-persona-investidor.md](02-persona-investidor.md) — Investidor: Jornada, análise, indicadores
- [03-persona-torcedor.md](03-persona-torcedor.md) — Torcedor: Jornada, visualização, experiência

### B. Referências Externas

- Campeonato Brasileiro Série A 2026 (CBF)
- Sofascore, ESPN, Kicker (fontes de dados potenciais)
- WCAG 2.1 AA (acessibilidade)

---

**Documento assinado por Morgan (PM)**  
**Data: Outubro 5, 2026**  
**Próxima revisão: Após validação com @Architect e stakeholders**
