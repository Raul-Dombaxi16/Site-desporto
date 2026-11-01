# CD Horizonte — versão dinâmica (desenvolvimento)

Site Bootstrap com frontend servido pelo Express, API REST e MySQL. Conteúdos como jogos, galeria, plantel, notícias e produtos são obtidos da base de dados. O painel `/admin` permite gerir conteúdos e consultar inscrições/mensagens.

## Requisitos
- Node.js 18+ (recomendado 20 LTS)
- MySQL 8+ ou MariaDB compatível

## Instalação local
1. Cria uma base de dados e importa `backend/schema.sql` no MySQL/phpMyAdmin.
2. Entra na pasta `backend`.
3. Executa `npm install`.
4. Copia `.env.example` para `.env` e preenche as credenciais MySQL e um `SESSION_SECRET` forte.
5. Executa `npm run create-admin` para criar o administrador.
6. Inicia com `npm run dev` e abre `http://localhost:3000`.
7. O painel fica em `http://localhost:3000/admin`.

## Funcionalidades
- Sessão de administrador, login/logout e password hash bcrypt.
- CRUD de jogos, jogadores, notícias e produtos.
- Upload de imagens (JPG/PNG/WEBP/GIF até 5 MB) e gestão da galeria.
- Inscrições de sócios e mensagens de contacto guardadas no MySQL.
- Páginas públicas de jogos, notícias, loja e plantel consomem a API.

## Imagens
As imagens são carregadas para `backend/uploads` e servidas em `/uploads`. Podes substituir as imagens demonstrativas no painel. Em produção, configura armazenamento persistente para uploads.

## Notas importantes
- Dados e marca são demonstrativos; substitui-os pelos dados autorizados do clube.
- Não existe integração com fornecedor de resultados desportivos ao vivo; o administrador atualiza o estado/resultado dos jogos.
- A loja é catálogo, sem checkout/pagamentos.
- Antes de produção: HTTPS, segredo de sessão forte, rate limiting, proteção CSRF, validação adicional, backups, testes, política de privacidade e revisão de permissões.
