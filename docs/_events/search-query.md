# Search and Query Operations

With Tigris, you can query and search events the same way you are used to
querying and searching data in a standard database.

:::info Automatic indexing of event data enabling powerful query and search capability

Tigris automatically indexes the event data in topics and provides
rich query and search capability out-of-the-box. This differentiates Tigris
from other event streaming systems such as Kafka.

:::

## Query Operations

Query operations retrieve events from a topic. Tigris by default
indexes all the fields of the event allowing you to retrieve data by
applying filters on any of the fields.

![Query](/img/findmany.jpg)

Query operations support the following features:

- **Exact Matches**: Perform equality match on any field
- **Range Queries**: Do range queries on any numeric field. Tigris also
  enables, by default, range queries on created or updated at timestamp of the
  event
- **Nested fields**: Query on nested fields
- **Projection**: Include or exclude the fields that are not needed in the result
- **Pagination**: Paginate the results through the use of _limit_ and _offset_

Tigris TypeScript SDK provides the following two APIs to query events in a
topic:

- [findOne()](docs/typescript/_events/query#simple-read-query): query for a single
  event
- [findMany()](docs/typescript/_events/query#filtering-on-multiple-fields): query for
  multiple events based on some filtering condition

See the language-specific sections for more examples of Read operations:

- [Query in TypeScript](docs/typescript/_events/query)
- [Query in Go](docs/golang/_events/query)
- [Query in Java](../java/query)

## Search Operations

Search operations support the following features:

- **Full-text search**: Ability to perform full-text search queries on the
  topic
- **Faceted search**: Ability to perform facet query to aggregate search
  results by fields.
- **Searching on nested fields**: Ability to perform search on nested fields in
  the event
- **Projection**: Ability to include or exclude fields that are not needed in
  the result

Tigris TypeScript SDK provides the following API to search for events
in a topic:

- [search()](docs/typescript/_events/search#searching-for-documents): search for one
  or more events in a topic

See the language-specific sections for more examples of Search operations:

- [Search in TypeScript](docs/typescript/_events/search)
- [Search in Go](docs/golang/_events/search)
- [Search in Java](../java/search)

## Filters

The search and query operations allow specifying filters on any of the fields.

Filters support the following comparison operators:

- **EQ**: equal to is used for exact matching
- **LT**: less than is used for matching documents using less than criteria
- **LTE**: less than or equal to is similar to **LT** but also matches for
  equality
- **GT**: greater than is used for matching documents using greater than
  criteria
- **GTE**: greater than or equal to is similar to **GT** but also matches
  for equality

For multiple conditions, there are two logical operators provided:

- **OR**: Combines multiple filter operators and returns documents when
  either condition is met
- **AND**: Combines multiple filter operators and returns documents when all
  the conditions are met
