# Atividade 4 - Cabeçalho compartilhado

Desenvolvimento Web I - Fatec

Aplicação com Node.js e Express em que o cabeçalho (logos, título do curso e menu dos seis semestres) fica em um único arquivo, `server/partials/header.html`. O servidor troca o comentário `<!-- shared-header -->` de cada página pelo conteúdo desse arquivo antes de enviar o HTML.

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

## Rotas

- `/` - página inicial
- `/1dsm` a `/6dsm` - páginas dos semestres
- qualquer outra rota - "Página não encontrada"

## Como executar

Requer Node.js 20.11 ou superior.

```bash
npm install
npm start
```

Abra `http://localhost:3000` no navegador.
