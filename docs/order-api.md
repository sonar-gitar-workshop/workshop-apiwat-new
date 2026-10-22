# Order API contract

## Create an order

`POST /orders` accepts an `items` array. Each item contains a `sku` and `quantity`.

A successful response uses HTTP 201 and contains:

- `id`: Internal order identifier.
- `reference`: Customer-facing order reference in the form `ORDER-` followed by the order ID padded to six digits (for example, `ORDER-000001`).
- `items`: Priced order line items.
- `total_cents`: Total order price in cents.

## Get an order

`GET /orders/<order_id>` returns the stored order using the same response fields. An unknown order returns HTTP 404.

## Get a product

`GET /products/<sku>` returns `sku`, `name`, and `price_cents`. An unknown product returns HTTP 404.
