# Atividade 4 - Cabeçalho compartilhado

Desenvolvimento Web I - Fatec

O cabeçalho (logos, título e menu dos semestres) fica em um único arquivo, `server/partials/header.html`. O servidor Express troca o comentário `<!-- shared-header -->` de cada página pelo conteúdo desse arquivo antes de enviar o HTML.

## Estrutura

```txt
server/
├── main.js
└── partials/
    └── header.html
public/
├── index.html
├── pages/
│   └── 1dsm.html ... 6dsm.html
└── assets/
```

## Como executar

```bash
npm install
npm start
```

Depois abra `http://localhost:3000`. A porta pode ser alterada com `PORT` em um arquivo `.env` (veja `.env.example`).
