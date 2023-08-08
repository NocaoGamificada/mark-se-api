# Controlador Mark-se Academy

Controller referente para tratar das contas.


## Client

### `POST /account/user/login`

#### Request

```json
{
    "email": "email",
    "password": "senha"
}
```

#### Response

```json
{
    "email": "email criptografado",
    "password": "senha criptografada",
    "roles": ["roles do usuario"]
}
```