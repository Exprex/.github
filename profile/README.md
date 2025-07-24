# Exprex

Este repositório contém o código de uma aplicação desenvolvida na disciplina de Projeto Integrado I, com o objetivo de divulgar os editais da PREX/UFC. A aplicação visa facilitar o compartilhamento e o acesso a esses editais, bem como às oportunidades de participação disponíveis para docentes da Universidade Federal do Ceará.

O sistema foi projetado para apoiar a organização e a publicação dos editais, promovendo maior transparência e acessibilidade. Além disso, oferece às alunas informações importantes sobre cronogramas, materiais de apoio e demais conteúdos relacionados às atividades e processos seletivos vinculados ao projeto.

---

## 👩‍💻 Autores

- **Arthur Hugo Alves Lima** — Sistemas e Mídias Digitais, UFC  
- **Lina dos Santos Martins** — Sistemas e Mídias Digitais, UFC  
- **Joao Pedro Mesquita Abreu** — Sistemas e Mídias Digitais, UFC  
- **Sofia Leandra Da Silva Viana** — Sistemas e Mídias Digitais, UFC  

---

## 🚀 Sobre

**Exprex** é uma aplicação que visa facilitar o compartilhamento e o acesso a editais.

- **Backend**: Node.js + Express + Sequelize (SQLite)  
- **Upload**: Multer  
- **Frontend**: Alpine.js  
- **Banco**: SQLite  

---

## ✅ Requisitos Funcionais

| ID   | Título                          | User Story                                                                                                                                        |
|------|----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| RF01 | Fazer upload de edital          | Como usuário, quero enviar um edital em PDF via formulário para que ele seja renomeado, salvo no servidor e registrado no banco de dados.         |
| RF02 | Listar editais                  | Como visitante, quero ver uma lista de editais com título, data e status para saber quais estão abertos ou encerrados.                            |
| RF03 | Editar informações              | Como administrador, quero editar o título, descrição, datas e categoria de um edital para manter as informações sempre atualizadas.               |
| RF04 | Excluir edital                  | Como administrador, quero excluir editais antigos ou com erro para manter o sistema limpo e organizado.                                           |
| RF05 | Validar uploads                 | Como sistema, quero aceitar apenas arquivos `.pdf` de até 10 MB para garantir integridade e evitar congestionamento no servidor.                  |
| RF06 | Servir arquivos estáticos       | Como usuário, quero acessar os PDFs, imagens e scripts diretamente via `/public` para navegação mais rápida.                                      |
| RF07 | Autenticar usuários             | Como administrador, quero fazer login para publicar, editar ou excluir editais com segurança.                                                     |
| RF08 | Filtrar e buscar editais        | Como visitante, quero filtrar editais por tipo (bolsa, monitoria, extensão etc.) ou buscar por palavras-chave para encontrar o que me interessa.  |
| RF09 | Adicionar anexos complementares | Como administrador, quero anexar cronogramas, formulários ou documentos extras aos editais para que tudo fique centralizado.                      |
| RF10 | Comentar ou reagir (opcional)   | Como usuário logado, quero poder deixar comentários ou reagir a um edital para tirar dúvidas ou marcar interesse. (Funcionalidade opcional)       |
| RF11 | Registrar erros e logs          | Como desenvolvedor, quero que o sistema registre erros e atividades para facilitar a manutenção e não depender de reza brava quando algo quebrar. |
| RF12 | Configurar via variáveis        | Como desenvolvedor, quero usar variáveis de ambiente no `.env` para senhas, caminhos e configurações sensíveis, longe do código-fonte.            |
| RF13 | Garantir layout responsivo      | Como visitante, quero acessar o sistema pelo celular, tablet ou desktop sem ver elementos desalinhados ou texto sumido.                           |
| RF14 | Mostrar status do edital        | Como visitante, quero ver claramente se o edital está **aberto**, **encerrado** ou **em análise**, para não perder prazos importantes.            |
| RF15 | Ordenar por data de publicação  | Como visitante, quero que os editais mais recentes apareçam primeiro para acompanhar as novidades sem precisar vasculhar tudo.                    |

---
## Requisitos Funcionais

| ID   | Título                     | Backend                                                            | Frontend                                                                | Comunicação (API)                                                         | Prioridade      |
| ---- | -------------------------- | ------------------------------------------------------------------ | ----------------------------------------------------------------------- | ------------------------------------------------------------------------- | --------------- |
| RF01 | Abrir modal de projeto     |N/A |Clique em "Ver mais" exibe modal com informações detalhadas| N/A |Alta Prioridade
| RF02 | Listar editais enviados             | Rota GET que busca todos os editais no banco (ordem decrescente)                                | Lista em cards com nome, descrição, botão abrir e botão excluir                                          | `GET /`                                                             | Alta Prioridade |
| RF03 | Acessar PDF no navegador           | Arquivo é servido via rota estática do Express                           | Link "Abrir PDF" abre nova aba                                             | `/uploads/:nome_do_arquivo`                                                         | Alta Prioridade |
| RF04 | Excluir imagem             | Rota POST que apaga do banco e remove o arquivo da pasta                         | Botão "Excluir" com confirmação                                                         | `POST /delete/:id`                                                        | Alta Prioridade |
| RF05 | Validar uploads            | Middleware do Multer para aceitar só PDF e limitar para 10MB               | Alerta de erro simples (resposta do servidor)                                | Retorno HTTP 400 com mensagem                                          | Alta Prioridade |
| RF06 | Servir arquivos estáticos  | Express serve as pastas `public/` (CSS) e `uploads/` (PDFs)                     | Interface com CSS simples (opcional: `public/style.css`)                              | N/A (arquivos acessados direto pelo navegador)                          | Alta Prioridade |
| RF07 | Tratar erros do sistema        | Middleware final trata erros do Multer e do sistema              | Exibe mensagem de erro direto na tela (texto simples)                       | Mensagens como: "Arquivo muito grande" ou "Erro ao salvar no banco"                 | Alta Prioridade |
| RF08 | Armazenar no PostgreSQL  | Conexão com banco via `pg.Pool`; inserção e exclusão com SQL        | N/A                                    | Banco usado internamente pelas rotas                                         | Alta Prioridade |
| RF09 | Interface amigável           | N/A                          | Formulário centralizado e cards organizados para listagem dos editais                                             | N/A | Alta Prioridade |




## 🛠 Tecnologias

- **Node.js**
- **Express**
- **Sequelize (SQLite)**
- **Multer** (upload de arquivos)
- **Alpine.js** (UI reativa)
- **Jsonwebtoken (JWT)** — segurança/autenticação

---

## 🤝 Contribuindo

Contribuições são sempre bem-vindas!

