# Queue Monitor Events

---

## Purpose

This webhook provides real-time notifications when an agent joins or leaves a queue in Webex.

## Endpoint

The system sends HTTP POST requests to the configured webhook URL.

- **Content-Type:** `application/json`
- **Header:** `x-org-id: <Organization ID>`

---

## Payload Structure

The payload contains the following fields:

- `payload`: A static identifier, always set to `queue-monitor`.
- `timestamp`: The ISO 8601 UTC timestamp indicating when the event was generated.
- `items`: An object containing the users and their queue status changes.

### Items Object

- `userId` (string): The ID of the agent.
- `queueId` (string): The ID of the queue.
- `status` (string): The agent's new status in the queue. Can be either `'active'` or `'inactive'`.

---

## Field Descriptions

| Field       | Type     | Description                                          |
| :---------- | :------- | :--------------------------------------------------- |
| `payload`   | `string` | Always `"queue-monitor"` — indicates the event type. |
| `timestamp` | `string` | UTC timestamp of when the event was generated.       |
| `items`     | `object` | A map of `userId` to their queue changes.            |

---

## Received Payload Examples

### Agent Joins a Queue

```json
{
  "payload": "queue-monitor",
  "timestamp": "2025-07-23T18:53:26.298Z",
  "items": {
    "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9a...": {
      "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNm...": "active"
    }
  }
}
```

### Agent Leaves a Queue

```json
{
  "payload": "queue-monitor",
  "timestamp": "2025-07-23T19:02:11.551Z",
  "items": {
    "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9a...": {
      "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNT...": "inactive"
    }
  }
}
```

### Multiple Agents in One Payload

If changes for multiple users happen simultaneously, they can appear in the same payload:

```json
{
  "payload": "queue-monitor",
  "timestamp": "2025-07-23T19:05:00.000Z",
  "items": {
    "<userId1>": {
      "<queueId>": "active"
    },
    "<userId2>": {
      "<queueId>": "inactive"
    }
  }
}
```

**Note:** If no changes are detected during a polling cycle, no webhook will be sent.
