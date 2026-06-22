# Modelagem MongoDB — BetCup

Collections principais e exemplos de documentos JSON.

## users

Exemplo de documento:

```json
{
  "_id": "641f6a1c0b1234ab56cd7890",
  "name": "Lucas Martins",
  "email": "lucas@betcup.com",
  "passwordHash": "<bcrypt-hash>",
  "role": "member",
  "score": 1980,
  "createdAt": "2026-05-27T14:12:00Z"
}
```

Índices sugeridos: `email` (unique), `score` (desc) para ranking.

## games

Exemplo:

```json
{
  "_id": "645f7c2a7d8910fa23bc4567",
  "homeTeam": "Brasil",
  "awayTeam": "Argentina",
  "date": "2026-11-24T19:00:00Z",
  "stage": "Semi-final",
  "result": {"homeScore": 2, "awayScore": 1},
  "status": "finalized" // enum: scheduled|open|closed|finalized
}
```

## bets

Exemplo:

```json
{
  "_id": "648a5b3c9e2467b1f2345678",
  "userId": "641f6a1c0b1234ab56cd7890",
  "gameId": "645f7c2a7d8910fa23bc4567",
  "predicted": {"homeScore": 2, "awayScore": 1},
  "points": 10,
  "status": "confirmed", // pending|confirmed|cancelled
  "createdAt": "2026-12-01T10:05:00Z"
}
```

## rankings

Exemplo:

```json
{
  "_id": "649b9d4f8b345c2a78de9012",
  "userId": "641f6a1c0b1234ab56cd7890",
  "position": 1,
  "score": 1980,
  "wins": 32,
  "updatedAt": "2026-12-18T21:00:00Z"
}
```