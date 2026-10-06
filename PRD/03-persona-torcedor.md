# Persona: Torcedor

## Perfil Geral

| Atributo | Valor |
|----------|-------|
| **Nome** | Fã/Torcedor do Futebol Brasileiro |
| **Escopo de Acesso** | Dados e informações do clube escolhido |
| **Responsabilidade** | Acompanhar, celebrar e analisar seu time |
| **Frequência de Uso** | Diariamente, especialmente dias de jogo |
| **Nível de Conhecimento** | Futebol; baixo para ferramentas digitais |

---

## Objetivos Principais

1. **Acompanhamento Emocional:** Seguir a jornada de seu time favorito na temporada
2. **Celebração de Vitórias:** Compartilhar sucesso com outros torcedores
3. **Análise Casual:** Entender o desempenho do time sem necessidade de análise profunda
4. **Conhecimento de Jogadores:** Ver quem são os destaques (melhores) e as dificuldades (piores)
5. **Comparação Local:** Ver como seu time se compara na tabela

---

## Jornada do Usuário

### Fluxo Principal

```
[Login/Entrada]
    ↓
[Seleção ou Confirmação de Clube Favorito]
    ↓
[Dashboard Dedicado do Clube]
    ├─ Informações Principais do Time
    │   ├─ Posição na Tabela
    │   ├─ Vitórias e Derrotas (Total)
    │   ├─ Saldo de Gols
    │   └─ Próximo Jogo (opcional)
    ├─ Destaque de Jogadores
    │   ├─ Melhor Jogador no Momento
    │   └─ Pior Jogador no Momento
    └─ Acompanhamento Emocional
        └─ Histórico Recente (Fase 2)
```

### Cenários de Uso

1. **Primeira Visita (Torcedor Novo)**
   - Entrada: Torcedor se registra no Foot Fanatics
   - Ações: Navega para Seleção de Clube → Procura por seu time → Clica para confirmar
   - Saída: Dashboard dedicado aparece com informações atualizadas

2. **Check-In Diário**
   - Entrada: Torcedor abre o app/site para "checar o time"
   - Ações: Vê posição na tabela, vitórias/derrotas, saldo de gols em destaque
   - Saída: Satisfação ao ver informações rápidas e claras de seu time

3. **Após Jogo Importante**
   - Entrada: Seu time jogou e torcedor quer celebrar (ou lamentar)
   - Ações: Abre dashboard → Verifica resultado, vê atualização de vitórias/derrotas → Visualiza jogadores em destaque
   - Saída: Compartilhamento emocionado do resultado

4. **Acompanhamento de Jogadores**
   - Entrada: Torcedor quer saber quem está jogando bem/mal no time
   - Ações: Scroll até seção "Destaque de Jogadores" → Vê "Melhor Jogador" e "Pior Jogador no Momento"
   - Saída: Entendimento de quem torcer mais ou quem está com dificuldade

5. **Comparação com Rival (Fase 2 / escopo a validar)**
   - Entrada: Torcedor quer saber como seu time se compara com rival
   - Ações: Busca por outro clube (funcionalidade limitada) → Vê apenas visão geral, sem editar
   - Saída: Comparação rápida, mas foco principal segue sendo seu clube

---

## Permissões e Funcionalidades

| Funcionalidade | Acesso | Descrição |
|----------------|--------|-----------|
| **Selecionar Clube Favorito** | ✓ | Escolher qual time acompanhar e salvá-lo |
| **Visualizar Dashboard do Clube** | ✓ | Painel dedicado com dados do time |
| **Ver Posição na Tabela** | ✓ | Colocação atual no Brasileirão A |
| **Ver Vitórias e Derrotas** | ✓ | Contagem total de vitórias e derrotas |
| **Ver Saldo de Gols** | ✓ | Gols pró - Gols contra |
| **Ver Melhor Jogador** | ✓ | Jogador com melhor performance |
| **Ver Pior Jogador** | ✓ | Jogador com menor performance |
| **Histórico de Últimos Jogos** | Fase 2 | Resultados das últimas cinco rodadas |
| **Buscar Outros Clubes** | ~ | Visualizar (sem editar) dados de outros times para comparação casual |
| **Compartilhar Resultados** | ~ | Opção de compartilhar no perfil ou redes sociais |
| **Receber Notificações** | ~ | Alerta quando seu time joga ou resultado é atualizado |
| **Editar Dados** | ✗ | Não pode modificar nenhuma informação |
| **Ver Admin Panel** | ✗ | Sem acesso a ferramentas administrativas |
| **Acessar Dados de Outros Torcedores** | ✗ | Privacidade; sem acesso a perfis de outros usuários |

**~ = Funcionalidade a ser definida como MVP ou fase 2**

---

## Necessidades Críticas

- **Rapidez:** Informação disponível em 1-2 cliques
- **Clareza Visual:** Números grandes e fáceis de ler
- **Atualização Confiável:** Dados sincronizados logo após jogo
- **Simplicidade:** Sem jargão técnico; linguagem de torcedor
- **Emoção:** Design que celebra vitórias e oferece suporte em derrotas

---

## Pontos de Dor (Riscos)

- Dados desatualizados (torcedor vê resultado antiga quando clube já jogou)
- Interface confusa ou lenta frustra acompanhamento diário
- Critério indefinido para "melhor/pior jogador" causa ceticismo
- Impossibilidade de ver histórico (torcedor quer lembrar performance do time)
- Comparação desfavorável com rival afeta retenção

---

## Métricas de Sucesso

- **Engajamento:** Torcedor abre app/site ao menos 1x por dia, especialmente pós-jogo
- **Satisfação:** 4.5+/5 de satisfação com atualização e clareza de dados
- **Retenção:** Taxa de retorno >70% após primeira semana
- **Compartilhamento:** 30%+ dos torcedores compartilham resultados em redes sociais

---

## Indicadores Essenciais Exibidos

| Indicador | Significado | Visibilidade |
|-----------|------------|------------|
| **Posição na Tabela** | Colocação atual (Ex: 5º lugar) | Destaque principal |
| **Vitórias** | Total de vitórias na temporada | Lado a lado com derrotas |
| **Derrotas** | Total de derrotas na temporada | Lado a lado com vitórias |
| **Saldo de Gols** | Gols a favor menos gols contra | Destaque após P/D |
| **Melhor Jogador** | Quem está jogando melhor (criado/definido periodicamente) | Card destacado |
| **Pior Jogador** | Quem está com dificuldade | Card destacado (com contexto positivo) |
| **Próximo Jogo** | Quando e contra quem (opcional, MVT?) | Banner ou seção própria |

---

## Variações e Extensões

- **Torcedor Casual:** Apenas quer saber colocação e resultado rápido
- **Torcedor Engajado:** Quer histórico completo, análises semanais, comparações
- **Fã de Jogador:** Quer tracking específico do desempenho de seu jogador favorito
- **Community:** Área para torcedores discutirem, compartilharem memes, celebrarem (fase 2)

---

## Acessibilidade

- Texto em tamanho legível
- Cores com contraste adequado para legibilidade
- Funcionalidade em mobile-first (a maioria acessa via smartphone)
- Sem requisitos de download de app na fase 1 (web-first)

---

## Exemplos de Interações Esperadas

### Exemplo 1: Torcedor Flamengo
1. Abre Foot Fanatics
2. Seleciona Flamengo como clube favorito
3. Vê dashboard com: Posição (ex: 3º), Vitórias (18), Derrotas (8), Saldo (+15)
4. Vê "Melhor Jogador: Vinícius Jr. (Rating 8.5/10)"
5. Vê "Pior Jogador: Goleiro X (Rating 5.2/10)"
6. Compartilha resultado satisfeito

### Exemplo 2: Torcedor São Paulo
1. Abre Foot Fanatics
2. Clube favorito já salvo (São Paulo)
3. Vê dashboard com dados atualizados
4. Nota queda na classificação desde última visita
5. Clica em "Pior Jogador" para entender dificuldade
6. Visualiza esperança com "Melhor Jogador" em destaque
7. Volta amanhã para verificar próximo jogo
