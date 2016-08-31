# bigland-api-docs

[< Voltar](/README.md)

### Job endpoint

Request for specific job details

* [Target](#target)
* [Paylaod](#payload)
* [Response](#response)

## Target

Method `GET`
Endpoint `/job`

## Payload

`https://{endpoint_base}/job?id={job_id}`

| Query parameter | Value | Example |
| --------------- | ----- | ------- |
| id              | `job_id` The job id sent from the test dispatch request | `?id=08ede4b6-d2ff-4972-b05b-fe545e41ff84` |

## Response

```
{
  "id": "generated_uuid_job_1",

  "name": "Desenvolvedor front end",
  "summary": "<div>Vaga de dev front end!</div>",

  "location": {

    "zip_code": "09955-222",

    "geolocation": {
      "lat": -23.3197758,
      "lng": -41.425777999
    }
  },

  "validation": {

    "skill_tags": [ "javascript", "angular2" ],
    "age_range": { "min": 21, "max": 23 },
    "required_gender": "man",
    "marital_status": "single",

    "language": [
      { "label": "en", "proficiency": "FP" }
    ],

    "company_size": "C",
    "education_level": "BAD",
    "job_function_code": "cnsl",
    "seniority": "EN",

    "monthly_travel_availability": 5,
    "relative_travel_distance": 15,
    "house_move_available": false,

    "industry": [ "tecnology" ],
    "position": [ "developer", "product manager", "vp" ],
    "competences": [ "proactivity", "leadership" ]
  },

  "employment_type": "FT",
  "employment_type_legal": "PJ"
}
```