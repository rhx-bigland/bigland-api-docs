# bigland-api-docs

Public bigland api integration for tests and third party services

This guide is intended to be the startup point for third party integrations to the Bigland platform.

The flow is a simple yet malleable process, which allows to multiple services, with different needs, a easy integration to the tests marketplace platform.

## Integration flow

##### Setup

1. Application signup on the bigland platform (contact us at is@bigland.co)
2. Security configurations (cors domains and private keys)

##### Tests requests

```
+---------------+                         +---------------+
|               |                         |               |
|               |                         |               |
|    Bigland    +---------+ GET +----------> Third party  |
|       +      <--------------------------+               |
|       |       |    tests available      |               |
|       |       |                         |               |
|       v       |                         |               |
|    Test       |                         |               |
|    request    +---------+ POST +---------> Integration  |
|               |    request_token        |       +       |
|               |    test_id              |       |       |
|               |    job_id               |       |       |
|               |                         |       v       |
|     /job     <------+ Optional GET +----+   Read job    |
|               +-------------------------->  details     |
|               |    job data             |       +       |
|               |    title, area, desc..  |       |       |
|               |                         |       |       |
|               |                         |       v       |
|   /contact   <------+ Optional GET +----+  Read contact |
|               +-------------------------->  details     |
|               |    contact details      |       +       |
|               |    skills, gender, age  |       |       |
|               |                         |       |       |
|               |                         |       v       |
|     /test    <------+ Optional GET +----+   Read test   |
|               +-------------------------->  details     |
|               |    candidates           |       +       |
|               |    templates            |       |       |     +
|               |    third party tests    |       |       |     |
|               |                         |       v       |     |
|               |                         |   Dispatch +------> |
|               |                         |       +       |     |
|               |                         |       |       |     |
|               |                         |       |       |     |
|               |                         |       v       |     |
|   /results   <----------+ POST +--------+    Results <------+ |
|               |    test scores          |               |     |
|               |    documents, links..   |               |     |
+---------------+                         +---------------+     +
```

1. Bigland -> Get tests vailable -> Third party tests available
2. Bigland -> Request test dispatch -> Third party ack
3. [optional] Third party -> Get job details -> Bigland job details
4. [optional] Third party -> Get candidates details -> Bigland candidates details
4. Third party -> Get test details -> Bigland test details and candidates
5. Third party -> Post test results -> Bigland ack

## Endpoints

| Environment | **Endpoint base** |
| ----------- | ----------------- |
| Live        | https://api.bigland.co/i/a |
| Staging     | https://apistaging.bigland.co/i/a |

All integration requests must be done to the given *endpoint base path*.

All requests must be sent from the defined third party domain

### Security

All the requests sent from the third party must be done with an `Authorization` header

The header is of the format `Authorization=Bearer {authorization_token}`

The `authorization_token` is the sha256 hash result from the `request_token` updated with the third party application `private_token`.

-----
##### `QUERY ~ /job`

| Query job details | Request |
| ----------------- | ------- |
| Method            | `GET` |
| Endpoint          | `/job` |
| Payload           | [Payload](/job#payload) |
| Response          | [Response](/job#response) |


-----
##### `QUERY ~ /test`

| Query test details | Request |
| ------------------ | ------- |
| Method             | `GET` |
| Endpoint           | `/test` |
| Payload            | [Payload](/test#payload) |
| Response           | [Response](/test#response) |


-----
##### `QUERY ~ /contact`

| Query contact details | Request |
| --------------------- | ------- |
| Method                | `GET` |
| Endpoint              | `/contact` |
| Payload               | [Payload](/contact#payload) |
| Response              | [Response](/contact#response) |


-----
##### `POST ~ /results`

| Post test results | Request |
| ----------------- | ------- |
| Method            | `POST` |
| Endpoint          | `/results` |
| Payload           | [Payload](/result#payload) |
| Response          | [Response](/result#response) |
