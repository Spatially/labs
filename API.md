# Spatially API

Once you have created an account at [Spatially Labs](https://labs.spatially.com) you should be able to see your API code & key. Your API key is secret and make sure to store it in a secure place.

## Generate an access token

In order to generate an access token that can be used to access Spatially Labs services, you must first generate an access token, this is done by making an HTTP call to our API gateway with your API code and key.

Below is an example:

_Request_

```
POST https://api.spatially.com/gateway/client

Headers:
  Content-Type: application/json

Body:
  { "code": "{YOUR_APPLICATION_CODE}", "key": "{YOUR_APPLICATION_KEY}" }
```

_Response_

```json
{
  "token":
    "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzZXJ2aWNlcyI6WyJzcGF0aWFsZGIiLCJhZHMvc2NpZW5jZS9hdGEiXSwiYXV0aCI6ImFub24iLCJrZXkiOiI5MGEyOWI5OC1kYzVkLTQzNTktODkwMi1mZTVmZjZiNGIzN2IiLCJhdWQiOiJzZXJ2aWNlcy5nYXRld2F5LkF1dGhvcml6ZVVzZXIiLCJleHAiOjE1MjI5NjU3OTMsImlzcyI6InNlcnZpY2VzLmdhdGV3YXkuQXV0aG9yaXplQ2xpZW50Iiwic3ViIjoic3BhdGlhbGx5ZGIifQ.8iSWx7WH3Ejy-kz9sSlNzoVWg-PtnZfaPmWS0g8KPgI",
  "config": {}
}
```
