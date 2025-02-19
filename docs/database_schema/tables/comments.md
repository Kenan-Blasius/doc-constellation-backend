# Comments Table

The Comments table stores information about the comments made by users on constellations and files. It contains the following columns:

- `uuid`: The unique identifier for each comment.
- `content`: The content of the comment.
- `creator_uuid`: The unique identifier of the user who made the comment.
- `created_at`: The timestamp when the comment was made.
- `file_uuid`: The unique identifier of the file on which the comment was made.
- `parent_uuid`: The unique identifier of the comment parent (if it is a reply).

## Columns

### uuid
- **Type**: UUID
- **Description**: The unique identifier for each comment.

### content
- **Type**: Text
- **Description**: The content of the comment.

### creator_uuid
- **Type**: UUID
- **Description**: The unique identifier of the user who made the comment.

### created_at
- **Type**: Timestamp
- **Description**: The timestamp when the comment was made.

### file_uuid
- **Type**: UUID
- **Description**: The unique identifier of the file on which the comment was made.

### parent_uuid
- **Type**: UUID
- **Description**: The unique identifier of the comment parent (if it is a reply).

## Relationships

- **creator_uuid**: Foreign key referencing the `uuid` column in the `Users` table.
- **file_uuid**: Foreign key referencing the `uuid` column in the `Files` table.
- **parent_uuid**: Foreign key referencing the `uuid` column in the `Comments` table (if it is a reply).

## Indexes

- **Primary Key**: `uuid`
- **Foreign Key**: `creator_uuid` references `Users(uuid)`
- **Foreign Key**: `file_uuid` references `Files(uuid)`
- **Foreign Key**: `parent_uuid` references `Comments(uuid)`

This table is used to store metadata about comments made by users, including the user who made the comment, the file on which the comment was made, and any parent comment if it is a reply.