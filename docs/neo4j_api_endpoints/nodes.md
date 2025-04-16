# Node API

This document provides detailed information about the nodes-related API endpoints available in the Constellation project.

## Base

### Get all nodes

#### GET `/constellation/{constellation_uuid}/nodes`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

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
  "message": "All nodes successfully returned"
}
```

### Get a node by UUID

#### GET `/constellation/{constellation_uuid}/node/{node_uuid}`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.
- `node_uuid` (path): The unique identifier of the node.

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

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
  "message": "Node retrieved successfully"
}
```

### Update a node

#### PATCH `/constellation/{constellation_uuid}/node/{node_uuid}`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.
- `node_uuid` (path): The unique identifier of the node.

**Request Body:**

```json
{
  "title": "example_title",
  "content": "example_content",
  "example_attribute": "example_value"
}
```

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

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
  "message": "Node updated successfully"
}
```

### Delete a node

#### DELETE `/constellation/{constellation_uuid}/node/{node_uuid}`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.
- `node_uuid` (path): The unique identifier of the node.

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

**Response Example:**

```json
{
  "success": true,
  "message": "Node deleted successfully"
}
```

### Create a new node

#### POST `/constellation/{constellation_uuid}/node`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.

**Request Body:**

```json
{
  "title": "example_title",
  "content": "example_content",
  "example_attribute": "example_value"
}
```

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

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
  "message": "Node created successfully"
}
```

## Attributes

### Get all attributes in the constellation

#### GET `/constellation/{constellation_uuid}/attributes`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

**Response Example:**

```json
{
  "success": true,
  "data": [
    "attribute1",
    "attribute2",
    "attribute3"
  ],
  "message": "Attributes retrieved"
}
```

### Get all attributes of a node

#### GET `/constellation/{constellation_uuid}/node/{node_uuid}/attributes`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.
- `node_uuid` (path): The unique identifier of the node.

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

**Response Example:**

```json
{
  "success": true,
  "data": [
    "attribute1",
    "attribute2",
    "attribute3"
  ],
  "message": "Attributes retrieved"
}
```

### Get the value of a specific attribute of a node

#### GET `/constellation/{constellation_uuid}/node/{node_uuid}/attribute/{attribute}`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.
- `node_uuid` (path): The unique identifier of the node.
- `attribute` (path): The name of the attribute.

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

**Response Example:**

```json
{
  "success": true,
  "data": [
    "value"
  ],
  "message": "Attribute retrieved"
}
```

### Set the value of a specific attribute of a node

#### PATCH `/constellation/{constellation_uuid}/node/{node_uuid}/attribute/{attribute}`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.
- `node_uuid` (path): The unique identifier of the node.
- `attribute` (path): The name of the attribute.

**Request Body:**

- `value` (body): The value to set for the attribute.

```json
{
  "value": "example_value"
}
```

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

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
  "message": "Attribute updated"
}
```

### Delete a specific attribute of a node

#### DELETE `/constellation/{constellation_uuid}/node/{node_uuid}/attribute/{attribute}`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.
- `node_uuid` (path): The unique identifier of the node.
- `attribute` (path): The name of the attribute.

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

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
  "message": "Attribute deleted"
}
```

### Add an attribute to a node

#### POST `/constellation/{constellation_uuid}/node/{node_uuid}/attribute/{attribute}`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.
- `node_uuid` (path): The unique identifier of the node.
- `attribute` (path): The name of the attribute.

**Request Body:**

- `value` (body): The value to set for the attribute.

```json
{
  "value": "example_value"
}
```

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

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
  "message": "Attribute added"
}
```

### Get all nodes with a specific attribute

#### GET `/constellation/{constellation_uuid}/nodes/attribute/{attribute}`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.
- `attribute` (path): The name of the attribute.

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

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

## Labels

### Get all labels in the constellation

#### GET `/constellation/{constellation_uuid}/labels`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

**Response Example:**

```json
{
  "success": true,
  "data": [
    "Node",
    "Person",
    "Movie",
    "Book"
  ],
  "message": "Labels successfully retrieved"
}
```

### Get all labels of a node

#### GET `/constellation/{constellation_uuid}/node/{node_uuid}/labels`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.
- `node_uuid` (path): The unique identifier of the node.

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

**Response Example:**

```json
{
  "success": true,
  "data": [
    [
      "Node",
      "Person"
    ]
  ],
  "message": "Labels successfully retrieved"
}
```

### Remove all labels from a node

#### DELETE `/constellation/{constellation_uuid}/node/{node_uuid}/labels`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.
- `node_uuid` (path): The unique identifier of the node.

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

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
  "message": "All labels successfully removed"
}
```

### Get all nodes with a label

#### GET `/constellation/{constellation_uuid}/nodes/label/{label}`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.
- `label` (path): The name of the label.

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

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
  "message": "Nodes successfully retrieved"
}
```

### Add a label to a node

#### POST `/constellation/{constellation_uuid}/node/{node_uuid}/label/{label}`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.
- `node_uuid` (path): The unique identifier of the node.
- `label` (path): The name of the label to add.

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

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
  "message": "Label successfully added"
}
```

### Remove a label from a node

#### DELETE `/constellation/{constellation_uuid}/node/{node_uuid}/label/{label}`

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.
- `node_uuid` (path): The unique identifier of the node.
- `label` (path): The name of the label to delete.

**Response:**

- `200 OK`: Returns user details.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

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
  "message": "Label successfully removed"
}
```

<!--
Format Example:

## Get a User by ID

### GET `/users/{user_uuid}`
Retrieve a user by their ID.

**Request Parameters:**
- `user_uuid` (path): The unique identifier of the user.

**Response:**
- `200 OK`: Returns user details.
- `404 Not Found`: User not found.

**Response Example**
```json
{
    "uuid": "0000-000000...",
    "name": "string",
    "email": "string"
}
``` -->
