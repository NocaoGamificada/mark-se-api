[Back](README.md)

# Documentação do Controller Course
## Índice
1. [Introdução](#introdução)
3. [EndPoints](#endpoints)
    - [Cliente](#cliente)
        - [GetAllCourses](#GetAllCourses)
        - [BuyCourse](#buycourse)
    - [Gerente](#gerente)
        - [CreateCourse](#createcourse)
        - [DeleteCourse](#deletecourse)
        - [UpdateCourse](#updatecourse)


## Introdução

<p>Este documento descreve o controller de contas da API `Marke_se_Api`. Este controller lida com todas as ações relacionadas ao registro e saida de leads, e visualização dos leades</p>

## EndPoints

### Cliente

#### GetAllCourses

- Endpoint: `/Course/GetAllCourses`
- Método: GET

Pega todos os cursos disponiveis na plataforma.
<br>

#### BuyCourse
<p>Compra o curso especificado.</p>

- Endpoint: `/Course/BuyCourse`
- Método: GET
- Parâmetros: `[Url] int courseId`, `[Header] string email`, `[Header] string password`
<br>

### Gerente

#### CreateCourse
<p>Cria um novo curso.</p>

- Endpoint: `/Course/CreateCourse`
- Método: POST
- Parâmetros: `[Header] string token`
- Resquest / Response Body: 
    ```json
    {
        "name": string,
        "description": string,
        "price": number
    }
    ```
<br>

#### DeleteCourse
<p>Deleta um curso</p>

- Endpoint: `/Course/DeleteCourse`
- Método: DELETE
- Parâmetros: `[Url] int courseId, [Header] string token`
<br>

#### UpdateCourse
<p>Atualiza um curso existente</p>

- Endpoint: `/Course/UpdateCourse`
- Método: PUT
- Parâmetros: `[Url] int courseId, [Header] string token`
- Resquest Body: 
    ```json
    {
        "name": string,
        "description": string,
        "price": number
    }
    ```
<br>
