# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento das API's nos Capstones do Q2.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.


### Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"


### Projects

POST /projects

Esse endpoint ira cadastrar os projetos realizados pelos usuarios logados.
Exemplo:
body: {
      "name": "corpomaquina",
      "type": "technology",
      "userId": 2
    }

authorization: {
    "Bearer": "token"
}

Get /projects

Ira mostrar todos os projetos cadastrados, tanto para usuarios logados quanto para nao logados. 

Status: 200-ok
        401-UNAUTHORIZED

### Comments

POST /comments 

body: {
    "comment": "exemplo"
}

Esse endpoint voce precisa estar logado para escrever comentarios.

GET /comments

Esse endpoint voce voce precisa estar logado para ler os comentarios.
authorization: {
    "Bearer": "token"
}

Status: 200-ok
        401-UNAUTHORIZED