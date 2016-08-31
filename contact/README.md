# bigland-api-docs

[< Voltar](/README.md)

### Contact endpoint

Request for specific contact details

* [Target](#target)
* [Paylaod](#payload)
* [Response](#response)

## Target

Method `GET`
Endpoint `/contact`

## Payload

`https://{endpoint_base}/contact?id={contact_id}`

| Query parameter | Value | Example |
| --------------- | ----- | ------- |
| id              | One or more `contact_id` received from the `/test` request. Containing the candidates information | `?id=08ede4b6-d2ff-4972-b05b-fe545e41ff84` or `?id[]=xxx-xxx-xxx&id[]=xxx-xxx-xxx` |

## Response

```
{
    "id": "generated_user_id",

    "first_name": "Caleb",
    "last_name": "Santana",

    "nationality": "BR",

    "gender": "man",

    "email": "caleb.santana@domain.com"
}
```
