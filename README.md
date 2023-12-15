# Quotes CRUD APP with Rust

Simple application showcasing buiding a CRUD app using Rust.

```shell
docker build -t crud-app .
docker run -p 3000:3000 crud-app
```

```shell
cargo install sqlx-cli

sqlx migrate add "initial database setup"

sqlx migrate run
```

## Create

```shell
curl -sS \
     -H 'Content-Type: application/json' \
     -X POST \
     -d '{"book":"A Game of Thrones", "quote":"Fear cuts deeper than swords"}' \
     https://rust-quotes-dev-bbdd.1.ie-1.fl0.io/quotes | jq

curl -sS \
     -H 'Content-Type: application/json' \
     -X POST \
     -d '{"book":"The Lord of the Rings", "quote":"The dark fire will not avail you"}' \
     https://rust-quotes-dev-bbdd.1.ie-1.fl0.io/quotes | jq

curl -sS \
     -H 'Content-Type: application/json' \
     -X POST \
     -d '{"book":"The Whhel", "quote":"String"}' \
     https://rust-quotes-dev-bbdd.1.ie-1.fl0.io/quotes | jq
```

## Read

```shell
curl https://rust-quotes-dev-bbdd.1.ie-1.fl0.io/quotes | jq
```

## Update

```shell
curl -sS \
     -H 'Content-Type: application/json' \
     -X PUT \
     -d '{"book":"The Wheel of Time", "quote":"Hope is like a piece of string"}' \
     https://rust-quotes-dev-bbdd.1.ie-1.fl0.io/quotes/498c3f64-308a/44b-b31c-b676f63f88d5
```

## Delete

```shell
curl -X DELETE https://rust-quotes-dev-bbdd.1.ie-1.fl0.io/quotes/498c3f64-308a/44b-b31c-b676f63f88d5 -v
```

Testing404:

```shell
uuidgen
9109D71D-1A52-4F50-B3EE-9CDCB20265C7
curl -X DELETE https://rust-quotes-dev-bbdd.1.ie-1.fl0.io/quotes/9109D71D-1A52-4F50-B3EE-9CDCB20265C7 -v
```
