# Controlador de cursos

Controller referente para fazer operações de crud dos cursos.

## Índice

- [Course Managers](#course-managers)
- [Course Clients](#course-client)

## Course Managers

### `GET /academy/course/get?courseId={id}`

Obtém os detalhes do curso com o ID fornecido.

#### Resposta

```json
{
    "id": 1,
    "title": "Nome do Curso",
    "description": "Descrição do Curso",
    "price": 199.99,
    "authorId": 1,
    "evaluationTotal": 4.5,
    "creationDate": "2023-07-12T00:00:00Z",
    "categoriesList": ["category1", "category2", "category3"]
}
```

### `POST /academy/course/add`

Cria um novo curso

#### Corpo da requisição

```json
{
    "title": "Nome do Curso",
    "description": "Descrição do Curso",
    "price": 0,
    "categoriesList": ["category1", "category2", "category3"]
}
```

#### Resposta
```json
{
    "id": 1,
    "title": "Nome do Curso",
    "description": "Descrição do Curso",
    "price": 199.99,
    "authorId": 1,
    "evaluationTotal": 4.5,
    "creationDate": "2023-07-12T00:00:00Z",
    "categoriesList": ["category1", "category2", "category3"]
}
```

### `PUT /academy/course/update?courseId={id}`

Atualiza as informações do curso

#### Corpo da requisição

```json
{
    "title": "Nome do Curso",
    "description": "Descrição do Curso",
    "price": 0,
    "categoriesList": ["category1", "category2", "category3"]
}
```

#### Resposta

Http status 200

### `DELETE /academy/course/delete?courseId={id}`

Deleta um curso vc so pode deletar se tiver permissão de super-admin ou for dono do curso

### `PUT /academy/course/update-thumb?courseId={id}`

Atualiza a thumbnail do curso

#### Corpo da requisição

Este endpoint aceita um formulário `multipart/form-data` com os seguintes campos:

- `image` (obrigatório): O arquivo a ser carregado deve ser obrigatoriamente ser uma imagem (qualquer tipo).

#### Resposta

Http status 200

### `GET /academy/course/can-edit?courseId={id}`

Diz se você tem permissão para editar ou deletar o curso.

### `GET /academy/course/get-owner-courses`

Retorna todos os cursos criados pelo usuario

### `POST /academy/course/add-client-in-course?clientId={id}&courseId={id}`

Da permissão para um usuario acessar um curso como aluno, permissão so pode ser efetuada se for super-admin ou dono do curso

## Course Client

### `GET /academy/course/get-all?page={index}&count={count}&filter={filters}(opcional)`

pega todos os cursos em ordena eles do mais novo ao mais antigo caso o parametro filter estiver vazio caso queira inverter a ordem é so colocar o valor de 'old' ou se quiser ter o mesmo resultado é so colocar 'new'

#### Resposta

```json
[
    {
        "id": 1,
        "title": "Nome do Curso",
        "description": "Descrição do Curso",
        "price": 199.99,
        "authorId": 1,
        "evaluationTotal": 4.5,
        "creationDate": "2023-07-12T00:00:00Z",
        "categoriesList": ["category1", "category2", "category3"]
    },
    ...
]
```

### `GET /academy/course/get-thumb?courseId={id}`

retorna a thumbnail do curso

### `GET /academy/course/search?q={searchTerm}&page={index}&filter={filter}(opcional)`

pesquisa os cursos de acordo com o titulo e ordena eles do mais novo ao mais antigo caso o parametro filter estiver vazio caso queira inverter a ordem é so colocar o valor de 'old' ou se quiser ter o mesmo resultado é so colocar 'new'

#### Resposta

```json
[
    {
        "id": 1,
        "title": "Nome do Curso",
        "description": "Descrição do Curso",
        "price": 199.99,
        "authorId": 1,
        "evaluationTotal": 4.5,
        "creationDate": "2023-07-12T00:00:00Z",
        "categoriesList": ["category1", "category2", "category3"]
    },
    ...
]
```

### `GET /academy/course/get-client-courses`

Retorna todos os cursos ao qual o usuario esta inscrito no momento caso ele seja um usuario que possa criar cursos também retorna os que ele criou

#### Resposta

```json
{
    "registered": [
        {
            "id": 1,
            "title": "Nome do Curso",
            "description": "Descrição do Curso",
            "price": 199.99,
            "authorId": 1,
            "evaluationTotal": 4.5,
            "creationDate": "2023-07-12T00:00:00Z",
            "categoriesList": ["category1", "category2", "category3"]
        },
        ...
    ],
    "owner": [
        {
            "id": 1,
            "title": "Nome do Curso",
            "description": "Descrição do Curso",
            "price": 199.99,
            "authorId": 1,
            "evaluationTotal": 4.5,
            "creationDate": "2023-07-12T00:00:00Z",
            "categoriesList": ["category1", "category2", "category3"]
        },
        ...
    ]
}
```

### `GET /academy/course/get-info?courseId={id}`

Pega as minimas informações de um curso especificado pelo id

#### Resposta

```json
{
    "id": 1,
    "title": "Nome do Curso",
    "description": "Descrição do Curso",
    "price": 199.99,
    "authorId": 1,
    "evaluationTotal": 4.5,
    "creationDate": "2023-07-12T00:00:00Z",
    "categoriesList": ["category1", "category2", "category3"]
}
```

### `GET /academy/course/get?courseId={id}`

Pega todas as informações da pagina do curso

#### Resposta
```json
{
    "course": {
        {
            "id": 1,
            "title": "Nome do Curso",
            "description": "Descrição do Curso",
            "price": 199.99,
            "authorId": 1,
            "evaluationTotal": 4.5,
            "creationDate": "2023-07-12T00:00:00Z",
            "categoriesList": ["category1", "category2", "category3"]
        }
    },
    "videos": [
        {
            "id": 1,
            "title": "Nome do Curso",
            "description": "Descrição do Curso",
            "index": 1,
            "haveQuestions": true
        },
        ...
    ],
    "comments": [
        {
            "id": 1,
            "courseId": 1,
            "content": "Conteudo do comentario",
            "owner": {
                "id": 1,
                "name": "Nome do usuario"
            }
        },
        ...
    ]
}
```

### `POST /academy/course/buy-course?courseId={id}`

Compra um curso (ainda não completamente implementada)

### `POST /academy/course/comment?courseId={id}`

Pemite o usuario fazer um comentario sobre o curso em questão, apenas se ele estiver inscrito no curso

### `GET /academy/course/have-course?courseId={id}`

Retorna se o usuario esta inscrito no curso em questão ou não

    