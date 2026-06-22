# BetCup — Modelagem do Sistema (MEAN)

Repositório com a modelagem visual, wireframes e exemplos estáticos do protótipo "BetCup" — sistema de apostas da Copa.

## Como visualizar o protótipo localmente

Opções rápidas para abrir e inspecionar o protótipo (arquivo principal: `BetCup_Modelagem.html`):

- Abrir diretamente no navegador
	- Clique duas vezes em `BetCup_Modelagem.html` no explorador de arquivos.

- Usar um servidor HTTP local (recomendado para evitar problemas com recursos externos):

	- Python 3:

		```bash
		cd "c:/Users/luizh/Desktop/DESKTOP 2/codigos/BetCup_Modelagem-de-Sistema-MEAN"
		python -m http.server 8000
		# então abra http://localhost:8000/BetCup_Modelagem.html
		```

	- npx http-server (Node.js):

		```bash
		cd "c:/Users/luizh/Desktop/DESKTOP 2/codigos/BetCup_Modelagem-de-Sistema-MEAN"
		npx http-server -c-1 -p 8000
		# abra http://127.0.0.1:8000/BetCup_Modelagem.html
		```

- VS Code: instale a extensão **Live Server** e clique em "Go Live" com `BetCup_Modelagem.html` aberto.

## Requisitos (apenas para visualização)

- Navegador moderno (Chrome, Edge, Firefox)
- (Opcional) Python 3 ou Node.js para rodar servidor local

## Estrutura mínima do repositório

- `BetCup_Modelagem.html` — arquivo principal do protótipo/documentação visual
- `README.md` — instruções (este arquivo)
- `.git/` — controle de versão

## Observações

- Este repositório contém apenas um protótipo visual estático (HTML/CSS/JS). Não é necessário instalar dependências para visualizar o protótipo.
- Para transformar isso em um projeto Angular/Node/MongoDB real será necessário scaffolding adicional, dependências e configuração de backend.

---

## Como preparar o backend (Express) — instruções rápidas

Observação: o repositório atual contém apenas o protótipo estático. As instruções abaixo mostram como criar o backend mínimo para desenvolvimento.

1. Crie a pasta do servidor e inicialize o Node:

```bash
mkdir betcup-backend
cd betcup-backend
npm init -y
npm install express dotenv mongodb
npm install --save-dev nodemon
```

2. Exemplo mínimo de `server/index.js`:

```js
const express = require('express');
const app = express();
app.use(express.json());

app.get('/health', (req, res) => res.json({status: 'ok'}));

app.listen(3000, () => console.log('API running on http://localhost:3000'));
```

3. Scripts úteis no `package.json` do backend:

```json
"scripts": {
	"start": "node server/index.js",
	"dev": "nodemon server/index.js"
}
```

4. Conectar ao MongoDB: criar `server/config/db.js` usando `mongodb` driver e usar `process.env.MONGODB_URI`.

## Como preparar o frontend (Angular) — instruções rápidas

1. Instale Angular CLI (se ainda não instalada):

```bash
npm install -g @angular/cli
```

2. Crie o projeto Angular e execute:

```bash
ng new betcup-frontend
cd betcup-frontend
ng serve --open
```

3. Integre serviços para consumir a API Express (`src/app/services/*.ts`) e use `environment.ts` para apontar `apiBaseUrl`.

## Execução conjunta (desenvolvimento)

1. Inicie o backend (na pasta `betcup-backend`):

```bash
npm run dev
```

2. Inicie o frontend (na pasta `betcup-frontend`):

```bash
ng serve
```

Abra `http://localhost:4200` para o frontend e `http://localhost:3000` para a API.

---
