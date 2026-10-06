# 🏗️ Foot Fanatics — Visão Arquitetural das Personas

```
┌─────────────────────────────────────────────────────────────────┐
│                    FOOT FANATICS                                │
│         Série A do Campeonato Brasileiro 2026                   │
└─────────────────────────────────────────────────────────────────┘

┌────────────┐     ┌────────────┐     ┌────────────┐
│   ADMIN    │     │ INVESTIDOR │     │ TORCEDOR   │
│ (Gerente)  │     │ (Analista) │     │   (Fã)     │
└────────────┘     └────────────┘     └────────────┘
      │                   │                   │
      │                   │                   │
      v                   v                   v
  [ACESSO]          [ACESSO]            [ACESSO]
  TOTAL ao          TODOS os            APENAS 1
  SISTEMA           CLUBES              CLUBE

      │                   │                   │
      │ Gerencia Dados    │ Analisa Perf.    │ Acompanha
      │ Valida Integ.     │ Compara Clubes   │ Celebra
      │ Configura Ranks   │ Avalia Tendências│ Emoção
      │ Controla Acesso   │                  │
      │ Auditoria         │                  │
      │                   │                  │
      v                   v                   v
┌──────────────────────────────────────────────────────────┐
│                  BASE DE DADOS CENTRAL                   │
│  ┌────────────┬───────────┬──────────────────────────┐   │
│  │  CLUBES    │ JOGADORES │    USUÁRIOS & PERMS.    │   │
│  │ (20 times) │(Melhor    │ (Admin, Investidor,     │   │
│  │            │ Pior)     │  Torcedor)              │   │
│  └────────────┴───────────┴──────────────────────────┘   │
│  Atualização: Semanal (máximo 24h após rodada)          │
└──────────────────────────────────────────────────────────┘
```

---

## 📋 Detalhamento das Personas

### 1️⃣ ADMINISTRADOR (Admin)

**Função:** Manter o sistema funcionando, gerenciar dados  
**Acesso:** Sistema inteiro  
**Frequência:** Diário, conforme necessário

```
┌─────────────────────────────────────┐
│        ADMIN DASHBOARD              │
├─────────────────────────────────────┤
│ ✓ Atualizar Dados de Clubes         │
│   ├─ Vitórias/Derrotas              │
│   ├─ Saldo de Gols                  │
│   └─ Posição na Tabela              │
│                                     │
│ ✓ Gerenciar Jogadores               │
│   ├─ Melhor do Momento              │
│   ├─ Pior do Momento                │
│   └─ Histórico                      │
│                                     │
│ ✓ Controle de Usuários              │
│   ├─ Criar/Editar/Deletar           │
│   ├─ Atribuir Papéis                │
│   └─ Suspender Contas               │
│                                     │
│ ✓ Monitoramento                     │
│   ├─ Logs de Ações                  │
│   ├─ Integridade de Dados           │
│   └─ Alertas do Sistema             │
│                                     │
│ ✓ Configuração                      │
│   ├─ Critério de Rankings           │
│   ├─ Temporada do Campeonato        │
│   └─ Políticas de Segurança         │
└─────────────────────────────────────┘
```

**Indicadores de Sucesso:**
- ✅ Dados atualizados < 24h após rodada
- ✅ Uptime 99%+
- ✅ Zero brechas de segurança
- ✅ Auditoria 100% completa

---

### 2️⃣ INVESTIDOR (Analista de Performance)

**Função:** Analisar e comparar desempenho de clubes  
**Acesso:** Visualização de todos os 20 clubes  
**Frequência:** 2-3 vezes por semana

```
┌──────────────────────────────────────────────┐
│      INVESTOR DASHBOARD (Tabela)             │
├──────────────────────────────────────────────┤
│ Posição │ Clube      │ Vitórias │ Derrotas ││
├─────────┼────────────┼──────────┼──────────┤│
│  1º     │ Botafogo   │   25     │   5     ││
│  2º     │ Flamengo   │   24     │   6     ││
│  3º     │ São Paulo  │   22     │   8     ││
│  4º     │ Palmeiras  │   20     │   10    ││
│  5º     │ Grêmio     │   19     │   11    ││
│  ...    │   ...      │  ...     │  ...    ││
│  20º    │ Chapecoense│   8      │   22    ││
├──────────────────────────────────────────────┤
│                                              │
│ Filtros: [ Posição ▾ ] [ Tendência ▾ ]   │
│ Ordenação: [ Vitórias ↓ ]                 │
│                                              │
│ [Clique em clube para análise detalhada]   │
└──────────────────────────────────────────────┘
        │
        │ Clica em clube
        v
┌──────────────────────────────────────────┐
│     ANÁLISE DETALHADA (Botafogo)         │
├──────────────────────────────────────────┤
│ Informações Principais:                  │
│  • Posição: 1º lugar                     │
│  • Vitórias: 25                          │
│  • Derrotas: 5                           │
│  • Saldo de Gols: +28                    │
│  • Tendência: ↗ (Melhora)               │
│                                          │
│ Destaque de Jogadores:                  │
│  👍 Melhor: John (Rating 9.2/10)        │
│  👎 Pior: Alex (Rating 5.1/10)          │
│                                          │
│ [Exportar Comparação] [Comparar com outro]│
└──────────────────────────────────────────┘
```

**Indicadores de Sucesso:**
- ✅ Tabela carrega < 3 segundos
- ✅ Dados confiáveis 100%
- ✅ Comparação realizada < 2 minutos
- ✅ DAU 30%+

---

### 3️⃣ TORCEDOR (Fã de Futebol)

**Função:** Acompanhar seu time favorito  
**Acesso:** Apenas o clube escolhido  
**Frequência:** Diariamente, especialmente pós-jogo

```
┌─────────────────────────────────────┐
│  SELEÇÃO DE CLUBE (Primeira Vez)   │
├─────────────────────────────────────┤
│                                     │
│  Qual é seu time favorito?          │
│                                     │
│  🔍 [Buscar...                 ]   │
│                                     │
│  🟢 Flamengo                        │
│  🟢 Botafogo                        │
│  🔴 São Paulo                       │
│  🟡 Palmeiras                       │
│  🟦 Grêmio                          │
│  🟥 Internacional                   │
│  ...                                │
│                                     │
└─────────────────────────────────────┘
        │
        │ Seleciona Flamengo
        v
┌─────────────────────────────────────────────┐
│     🔴 PAINEL DO FLAMENGO 🔴               │
├─────────────────────────────────────────────┤
│                                             │
│  ┌─────────────────────────────────────┐  │
│  │  POSIÇÃO: 3º lugar                  │  │
│  │  VITÓRIAS: 22  |  DERROTAS: 8       │  │
│  │  SALDO DE GOLS: +18                 │  │
│  └─────────────────────────────────────┘  │
│                                             │
│  👍 MELHOR JOGADOR:                       │
│     Vinícius Jr. - Atacante              │
│     Rating: 8.7/10                       │
│                                             │
│  👎 PIOR JOGADOR:                        │
│     Diego - Meia                         │
│     Rating: 5.4/10                       │
│                                             │
│  📊 ÚLTIMAS RODADAS:                      │
│     Rodada 33: ✓ Vitória 2x1             │
│     Rodada 32: ✗ Derrota 0x3             │
│     Rodada 31: ✓ Vitória 4x0             │
│     Rodada 30: ✓ Vitória 1x0             │
│     Rodada 29: ✓ Empate 1x1              │
│                                             │
│  [Compartilhar no Twitter] [Ver Rival]    │
└─────────────────────────────────────────────┘
```

**Indicadores de Sucesso:**
- ✅ DAU 30%+ (usa diariamente)
- ✅ Satisfação NPS 50+
- ✅ Dashboard carrega < 3 segundos
- ✅ 70%+ compartilham resultados

---

## 📊 Matriz de Dados Centralizada

```
┌──────────────────────────────────────────────────────────────┐
│                     BASE DE DADOS                            │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│  TABELA: CLUBES                                             │
│  ┌─────┬────────────┬────────┬─────────┬────────┬─────────┐ │
│  │ ID  │ Nome       │ Posição│Vitórias │Derrotas│ Saldo  │ │
│  ├─────┼────────────┼────────┼─────────┼────────┼─────────┤ │
│  │ 1   │ Botafogo   │ 1      │ 25      │ 5      │ +28    │ │
│  │ 2   │ Flamengo   │ 3      │ 22      │ 8      │ +18    │ │
│  │ 3   │ São Paulo  │ 2      │ 24      │ 6      │ +22    │ │
│  │ ... │ ...        │ ...    │ ...     │ ...    │ ...    │ │
│  └─────┴────────────┴────────┴─────────┴────────┴─────────┘ │
│  Atualização: SEMANAL (máximo 24h após rodada)              │
│                                                              │
│  TABELA: JOGADORES                                          │
│  ┌─────┬────────┬──────────┬────────┬─────────┬──────────┐ │
│  │ ID  │ Nome   │ Clube    │Posição │ Rating  │ Status   │ │
│  ├─────┼────────┼──────────┼────────┼─────────┼──────────┤ │
│  │ 101 │Vinícius│ Flamengo │Atacante│ 8.7    │ MELHOR   │ │
│  │ 102 │ Diego  │ Flamengo │ Meia   │ 5.4    │ PIOR     │ │
│  │ ... │  ...   │  ...     │ ...    │ ...    │ ...      │ │
│  └─────┴────────┴──────────┴────────┴─────────┴──────────┘ │
│  Atualização: PERIÓDICA (a definir critério)               │
│                                                              │
│  TABELA: USUÁRIOS                                           │
│  ┌────┬──────────┬───────────┬──────────┬──────────────┐   │
│  │ ID │ Email    │ Tipo      │ Clube    │ Criado       │   │
│  ├────┼──────────┼───────────┼──────────┼──────────────┤   │
│  │ 1  │admin@... │ ADMIN     │ N/A      │ 2026-10-05   │   │
│  │ 2  │inv@...   │ INVESTIDOR│ N/A      │ 2026-10-05   │   │
│  │ 3  │tor@...   │ TORCEDOR  │ Flamengo │ 2026-10-05   │   │
│  │ ... │ ...      │ ...       │ ...      │ ...          │   │
│  └────┴──────────┴───────────┴──────────┴──────────────┘   │
│  Atualização: ON-DEMAND (ao registrar novo usuário)         │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

---

## 🔐 Permissões por Persona

```
                ADMIN    INVESTIDOR    TORCEDOR
┌─────────────────────────────────────────────────┐
│ Ver Todos Clubes         ✓          ✓             │
│ Ver Clube Específico      ✓          ✓             ✓
│ Editar Dados Clubes       ✓          ✗             ✗
│ Editar Jogadores          ✓          ✗             ✗
│ Gerenciar Usuários        ✓          ✗             ✗
│ Acessar Logs              ✓          ✗             ✗
│ Configurar Rankings       ✓          ✗             ✗
│ Ver Painel Admin          ✓          ✗             ✗
│ Compartilhar Resultados   ~          ~             ✓
│ Exportar Dados            ~          ✓             ✗
└─────────────────────────────────────────────────┘
```

---

## 📈 Roadmap Resumido

### MVP (Agora)
- ✅ Admin Panel completo
- ✅ Investor Dashboard (tabela + detalhes)
- ✅ Torcedor Dashboard (clube único)
- ✅ Sincronização semanal de dados
- ✅ Permissões por persona

### Fase 2 (T+3 meses)
- 📋 Histórico de temporadas
- 📋 Comparação lado-a-lado avançada
- 📋 Exportação de relatórios
- 📋 Notificações em tempo real
- 📋 Integração com redes sociais

### Fase 3 (T+6 meses)
- 🚀 Community de torcedores
- 🚀 Análises estatísticas avançadas
- 🚀 Suporte para Série B
- 🚀 API pública
- 🚀 Fantasy Football

---

## 🎯 Métricas de Sucesso

| Métrica | Meta MVP | Fase 2 |
|---------|----------|--------|
| DAU (Daily Active Users) | 10%+ | 30%+ |
| Retenção 7-dia | 60%+ | 75%+ |
| Uptime | 99%+ | 99.9%+ |
| Tempo de Load | <3s | <2s |
| Satisfação (NPS) | 50+ | 70+ |

---

**Criado por Morgan (PM)**  
**Outubro 5, 2026**
