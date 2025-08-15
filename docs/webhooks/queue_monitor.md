# Queue Monitor

This webhook will check the queue status and show the status of the queue if changes happen.

This webhook monitors queue status and reports any changes.

#### It can display more than one queue status at a time.

#### It can also show multiple users’ queue statuses if they trigger updates simultaneously.

## Sample Payload

```json
{
  "payload": "queue-monitor",
  "timestamp": "2025-07-23T18:53:26.298Z",
  "items": {
    "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9a...": {
      // user id
      "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNm...": "active" // queue id
    }
  }
}
```
