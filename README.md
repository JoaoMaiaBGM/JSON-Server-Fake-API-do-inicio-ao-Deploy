# JSON-Server-Fake-API-do-inicio-ao-Deploy

Creating a API, using Heroku, to use in a front end project.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login. Contudo, nessa fake api iremos usar os seguintes endpoints:

### Cadastro

POST /register

body:<br>
{<br>
"email": "joao@mail.com",<br>
"password": "123456",<br>
"name": "João"<br>
}

response:<br>
{<br>
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.<br> eyJlbWFpbCI6ImpvYW9AbWFpbC5jb20iLCJpYXQiOjE2NjE0NTMzNTcsImV4cCI6MTY2MTQ1Njk1Nywic3ViIjoiMiJ9.Feib36FaCqM8TxmdWZiJo0aVU5GmWDA1A4VX2GPgpfg",<br>
"user": {<br>
"email": "joao@mail.com",<br>
"name": "João",<br>
"id": 2<br>
}<br>
}

### Login

POST /login

body:<br>
{<br>
"email": "marta@mail.com",<br>
"password": "123456"<br>
}

response:<br>
{<br>
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.<br> eyJlbWFpbCI6Im1hcnRhQG1haWwuY29tIiwiaWF0IjoxNjYxNDU3MzQ3LCJleHAiOjE2NjE0NjA5NDcsInN1YiI6IjEifQ.3ovemJIJcrj-d1FNnUvEVhX3OjpMZjL_i8Dvd4NI1Ts",<br>
"user": {<br>
"email": "marta@mail.com",<br>
"name": "Marta",<br>
"id": 1<br>
}<br>
}

### Movies

Para cadastrar um novo filme o usário precisa estar logado. Após fazer o login, o usuário pode cadastrar um novo filme utilizando um título, o ano de lançamento e um resumo, através do endpoint:

POST /movies

body:<br>
{<br>
"title": "Lord of the rings",<br>
"resume": "A young hobbit, Frodo, who has found the One Ring that belongs to the Dark Lord Sauron, begins his journey with eight companions to Mount Doom, the only place where it can be destroyed.",<br>
"year": 2001<br>
}

response:<br>
{<br>
"title": "Lord of the rings",<br>
"resume": "A young hobbit, Frodo, who has found the One Ring that belongs to the Dark Lord Sauron, begins his journey with eight companions to Mount Doom, the only place where it can be destroyed.",<br>
"year": 2001,<br>
"id": 1<br>
}

### Cities (rota autenticada)

Para cadastrar e ler sobre uma cidade o usário deve estar logado. Cadastrando uma nova cidade o usuário devel utilizar um nome, um estado e uma região, através do endpoint:

POST /cities

body:<br>
{<br>
"name": "Recife",<br>
"state": "Pernambuco",<br>
"region": "nordeste"<br>
}

response:<br>
{<br>
"name": "Recife",<br>
"state": "Pernambuco",<br>
"region": "nordeste"<br>
"id": 1<br>
}

para deletar uma cidade, o usuário utilizará o seguinte endpoint:

DELETE /cities/idCidade
