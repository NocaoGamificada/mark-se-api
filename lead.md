[Back](README.md)

# Documentação do Controller Lead

## Índice
1. [Introdução](#introdução)
3. [EndPoints](#endpoints)
    - [LeadRegister](#leadregister)
    - [LeadExit](#leadexit)
    - [GetAllLeads](#get-all-leads)


## Introdução

Este documento descreve o controller de contas da API `Marke_se_Api`. Este controller lida com todas as ações relacionadas ao registro e saida de leads, e visualização dos leades 

## EndPoints

# Cliente

#### LeadRegister

- Endpoint: `/Lead/LeadRegister`
- Método: POST

Efetua o registro do cliente no sistema.
- Request Body
    ```json
    {
        "name": string,
        "email": string,
        "phoneNumber": string,
        "alreadyUndertaken": boolean,
        "haveABusiness": boolean
    }
    ```

<br><br>

#### LeadExit

- Endpoint: `/Lead/LeadExit`
- Método: GET
- Parametros: `email`

Efetua a retirada do cliente no sistema.

<br><br>

# Gerentes

#### Get All Leads

- Endpoint: `/Lead/GetAllLeads`
- Método: GET
- Parametros: `[Header] string email`, `[Header] string token`

Pega todos os leads cadastrados
<br><br>

#### SendEmailForAllLeads

- Endpoint: `/Lead/sendEmailForAllLeads`
- Método: GET
- Parametros: `[Header] string email`, `[Header] string token`

Pega todos os leads cadastrados
- Request Body
    ```json
    {
        "subject": string,
        "html": string
    }
    ```
<br><br>