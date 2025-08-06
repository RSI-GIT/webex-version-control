# Webex Presence Webhook Integration Guide

## Overview

The webhook sends a POST request to a pre-configured URL whenever a change in user presence is detected. This allows external services to stay synchronized with Webex user statuses.

## Payload Format

The webhook payload is sent as a JSON object in the body of the POST request.

### Headers

The following HTTP headers are included in the request:

| Header         | Description                       |
| -------------- | --------------------------------- |
| `Content-Type` | `application/json`                |
| `x-org-id`     | The ID of the Webex organization. |

### Body

The body of the request contains the presence information.

**Example Body:**

```json
{
  "payload": "user-presence",
  "items": [
    {
      "id": "abc123",
      "emails": ["john@example.com"],
      "sipAddresses": [
        {
          "type": "cloud",
          "value": "sip:john@example.com",
          "primary": true
        }
      ],
      "displayName": "John Doe",
      "nickName": "Johnny",
      "firstName": "John",
      "lastName": "Doe",
      "orgId": "org-12345",
      "status": "active",
      "lastModified": "2025-06-30T10:05:00Z",
      "lastActivity": "2025-06-30T10:10:00Z",
      "type": "person",
      "department": "Engineering"
    }
  ]
}
```

### Body Field Descriptions

| Field          | Type     | Description                                                              |
| -------------- | -------- | ------------------------------------------------------------------------ |
| `payload`      | `string` | Always `user-presence` for this webhook.                                 |
| `items`        | `array`  | A list of user presence objects that have changed.                       |
| `id`           | `string` |                                                                          |
| `emails`       | `array`  |                                                                          |
| `sipAddresses` | `array`  |                                                                          |
| `displayName`  | `string` |                                                                          |
| `nickName`     | `string` |                                                                          |
| `firstName`    | `string` |                                                                          |
| `lastName`     | `string` |                                                                          |
| `orgId`        | `string` | The ID of the organization the user belongs to.                          |
| `status`       | `string` | The user's presence status (e.g., `active`, `inactive`, `DoNotDisturb`). |
| `lastModified` | `string` | The timestamp of the last modification to the user's profile.            |
| `lastActivity` | `string` | The timestamp of the user's last activity.                               |
| `type`         | `string` | The type of object, typically `person`.                                  |
| `department`   | `string` |                                                                          |

## Update Frequency

- The webhook is triggered approximately **every 2 seconds**.
- A notification is sent **only if** there has been a change in any user's presence since the last successful update.
- The change detection mechanism relies on a combination of Webex APIs and a diffing process against a DynamoDB database that stores the last known presence states.
