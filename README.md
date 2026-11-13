# Atividade 4 - Cabeçalho compartilhado

Este projeto é uma aplicação web com **Node.js + Express** que serve páginas HTML e inclui um cabeçalho compartilhado em todas elas.

Antes, o cabeçalho estava repetido em cada arquivo HTML. Agora ele fica em um único arquivo e o servidor o insere nas páginas.

O objetivo é praticar:
- como identificar trechos de HTML repetidos;
- como criar um arquivo de cabeçalho compartilhado;
- como ler arquivos com Node.js (`readFile`);
- como incluir o cabeçalho nas páginas usando Express (`app.engine` e `res.render`).

## Tecnologias usadas
- Node.js
- Express
- Dotenv
- HTML5
- CSS3

## Estrutura do projeto
```txt
atividade-4/
|- package.json
|- package-lock.json
|- .gitignore
|- .env (opcional)
|- server/
|  |- main.js
|  |- partials/
|     |- header.html
|- public/
   |- index.html
   |- assets/
   |  |- css/index.css
   |  |- images/
   |- pages/
      |- 1dsm.html ... 6dsm.html
```

## O que cada parte faz
- `server/main.js`: inicializa o servidor Express, configura os arquivos estáticos, monta as páginas com o cabeçalho e define as rotas.
- `server/partials/header.html`: cabeçalho compartilhado (logos, título do curso e menu dos seis semestres).
- `public/index.html`: página inicial.
- `public/pages`: páginas dos seis semestres, com o número do semestre e a lista de disciplinas.
- `public/assets`: arquivos de apoio da interface (CSS e imagens).
- `.env`: permite definir a porta do servidor (`PORT`).

## Como o cabeçalho compartilhado funciona
1. Cada página HTML tem o comentário `<!-- shared-header -->` no lugar onde o cabeçalho deve aparecer.
2. Em `server/main.js`, `app.engine("html", ...)` cadastra uma função que monta os arquivos HTML.
3. As rotas usam `res.render(...)`, e o Express chama essa função.
4. A função lê a página e o `header.html` com `readFile`, troca o comentário pelo conteúdo do cabeçalho com `replace()` e entrega o HTML completo com `callback(null, paginaCompleta)`.

Para alterar um logo ou um link do menu, basta editar o arquivo `server/partials/header.html`.

## Rotas da aplicação
- `/` -> página inicial (`index.html`)
- `/1dsm` até `/6dsm` -> página de cada semestre (`pages/1dsm.html` até `pages/6dsm.html`)
- qualquer outra rota -> mensagem "Página não encontrada" (404)

## Como executar o projeto
É necessário ter o Node.js na versão 20.11 ou superior.

1. Instale as dependências:

```bash
npm install
```

2. Inicie o servidor:

```bash
npm start
```

3. Abra no navegador:

```txt
http://localhost:3000
```

Se quiser usar outra porta, crie um arquivo `.env` com `PORT=3001`, por exemplo.

## Modo desenvolvimento
Para rodar com reinício automático ao salvar arquivos:

```bash
npm run dev
```
