# Debug API

This document provides detailed information about the debug-related API endpoints available in the Constellation project.
All the debug endpoints are used for testing and debugging purposes only, and are available only in the development environment.
As it's debug-related, it doesn't require authentication.

## Get all nodes

### GET `/nodes`

**Response:**

- `200 OK`: Returns all nodes in the database.
- `500 Internal Server Error`: An error occurred while retrieving nodes.

**Response Example:**

```json
{
  "success": true,
  "data": [
    {
      "attributes": {
        "node_uuid": 1,
        "title": "example_title",
        "content": "example_content"
      },
      "labels": [
        "Node"
      ]
    }
  ],
  "message": "Nodes retrieved"
}
```

## Get all links

### GET `/links`

**Response:**

- `200 OK`: Returns all links in the database.
- `500 Internal Server Error`: An error occurred while retrieving links.

**Response Example:**

```json
{
  "success": true,
  "data": [
    {
      "start_node": 1,
      "end_node": 2,
      "type": "example_type",
      "attributes": {
        "link_uuid": 1
      }
    }
  ],
  "message": "Links retrieved"
}
```

## Reset the database

### GET `/reset`

**Response:**

- `200 OK`: Returns all links in the database.
- `500 Internal Server Error`: An error occurred while resetting the database.

**Response Example:**

```json
{
  "success": true,
  "message": "Database reset"
}
```

## Populate the database

### GET `/populate`

**Response:**

- `200 OK`: Returns all links in the database.
- `404 Not Found`: The populate cypher file was not found.
- `500 Internal Server Error`: An error occurred while populating the database.

**Response Example:**

```json
{
  "success": true,
  "message": "Database populated"
}
```

or

```json
{
  "success": false,
  "message": "Cypher file not found",
  "error": {
    "code": "FILE_NOT_FOUND",
    "message": "Cypher file not found"
  }
}
```
