# Besu privacy groups test

Example of a [Besu](https://besu.hyperledger.org/en/stable/) node with privacy features enabled using [Orion](https://docs.orion.pegasys.tech/en/stable/)

## Starting the services

Simply run `docker-compose up`. The Besu node rpc server will start at `http://localhost:28545`

## Creating a privacy group

Send a `POST` http request to `http://localhost:28545` with the following body

```json
{
  "jsonrpc": "2.0",
  "method": "priv_createPrivacyGroup",
  "params": [
    {
      "addresses": [
        "dpeuo81OCIkC2y6kRhBP4GcTVpfyzkQ+n+WbqG+qMEM="
      ],
      "name": "Group A",
      "description": "Description Group A"
    }
  ],
  "id": 1
}
```

Notice that the `addresses` array must include the public key stored in `data/orion/testKey.pub`.

This will return something like

```json
{
  "jsonrpc": "2.0",
  "id": 1,
  "result": "DpJSUfN7kRhwBlyG/L9ngMoTUZ+j9GraZycXG8cjs9U="
}
```
