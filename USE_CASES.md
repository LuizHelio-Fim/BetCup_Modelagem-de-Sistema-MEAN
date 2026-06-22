# Casos de Uso Principais — BetCup

Versão resumida dos casos de uso exigidos para a modelagem MEAN.

## Atores
- Usuário (apostador)
- Administrador
- Sistema (serviços backend para cálculo e persistência)

## Casos de Uso

1. Registrar Conta
   - Ator: Usuário
   - Descrição: Usuário preenche nome, e-mail e senha. Sistema cria conta com role `member`.

2. Autenticar (Login)
   - Ator: Usuário
   - Descrição: Usuário fornece e-mail e senha; sistema retorna JWT para consumo das APIs.

3. Visualizar jogos
   - Ator: Usuário
   - Descrição: Usuario consulta lista de jogos da Copa, horários e status (agendado, aberto, finalizado).

4. Registrar aposta
   - Ator: Usuário
   - Descrição: Usuario informa placar previsto (home/away) para uma partida com apostas abertas.

5. Visualizar histórico de apostas
   - Ator: Usuário
   - Descrição: Usuario verifica suas apostas, pontos obtidos e status de cada aposta.

6. Consultar ranking
   - Ator: Usuário
   - Descrição: Visualiza ranking global com posições e pontos acumulados.

7. Gerenciar jogos
   - Ator: Administrador
   - Descrição: Cria/edita partidas, altera status (abrir/encerrar apostas), e publica resultados oficiais.

8. Processar resultados e pontuação
   - Ator: Sistema / Administrador
   - Descrição: Ao inserir resultado oficial, sistema recalcula pontos das apostas e atualiza ranking.

9. Monitoramento e relatórios
   - Ator: Administrador
   - Descrição: Visualiza totais de usuários, apostas e estatísticas gerais.

---

Para cada caso de uso acima deve haver especificação de rota API (ex: POST /auth/login, GET /games, POST /bets, PUT /games/:id/result) e controles no frontend (guards para rotas protegidas usando JWT).
