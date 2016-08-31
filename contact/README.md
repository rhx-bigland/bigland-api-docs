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

"first_name": "Caleb",
"last_name": "Santana",

"birth_date": 1440035583,
"dependents": 2,
"nationality": "BR",

"gender": "man",
"marital_status": "single",

"email": [ "caleb.santana@domain.com" ],

"main_address": {

    "zip_code": "09955-222",

    "geolocation": {
        "lat": -23.3197758,
        "lng": -41.425777999
    }
},

"skill_tags": [ "angular2", "react" ],
"language": [
    { "label": "en", "proficiency": "FP" }
],

"education": [
    {
        "degree": "bachelor"

        "started_at": 1440035583,
        "finished_at": 1440035583
    }
],

"trajectory": [
    {
        "company": { "industry": "124" },

        "title": "Desenvolvedor front-end",
        "summary": "<div>Descrição sobre o trabalho desenvolvido</div>",

        "started_at": 1440035583,
        "finished_at": undefined,
        "is_current": true,

        "employment_type": "FT",
        "employment_type_legal": "PJ"
    }
]

}
```
