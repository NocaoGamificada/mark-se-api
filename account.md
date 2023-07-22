[Back](README.md)

# Documentação do Controller Account

## Índice
1. [Introdução](#introdução)
3. [EndPoints](#endpoints)
    - [Cliente](#cliente)
        - [Login](#login)
        - [Registro](#registro)
        - [Ativar Conta](#ativar-conta)
        - [Reenviar Email](#reenviar-email)
    - [Gerentes](#gerentes)
        - [Registro](#registro-gerente)
        - [Login](#login-gerente)

## Introdução

Este documento descreve o controller de contas da API `Marke_se_Api`. Este controller lida com todas as ações relacionadas ao login, registro e autenticação de contas de clientes e gerentes.

## EndPoints

# Cliente

#### Login

- Endpoint: `/Account/Login/Client`
- Método: GET
- Parâmetros: `string email`, `string password`

Efetua o login do cliente no sistema.
<br><br>

#### Registro

- Endpoint: `/Account/Register/Client`
- Método: POST
- Parâmetros: `[Bind] Client client`

Registra um novo cliente no sistema.
- Resquest / Response
```json
{
    "name": string,
    "dateOfBirth": string('ano-mês-dia'),
    "email": string,
    "password": string
}
```
<br>
#### Ativar Conta

- Endpoint: `/Account/activateAccount`
- Método: GET
- Parâmetros: `string token`, `string email`

Ativa a conta do cliente usando o token enviado por e-mail.
<br><br>
#### Reenviar Email

- Endpoint: `/Account/Login/resendEmail`
- Método: GET
- Parâmetros: `string email`, `string password`

Reenvia o e-mail de ativação de conta para o cliente.
<br><br>
# Gerentes

#### Registro Gerente

- Endpoint: `/Account/Register/Manager`
- Método: POST
- Parâmetros: `Manager Manager`, `[Header] string email`, `[Header] string token`

Registra um novo gerente no sistema.
- Request:
```json
{
    "name": string,
    "email": string
}
```
- Response:
```json
{
    "name": string,
    "email": string,
    "acessToken": string
}
```

#### Login Gerente

- Endpoint: `/Account/Login/Manager`
- Método: GET
- Parâmetros: `string email`, `string token`

Efetua o login do gerente no sistema.