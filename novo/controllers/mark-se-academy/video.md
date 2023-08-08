# Controlador de cursos

Controller referente para fazer operações de crud dos cursos.

## Índice

- [Video Managers](#video-managers)
- [Course Clients](#video-clients)

##  Video Managers

### `POST /academy/course/video/add-in-course?courseId={id}`

Adiciona um modulo ao curso.

#### Requisição

```json
{
    "title": "titulo do modulo",
    "description": "descrição do modulo",
    "courseId": 1 // id do curso
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


### `PUT /academy/course/video/upload-video?videoCourseId={id}`

Atualiza o arquivo do video.

#### Requisição

Este endpoint aceita um formulário `multipart/form-data` com os seguintes campos:

- `file` (obrigatório): O arquivo a ser carregado deve ser obrigatoriamente ser um arquivo mp4.

### `PUT /academy/course/video/update?videoCourseId={Id}`

Atualiza as informações do curso

#### Requisição

```json
{
    "title": "titulo do modulo",
    "description": "descrição do modulo",
    "thumbFile": File // caso não queira atualizar é so deixar como nulo
}
```

### `DELETE /academy/course/video/delete?videoCourseId={Id}`

Deleta um curso somente se vc for super admin ou dono do curso

### `PUT /academy/course/video/update-thumb?videoCourseId={Id}`

Atualiza a thumbnail de um curso

#### Requisição

Este endpoint aceita um formulário `multipart/form-data` com os seguintes campos:

- `image` (obrigatório): O arquivo a ser carregado deve ser obrigatoriamente ser uma imagem (qualquer tipo).

### `PUT /academy/course/video/upload-material?videoCourseId={Id}`

Atualiza o material do video especificado

#### Requisição

Este endpoint aceita um formulário `multipart/form-data` com os seguintes campos:

- `file` (obrigatório): O arquivo a ser carregado deve ser obrigatoriamente um arquivo pdf.

## Video Clients

### `GET /academy/course/get?courseId={id}`

Obtém os detalhes do curso com o ID fornecido.

