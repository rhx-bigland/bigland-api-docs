# bigland-api-docs

[< Voltar](/README.md)

### Test endpoint

Test details request. Contains informations about the tests requested, the candidates that should receive the test, and possibly templates and custom definitions.

* [Target](#target)
* [Payload](#payload)
* [Response](#response)

## Target

Method `GET`
Endpoint `/test`

## Payload

`https://{endpoint_base}/test?id={test_id}`

| Query parameter | Value | Example |
| --------------- | ----- | ------- |
| id              | `test_id` received from the test dispatch request | `?id=08ede4b6-d2ff-4972-b05b-fe545e41ff84` |

## Response

```
{
    "tests": [
        {
            "test_key": "third_party_test_id_1",
            "candidates": [
                {
                    "first_name": "Tiago",
                    "last_name": "Miranda",
                    "email": "tmiranda@rhx.com.br"
                }
            ]
        }
    ]
}
```
