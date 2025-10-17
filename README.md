# Nome do projeto
PROJECT_NAME="chatLaravelPusher"

echo "Criando o projeto Laravel..."
composer create-project laravel/laravel $PROJECT_NAME
cd $PROJECT_NAME || exit

echo "Instalando Laravel Breeze..."
composer require laravel/breeze
php artisan breeze:install

echo "Instalando Chatify..."
composer require munafio/chatify
php artisan chatify:install

echo "Instalando dependências front-end..."
npm install

echo "Compilando assets com pnpm..."
pnpm run dev

echo "Rodando migrações..."
php artisan migrate

echo "Gerando README.md..."
cat <<EOF > README.md
# Chat Laravel com Pusher (Chatify)

Este projeto é um sistema de chat em tempo real utilizando o framework **Laravel**, com a biblioteca **Chatify** para interface e lógica de mensagens. Usa **Laravel Breeze** para autenticação e **Pusher** para WebSockets em tempo real.

## Tecnologias utilizadas

- PHP 8+
- Laravel
- Laravel Breeze (autenticação)
- Chatify
- Composer
- PNPM
- MySQL
- Vite
- Pusher

---

## Comandos usados na criação

\`\`\`bash
composer create-project laravel/laravel chatLaravelPusher
cd chatLaravelPusher
composer require laravel/breeze
php artisan breeze:install
composer require munafio/chatify
php artisan chatify:install
npm i
pnpm run dev
php artisan serve
php artisan migrate
\`\`\`

---

## Como rodar localmente

### Pré-requisitos

- PHP >= 8.1
- Composer
- MySQL
- Node.js + PNPM
- Extensões PHP necessárias (OpenSSL, PDO, etc.)

### Passos

1. Clone o repositório:

\`\`\`bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd chatLaravelPusher
\`\`\`

2. Instale as dependências:

\`\`\`bash
composer install
npm install
\`\`\`

3. Copie o arquivo de ambiente e gere a chave:

\`\`\`bash
cp .env.example .env
php artisan key:generate
\`\`\`

4. Rode as migrações:

\`\`\`bash
php artisan migrate
\`\`\`

5. Compile os assets:

\`\`\`bash
npm run dev
\`\`\`

6. (EM OUTRO TERMINAL) Suba o servidor local:

\`\`\`bash
php artisan serve
\`\`\`

Acesse: [http://localhost:8000]

---

## Funcionalidades

- Login e registro
- Chat em tempo real
- Interface pronta via Chatify
- Notificações, histórico e mais

---

<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

You may also try the [Laravel Bootcamp](https://bootcamp.laravel.com), where you will be guided through building a modern Laravel application from scratch.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains thousands of video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the [Laravel Partners program](https://partners.laravel.com).

### Premium Partners

- **[Vehikl](https://vehikl.com)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel)**
- **[DevSquad](https://devsquad.com/hire-laravel-developers)**
- **[Redberry](https://redberry.international/laravel-development)**
- **[Active Logic](https://activelogic.com)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
