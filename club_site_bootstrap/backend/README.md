# Backend CD Horizonte

API Node.js/Express + MySQL, sessões de administrador, gestão de jogos, galeria, plantel, notícias, inscrições e mensagens.

## Requisitos
- Node.js 20+ e MySQL 8+
- Terminal na pasta `backend`

## Instalação local
1. Cria a base de dados e tabelas: executa `schema.sql` no MySQL (Workbench/phpMyAdmin).
2. Copia `.env.example` para `.env` e configura credenciais reais. Define `SESSION_SECRET` longo e aleatório e `ADMIN_PASSWORD` com pelo menos 12 caracteres.
3. `npm install`
4. `npm run create-admin`
5. `npm run dev`
6. Abre `http://localhost:3000/admin`

## Endpoints
Públicos: `GET /api/public/matches|gallery|players|news`, `POST /api/public/memberships`, `POST /api/public/messages`.
Autenticação: `POST /api/auth/login`, `GET /api/auth/me`, `POST /api/auth/logout`.
Admin autenticado: `/api/admin/matches`, `/api/admin/gallery`, `/api/admin/players`, `/api/admin/news`, `/api/admin/memberships`, `/api/admin/messages`.

## Segurança antes de publicar
- HTTPS obrigatório em produção; `NODE_ENV=production` activa cookie Secure.
- Nunca publiques `.env`, credenciais ou backups SQL.
- Cria um utilizador MySQL com permissões apenas sobre `cd_horizonte`, não uses root.
- Restrinja acesso ao painel, faça backups, atualize dependências e configure limites/rate-limit no login e proteção CSRF para produção.
- O upload aceita apenas JPEG/PNG/WebP até 5 MB; para produção, acrescente antivírus/armazenamento externo e validação real do conteúdo.
- A autenticação inicial cria um administrador. Não há registo público de administradores.

Este é um backend inicial funcional para desenvolvimento, não uma auditoria de segurança nem um sistema pronto para dados reais sem configuração, testes e endurecimento de produção.
