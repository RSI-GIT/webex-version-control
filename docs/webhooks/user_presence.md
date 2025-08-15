# User Presence

This webhook will be checking the status every 3 seconds. Depending on the user status and status message, it will send data. If no changes happen, no data will be sent.

## Sample Payloads

### Do Not Disturb

```json
{
  "body": {
    "payload": "user-presence",
    "items": [
      {
        "id": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE",
        "status": "DoNotDisturb",
        "statusMessage": "test update dnd 2",
        "lastActivity": "2025-08-15T16:42:27.199Z",
        "lastModified": "2025-06-05T13:24:42.790Z"
      }
    ],
    "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
    "timestamp": "2025-08-15T16:42:29.315Z"
  },
  "method": "POST",
  "url": "/webhook"
}
```

### Active

```json
{
  "body": {
    "payload": "user-presence",
    "items": [
      {
        "id": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE",
        "status": "active",
        "statusMessage": "test update 2",
        "lastActivity": "2025-08-15T16:42:36.772Z",
        "lastModified": "2025-06-05T13:24:42.790Z"
      }
    ],
    "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
    "timestamp": "2025-08-15T16:42:40.184Z"
  },
  "method": "POST",
  "url": "/webhook"
}
```

### Unknown

```json
{
  "body": {
    "payload": "user-presence",
    "items": [
      {
        "id": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE",
        "status": "unknown",
        "statusMessage": "Busy",
        "lastActivity": "2025-08-15T16:43:04.836Z",
        "lastModified": "2025-06-05T13:24:42.790Z"
      }
    ],
    "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
    "timestamp": "2025-08-15T16:43:06.295Z"
  },
  "method": "POST",
  "url": "/webhook"
}
```

### Away | Out of Office

```json
{
  "body": {
    "payload": "user-presence",
    "items": [
      {
        "id": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE",
        "status": "OutOfOffice",
        "statusMessage": "Out of office",
        "lastActivity": "2025-08-15T16:43:19.636Z",
        "lastModified": "2025-06-05T13:24:42.790Z"
      }
    ],
    "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
    "timestamp": "2025-08-15T16:48:06.602Z"
  },
  "method": "POST",
  "url": "/webhook"
}
```

### On Call

```json
{
  "body": {
    "payload": "user-presence",
    "items": [
      {
        "id": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE",
        "status": "call",
        "statusMessage": "",
        "lastActivity": "2025-08-15T16:49:53.758Z",
        "lastModified": "2025-06-05T13:24:42.790Z"
      }
    ],
    "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
    "timestamp": "2025-08-15T16:49:57.123Z"
  },
  "method": "POST",
  "url": "/webhook"
}
```
