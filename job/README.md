# bigland-api-docs

[< Voltar](/README.md)

### Job endpoint

Request for specific job details

* [Target](#target)
* [Payload](#payload)
* [Response](#response)

## Target

Method `GET`
Endpoint `/job`

## Payload

`https://{endpoint_base}/job?id={job_id}`

| Query parameter | Value | Example |
| --------------- | ----- | ------- |
| id              | `job_id` received from the test dispatch request | `?id=08ede4b6-d2ff-4972-b05b-fe545e41ff84` |

## Response

```
{
  "id": "generated_uuid_job_1",

  "name": "Desenvolvedor front end",
  "summary": "<div>Vaga de dev front end!</div>",

  "industry": [ "tecnology" ],
  "position": [ "developer", "product manager", "vp" ],

  "employment_type": "FT",
  "employment_type_legal": "PJ"
}
```
