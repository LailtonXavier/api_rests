# Uma API REST simples para consumo de dados

Para subir o projeto no ar com SQLite, copie o arquivo `.env_example` para `.env`.  

Você também precisará adicionar uma secret key no arquivo `.env`:

```
TOKEN_SECRET='sua_secret_key_aqui'
```

Execute os comandos abaixo:

```
npm i
npx sequelize db:migrate
npx sequelize db:seed:all
npm run dev
```

Neste ponto sua API deverá está rodando no endereço http://127.0.0.1:3001/.

Caso queira migrar para MySQL/MariaDB, edite as configurações de base de dados no arquivo `.env`, configure também o `src/config/database.js`.

Para SQLite as configurações são:

```javascript
require('dotenv').config();

module.exports = {
  dialect: 'sqlite',
  storage: './db.sqlite',
  define: {
    timestamps: true,
    underscored: true,
    underscoredAll: true,
    createdAt: 'created_at',
    updatedAt: 'updated_at',
  },
};
```

Para MySQL/MariaDB as configurações são:

```javascript
require('dotenv').config();

module.exports = {
  host: process.env.DATABASE_HOST,
  port: process.env.DATABASE_PORT,
  username: process.env.DATABASE_USERNAME,
  password: process.env.DATABASE_PASSWORD,
  database: process.env.DATABASE,
  dialectOptions: {
    timezone: 'America/Sao_Paulo',
  },
  timezone: 'America/Sao_Paulo',

  define: {
    timestamps: true,
    underscored: true,
    underscoredAll: true,
    createdAt: 'created_at',
    updatedAt: 'updated_at',
  },
};
```

Perceba que as configurações começando com `process.env.` vem do arquivo `.env`.

Os dados de usuário e senha dos arquivos de seed são:

- email = lailtonnx@gmail.com
- senha = 123456

- 

Você pode obter o token JWT na rota `/tokens`, passando os dados JSON:

```json
{
	"email": "admin@email.com",
	"password": "123456"
}
```

{
	"id" : 2,
	"nome" : "Lailton",
	"sobrenome": "Xavier",
	"idade": 23,
	"peso": 105,
	"altura": 1.5,
	"Fotos": 
	{
	"url" :
	"https://www.google.com/url?sa=i&url=https%3A%2F%2Fformacao.cancaonova.com%2Fafetividade-e-sexualidade%2Fafetividade-feminina%2Fquais-sao-caracteristicas-de-uma-mulher-de-valor%2F&psig=AOvVaw2ctoqIWawYyZhGq2T25UIf&ust=1620951976888000&source=images&cd=vfe&ved=0CAIQjRxqFwoTCLCN1-yyxfACFQAAAAAdAAAAABAD",
	
}
}

Headers:

```
Content-Type	application/json; charset=utf-8

# enviar alunos:

  {
    "id": 3,
    "nome": "fiona",
    "sobrenome": "silva",
    "email": "fione@gmail.com",
    "idade": 201,
    "peso": 150,
    "altura": 1000,
    "Fotos": []
  },
  {
    "id": 2,
    "nome": "jose",
    "sobrenome": "silva",
    "email": "jose@gmail.com",
    "idade": 201,
    "peso": 150,
    "altura": 1000,
    "Fotos": []
  },
  {
    "id": 1,
    "nome": "Lailton",
    "sobrenome": "Xavier",
    "email": "lailton@gmail.com",
    "idade": 21,
    "peso": 15,
    "altura": 100,
    "Fotos": []
  }


```
