# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento das API's nos Projetos Front-end.

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

## Post

POST /posts (Auth) <br/>
GET /posts <br/>
GET /posts/postId (Auth) <br/>
GET /users/userId/posts (Auth)

Com o método POST desse endpoint registra-se um novo post do usuário no banco de dados, necessitando que o usuário esteja logado para o mesmo
Já com o método GET desse endpoint, busca-se todos os posts no sistema, onde todos podem ler os mesmos, ou, passando o id de um determinado post, conseguimos buscar o mesmo isoladamente.
Para buscar os posts especificos feito por um usuário segue a rota -> /users/userId/posts

## Comments

POST /posts/postId/comments (Auth) <br/>
GET /posts/postId/comments  (Auth) <br/>

Com o método POST desse endpoint registra-se um novo comentário do usuário no post de outro usuário ou do próprio usuário no banco de dados, necessitando que o usuário esteja logado para o mesmo
Com o método GET desse endpoint, busca-se todos os comentários no post especifíco, onde o usuário precisar esta logado, para ler o mesmo.
