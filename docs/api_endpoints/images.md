# Images API

This document provides detailed information about the image-related API endpoints available in the Constellation project.

## List All Images

### GET `/images`
Retrieve a list of all images.

**Response:**
- `200 OK`: Returns a list of images.

**Response Example**
```json
{
  "images": [
    {
      "image_uuid": "0000-000000...",
      "name": "string",
      "url": "string"
    }
  ]
}
```

## Upload a New Image

### POST `/images`
Upload a new image.

**Request Body:**
```json
{
  "name": "string",
  "file": "binary"
}
```

**Response:**
- `201 Created`: Image successfully uploaded.
- `400 Bad Request`: Invalid input data.

**Response Example**
```json
{
  "image_uuid": "0000-000000...",
  "name": "string",
  "url": "string"
}
```

## Get an Image

### GET `/images/{image_uuid}`
Retrieve an image by its ID.

**Request Parameters:**
- `image_uuid` (path): The unique identifier of the image.

**Response:**
- `200 OK`: Returns image details.
- `404 Not Found`: Image not found.

**Response Example**
```json
{
  "image_uuid": "0000-000000...",
  "name": "string",
  "url": "string"
}
```

## Rename an Image

### PATCH `/images/{image_uuid}`
Rename an image.

**Request Parameters:**
- `image_uuid` (path): The unique identifier of the image.

**Request Body:**
```json
{
  "name": "string"
}
```

**Response:**
- `200 OK`: Image name successfully updated.
- `400 Bad Request`: Invalid input data.
- `404 Not Found`: Image not found.

**Response Example**
```json
{
  "image_uuid": "0000-000000...",
  "name": "string",
  "url": "string"
}
```

## Delete an Image

### DELETE `/images/{image_uuid}`
Delete an image.

**Request Parameters:**
- `image_uuid` (path): The unique identifier of the image.

**Response:**
- `200 OK`: Image successfully deleted.
- `404 Not Found`: Image not found.

**Response Example**
```json
{
  "message": "Image deleted"
}
```
