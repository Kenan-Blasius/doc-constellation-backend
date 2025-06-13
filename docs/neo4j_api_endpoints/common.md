# Node API

This document provides detailed information about the nodes-related API endpoints available in the Constellation project.

## Base

### Search for nodes and links

#### GET `/constellation/{constellation_uuid}/search`

**Description:**

Search for nodes and links in a constellation.

**Request Parameters:**

- `constellation_uuid` (path): The unique identifier of the constellation.
- `search` (query): The search term to find nodes and links.
- `in_filter` (query, optional): A filter to include only specific attributes in the final results
- `out_filter` (query, optional): A filter to exclude specific attributes from the final results

**Response:**

- `200 OK`: Returns matching nodes and links.
- `401 Unauthorized`: User not authorized.
- `403 Forbidden`: User does not have permission to access the constellation.
- `404 Not Found`: Constellation not found.
- `500 Internal Server Error`: An error occurred while retrieving links.

**Response Example:**

```json
{
    "success": true,
    "data": {
        "nodes":
            [
                {
                    "attributes": {
                        "node_uuid": "0000-000000...",
                        "title": "example_title",
                        "content": "example_content"
                    },
                    "labels": [
                        "Node"
                    ]
                }
            ],
        "links":
            [
                {
                    "start_node": "0000-000000...",
                    "end_node": "0000-000000...",
                    "link_type": "string",
                    "attributes": {
                        "link_uuid": "0000-000000...",
                        "title": "example_link_title",
                        "content": "example_link_content"
                    }
                }
            ]
        },
    "message": "All matching nodes and links successfully returned"
}
```
