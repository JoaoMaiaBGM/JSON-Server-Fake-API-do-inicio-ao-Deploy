# JSON-Server-Fake-API-do-inicio-ao-Deploy

Creating a API, using Heroku, to use in a front end project.

# Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

# Cadastro

POST /register
POST /signup
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password. Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

# Login

POST /login
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

# Movies

Para cadastrar um novo filme o usário precisa estar logado. Após fazer o login, o usuário pode cadastrar um novo filme utilizando um título, o ano de lançamento e um resumo, através do endpoint:

POST /movies

{
"title": "Lord of the rings",
"resume": "A young hobbit, Frodo, who has found the One Ring that belongs to the Dark Lord Sauron, begins his journey with eight companions to Mount Doom, the only place where it can be destroyed.",
"year": 2001
}

# Cities (rota autenticada)

Para cadastrar e ler sobre uma cidade o usário deve estar logado. Cadastrando uma nova cidade o usuário devel utilizar um nome, um estado e uma região, através do endpoint:

POST /cities

{
"name": "Recife",
"state": "Pernambuco",
"region": "nordeste"
}

para deletar uma cidade, o usuário utilizará o seguinte endpoint:

DELETE /cities/idCidade
