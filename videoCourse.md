[Back](README.md)

# Documentação do Controller VideoCourse
## Índice
1. [Introdução](#introdução)
3. [EndPoints](#endpoints)
    - [Cliente](#cliente)
        - [GetVideo](#getvideo)
    - [Gerente](#gerente)
        - [AddVideoInCourse](#addvideoincourse)
        - [UploadFileVideoInCourse](#uploadfilevideoincourse)
        - [UpdateVideoInCourse](#updateinfovideoincourse)
        - [UpdateVideoThumbnail](#updatevideothumbnail)
        - [DeleteVideo](#deletevideo)
        - [DeleteManyVideos](#deletemanyvideos)

## Introdução

<p>Este documento descreve o controller de contas da API `Marke_se_Api`. Este controller lida com todas as ações relacionadas ao registro e saida de leads, e visualização dos leades</p>
<br>

## EndPoints

### Cliente
<br>

#### GetVideo
<p>Gera um link de acesso temporario para o video do curso especificado se o cliente tiver acesso a ele</p>

- Endpoint: `/VideoCourse/GetVideo`

- Método: GET

- Parâmetros: `[Url] int videoCourseId`, `[Header] string email`, `[Header] string password`
<br>

### Gerente
<br>

#### AddVideoInCourse
<p>Gera um link de acesso temporario para o video do curso especificado se o cliente tiver acesso a ele</p>

- Endpoint: `/VideoCourse/AddVideoInCourse`

- Método: POST

- Parâmetros: `[Header] string token`

- Request Body `[Json]`
```json
{
    "name": string,
    "description": string,
    "courseId": number
}
```

- Response body <br>
    - VideoCourseId: `number`
<br>

#### UploadFileVideoInCourse
<p>Envia o video para o Cloud Storage</p>

- Endpoint: `/VideoCourse/UploadFileVideoInCourse`

- Método: PUT

- Parâmetros: `[Url] int videoCourseId, [Header] string token`

- Request Body `[Form]`
    - file: `video/mp4`

#### UpdateInfoVideoInCourse
<p>Atualiza as informações de um video que esta relacionado a um curso</p>

- Endpoint: `/VideoCourse/UpdateInfoVideoInCourse`

- Método: PUT

- Parâmetros: `[Url] int videoCourseId`, `[Header] string token`

- Request Body `[Json]`
```json
{
    "name": string,
    "description": string,
    "courseId": number
}
```
<br>

#### UpdateVideosOrdy
<p>Atualiza a ordem dos videos</p>

- Endpoint: `/VideoCourse/UpdateVideosOrdy`

- Método: PUT

- Parâmetros: `[Url] int videoCourseId`, `[Header] string token`

- Request Body `[Json]`
```json
    [number, ...]
```

#### UpdateVideoThumbnail
<p>Atualiza a thumbnail</p>

- Endpoint: `/VideoCourse/UpdateVideoThumbnail`

- Método: PUT

- Parâmetros: `[Url] int videoCourseId`, `[Form] file`, `[Header] string token`

- Request Body `[Form]`
    - file: `image/*`

#### DeleteVideo
<p>Deleta um video do curso especificado</p>

- Endpoint: `/VideoCourse/DeleteVideo`

- Método: DELETE

- Parâmetros: `[Url] int videoCourseId`, `[Header] string token`

#### DeleteManyVideos
<p>Deleta varios videos do curso especificado</p>

- Endpoint: `/VideoCourse/DeleteManyVideos`

- Método: DELETE

- Parâmetros: `[Url] int courseId`, `[Url] int videoCourseId`, `[Header] string token` 