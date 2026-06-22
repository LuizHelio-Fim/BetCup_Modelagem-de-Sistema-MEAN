# Estrutura de Diretórios sugerida — BetCup

Estrutura sugerida para o projeto MEAN.

## Frontend (Angular)

```
betcup-frontend/
├─ src/
│  ├─ app/
│  │  ├─ pages/
│  │  │  ├─ login/
│  │  │  ├─ register/
│  │  │  ├─ dashboard/
│  │  │  ├─ bets/
│  │  │  └─ ranking/
│  │  ├─ components/
│  │  │  ├─ header/
│  │  │  ├─ footer/
│  │  │  └─ match-card/
│  │  ├─ services/
│  │  │  ├─ auth.service.ts
│  │  │  └─ bets.service.ts
│  │  └─ guards/
│  └─ assets/
├─ angular.json
└─ package.json
```

## Backend (Express)

```
betcup-backend/
├─ server/
│  ├─ controllers/
│  │  ├─ auth.controller.js
│  │  ├─ bets.controller.js
│  │  └─ games.controller.js
│  ├─ routes/
│  │  ├─ auth.routes.js
│  │  ├─ bets.routes.js
│  │  └─ games.routes.js
│  ├─ middlewares/
│  │  ├─ jwt.middleware.js
│  │  └─ error.handler.js
│  ├─ repositories/
│  │  └─ mongo-repo.js
│  ├─ config/
│  │  └─ db.js
│  └─ index.js
├─ package.json
└─ .env
```

Observações:
- Rotas seguem padrão REST: `GET /games`, `POST /bets`, `PUT /games/:id/result`.
- Middleware JWT protege rotas sensíveis. Repositório usa driver nativo do MongoDB para acesso.
