# Status Message API Documentation

## Overview

This API endpoint allows you to update status messages for different user statuses. It stores status messages for later use when users change their status, acting as a "memory" system for status messages.

**Important Note**: This endpoint only updates the stored message for a specific status type. It does NOT change the user's current active status.

## Endpoint

```
POST /status-message
```

## Authentication

This endpoint requires proper authorization headers. The user's `orgId` and `userId` will be extracted from the authorization context.

## Request Format

### Headers

```
Content-Type: application/json
Authorization: [Your authorization token]
```

### Request Body

```json
{
  "status": "avl",
  "statusMessage": "Available for urgent matters only"
}
```

### Parameters

| Parameter       | Type   | Required | Description                                    |
| --------------- | ------ | -------- | ---------------------------------------------- |
| `status`        | string | Yes      | The status type for which to store the message |
| `statusMessage` | string | Yes      | The message to associate with this status      |

## Allowed Status Values

The following status values are accepted:

```javascript
["avl", "dnd", "busy", "oof"];
```

| Status | Description    |
| ------ | -------------- |
| `avl`  | Available      |
| `dnd`  | Do Not Disturb |
| `busy` | Busy           |
| `oof`  | Out of Office  |

## Response Format

### Success Response (200)

```json
{
  "message": "Status updated successfully",
  "userId": "user123",
  "status": "avl",
  "statusMessage": "Available for urgent matters only"
}
```

### Status Unchanged Response (200)

```json
{
  "message": "Status message for 'avl' unchanged",
  "userId": "user123",
  "status": "avl",
  "statusMessage": "Available for urgent matters only"
}
```

### Error Responses

#### Missing Status Message (400)

```json
{
  "message": "Status is required",
  "error": "MISSING_STATUS"
}
```

#### Invalid Status (400)

```json
{
  "message": "Valid status is required",
  "validStatuses": ["avl", "dnd", "busy", "oof"],
  "receivedStatus": "invalid_status"
}
```

#### Invalid JSON (400)

```json
{
  "message": "Invalid JSON in request body",
  "error": "INVALID_JSON"
}
```

#### Server Error (500)

```json
{
  "message": "Internal Server Error",
  "error": "INTERNAL_ERROR"
}
```

## Important Notes

1. **Duplicate Prevention**: If the same status message is sent for a status that already has that exact message, no update occurs and a "unchanged" response is returned.

2. **Trimming**: Status messages are automatically trimmed of leading/trailing whitespace.

3. **Timestamps**: When a status message is updated, the following timestamps are automatically set:
   - `lastSMChanged`
   - `lastActivity`
   - `lastModified`
