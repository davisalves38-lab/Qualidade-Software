# Persona: Investidor

## Perfil Geral

| Atributo | Valor |
|----------|-------|
| **Nome** | Investidor de Futebol / Analista de Performance |
| **Escopo de Acesso** | Visualização de todos os clubes e dados comparativos |
| **Responsabilidade** | Análise, pesquisa e decisão de investimento |
| **Frequência de Uso** | 2-3 vezes por semana ou após rodadas importantes |
| **Nível de Conhecimento** | Business/Finance; conhecimento moderado de futebol |

---

## Objetivos Principais

1. **Comparação de Desempenho:** Avaliar e comparar o desempenho de todos os clubes do Brasileirão A
2. **Análise de Tendências:** Entender trajetória de sucesso ou dificuldade de cada time
3. **Tomada de Decisão:** Usar dados para informar estratégias de investimento
4. **Identificação de Oportunidades:** Encontrar clubes com potencial de crescimento
5. **Acompanhamento:** Monitorar evolução de investimentos ao longo da temporada

---

## Jornada do Usuário

### Fluxo Principal

```
[Login Investidor]
    ↓
[Dashboard - Visão Geral de Todos os Clubes]
    ├─ Tabela Comparativa (Vitórias, Derrotas, Saldo, Posição)
    ├─ Filtros e Ordenação (por Posição, Tendência, etc.)
    ├─ Seleção de Clube para Análise Detalhada
    │   ├─ Histórico de Performance
    │   ├─ Evolução de Classificação
    │   └─ Dados de Jogadores-Chave
    └─ Exportar/Comparar Múltiplos Clubes
```

### Cenários de Uso

1. **Análise Inicial (Primeira Visita)**
   - Entrada: Investidor quer entender o mercado geral
   - Ações: Navega para a página inicial → Visualiza tabela comparativa de todos os clubes → Ordena por vitórias ou saldo de gols
   - Saída: Visão panorâmica do desempenho da Série A

2. **Análise Aprofundada de um Clube**
   - Entrada: Após ver visão geral, investe em um time específico
   - Ações: Clica no clube de interesse → Acessa dashboard dedicado com histórico de resultados, tendências e destaque de jogadores
   - Saída: Dados detalhados que informam decisão de investimento

3. **Comparação de Múltiplos Clubes (Fase 2)**
   - Entrada: Precisa escolher entre 2-3 opções de investimento
   - Ações: Seleciona clubes para comparação → Visualiza side-by-side de indicadores-chave (vitórias, posição, tendência)
   - Saída: Comparação clara facilitando escolha

4. **Acompanhamento Pós-Investimento**
   - Entrada: Monitorar desempenho de clube já investido
   - Ações: Abre dashboard do clube → Verifica atualização de dados após rodada → Recebe alerta se performance cai abruptamente
   - Saída: Segurança de que dados são atualizados e confiáveis

---

## Permissões e Funcionalidades

| Funcionalidade | Acesso | Descrição |
|----------------|--------|-----------|
| **Visualizar Todos os Clubes** | ✓ | Listar e consultar todos os 20 clubes da Série A |
| **Ver Visão Geral dos Clubes** | ✓ | Consultar os indicadores dos 20 clubes na visão geral da Série A |
| **Comparar Clubes Selecionados** | Fase 2 | Comparação lado a lado de clubes selecionados |
| **Filtrar/Ordenar** | ✓ | Organizar por posição, vitórias, saldo de gols, tendência |
| **Detalhar Performance de Clube** | ✓ | Histórico de resultados, evolução na tabela |
| **Visualizar Jogadores-Chave** | ✓ | Ver "melhor/pior jogador no momento" por clube |
| **Exportar Dados** | Fase 2 | Baixar relatório comparativo em formatos aprovados |
| **Receber Alertas** | Fase 2 | Notificação se clube sofre grande queda, com regras a definir |
| **Selecionar/Seguir Clubes** | ~ | Marcar favoritos ou clubes de interesse para acompanhamento |
| **Editar Dados** | ✗ | Não pode modificar informações do sistema |
| **Gerenciar Usuários** | ✗ | Sem acesso a painel administrativo |

**~ = Funcionalidade a ser definida como MVP ou fase 2**

---

## Necessidades Críticas

- **Dados Atualizados:** Informações sincronizadas em até 24h após rodada
- **Clareza Comparativa:** Fácil visualizar diferenças entre clubes
- **Acesso Rápido:** Dashboard carrega em menos de 3 segundos
- **Confiabilidade:** Números devem ser verificáveis e consistentes
- **Contexto:** Saber o critério por trás de rankings ("melhor jogador" = o quê?)

---

## Pontos de Dor (Riscos)

- Dados fora de sincronia afetam confiança em investimento
- Falta de transparência sobre como "melhor/pior jogador" é calculado
- Interface confusa que dificulta comparação entre clubes
- Dados históricos indisponíveis (não consegue avaliar evolução)

---

## Métricas de Sucesso

- **Engajamento:** Investidor retorna ao menos 2x por semana
- **Confiança:** 100% dos dados são considerados "confiáveis"
- **Usabilidade:** Comparação entre 3 clubes realizada em menos de 2 minutos
- **Retenção:** Taxa de retorno >80% após primeira rodada acompanhada

---

## Indicadores Essenciais Exibidos

| Indicador | Significado | Atualização |
|-----------|------------|------------|
| **Posição na Tabela** | Colocação atual no Brasileirão A | Semanal (após rodada) |
| **Vitórias** | Número total de vitórias | Semanal |
| **Derrotas** | Número total de derrotas | Semanal |
| **Saldo de Gols** | Gols pró - Gols contra | Semanal |
| **Melhor Jogador** | Jogador com melhor performance no período | A definir (semanal, últimas 5 rodadas, etc.) |
| **Pior Jogador** | Jogador com menor performance no período | A definir |
| **Tendência** | Melhora, estabilidade ou queda de performance | Calculada automaticamente |

---

## Variações e Extensões

- Investidor pode se tornar "membro premium" com alertas em tempo real e análises estatísticas avançadas
- Exportação para ferramentas de análise financeira (Excel, Tableau)
- Histórico completo de performance por temporada
- Comparação com temporadas passadas para entender padrões
