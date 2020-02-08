# Vue.js + Laravel API + Docker

## About
Docker template for Gizson project.

## Stack includes
* Vue.js
* Laravel (6.13.1 version)
* Mysql 8.0
* Nginx

## Installation

**1. Clone the repository and enter its folder**
```
git clone https://github.com/gizumo-inc/gizhack_team_k.git your-app-folder
cd your-app-folder
```

**2. Copy environment files**
```
cp .env.example .env
cp src/.env.example src/.env
```

**3. Edit DB Username and Password**
.env
```
DB_USER=example
DB_PASS=example
```
src/.env
```
DB_USER=example
DB_PASS=example

DB_USERNAME=example
DB_PASSWORD=example
```

**4. Making locally-trusted development certificates**
```
brew install mkcert
mkcert -install
mkdir cert-key
cd cert-key
mkcert localhost 127.0.0.1
```

**4. Build and up docker containers (It may take up to 10 minutes)**
```
docker-compose up -d --build
```

**5. Install composer dependencies**
```
docker-compose exec app composer install
```

**6. Set up laravel permissions**
```
sudo chmod -R 777 src/bootstrap/cache
sudo chmod -R 777 src/storage
```
**7. Generate Laravel's APP Key**
```
docker-compose exec app php artisan key:generate
```

**8. Install NPM packages**
```
cd src
npm install
```
or
```
docker-compose exec app npm install
```

**8. Run package.json script**
```
cd src
npm run dev
```
or
```
docker-compose exec app npm run dev
```

**9. Migration**
```
docker-compose exec app php artisan migrate
```

Now, you can access the URL http://localhost:8080 and can see Top page.

