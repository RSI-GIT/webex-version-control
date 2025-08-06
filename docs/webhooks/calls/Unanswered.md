# Unanswered Call

This hook is triggered when a call is not answered by an agent.

## Example Payload

```json
{
  "TalkTime": 0,
  "CallDir": "inbound",
  "TotalDuration": 0,
  "RingTime": 0,
  "Answered": false,
  "Events": [
    {
      "data": {
        "callId": "Y2lzY29zcGFyazovL3VzL0NBTEwvY2FsbGhhbGYtOTYwNjk0ODQwODow",
        "appearance": 1,
        "personality": "terminator",
        "created": "2025-08-05T17:47:22.677Z",
        "remoteParty": {
          "name": "POUYA SHAHRDAMI",
          "privacyEnabled": false,
          "number": "+19059227700",
          "callType": "external"
        },
        "muteCapable": false,
        "eventType": "received",
        "state": "alerting",
        "callSessionId": "ZjhkMmY3MGQtMzgwZS00NDAxLWE0OTEtMGM2OGYwODk4OTE5",
        "muted": false,
        "eventTimestamp": "2025-08-05T17:47:22.678Z",
        "completedElsewhere": false
      },
      "resource": "telephony_calls",
      "created": "2025-07-01T13:31:06.813Z",
      "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
      "actorId": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE",
      "createdBy": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE",
      "appId": "Y2lzY29zcGFyazovL3VzL0FQUExJQ0FUSU9OL0MzZjU0MjYwYTQyMjhjY2NlNWY4YjM3NDVlYjYzMDA0MDYzYjVlZTgzOWRlNDE4YjMyOGFkMGMxZTA5MjAzYzgx",
      "name": "WebexSAPROD",
      "id": "Y2lzY29zcGFyazovL3VzL1dFQkhPT0svYTkzZDliMTItM2YyNC00YzM1LTljYWYtMjFmMjMzZGUyMzNj",
      "event": "created",
      "targetUrl": "https://f8c2wc8446.execute-api.us-east-1.amazonaws.com/telephony",
      "ownedBy": "creator",
      "status": "active"
    },
    {
      "data": {
        "callId": "Y2lzY29zcGFyazovL3VzL0NBTEwvY2FsbGhhbGYtOTYwNjk0ODQwODow",
        "endpointType": "APPLICATION",
        "created": "2025-08-05T17:47:22.677Z",
        "endpointId": "Y2lzY29zcGFyazovL3VzL0FQUExJQ0FUSU9OLzAzNWVlYTFlLTY4ZmEtNDkyNS1iNWM2LWM2MzUwZmUwMzA3OA",
        "eventType": "updated",
        "callSessionId": "ZjhkMmY3MGQtMzgwZS00NDAxLWE0OTEtMGM2OGYwODk4OTE5",
        "completedElsewhere": false,
        "appearance": 1,
        "personality": "terminator",
        "remoteParty": {
          "name": "POUYA SHAHRDAMI",
          "privacyEnabled": false,
          "number": "+19059227700",
          "callType": "external"
        },
        "muteCapable": false,
        "state": "alerting",
        "muted": false,
        "eventTimestamp": "2025-08-05T17:47:22.678Z"
      },
      "resource": "telephony_calls",
      "created": "2025-07-01T13:31:06.813Z",
      "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
      "actorId": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE",
      "createdBy": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE",
      "appId": "Y2lzY29zcGFyazovL3VzL0FQUExJQ0FUSU9OL0MzZjU0MjYwYTQyMjhjY2NlNWY4YjM3NDVlYjYzMDA0MDYzYjVlZTgzOWRlNDE4YjMyOGFkMGMxZTA5MjAzYzgx",
      "name": "WebexSAPROD",
      "id": "Y2lzY29zcGFyazovL3VzL1dFQkhPT0svYTkzZDliMTItM2YyNC00YzM1LTljYWYtMjFmMjMzZGUyMzNj",
      "event": "updated",
      "targetUrl": "https://f8c2wc8446.execute-api.us-east-1.amazonaws.com/telephony",
      "ownedBy": "creator",
      "status": "active"
    }
  ],
  "Dead": false,
  "QueueCall": false,
  "SortKey": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE#ZjhkMmY3MGQtMzgwZS00NDAxLWE0OTEtMGM2OGYwODk4OTE5",
  "CallType": "external",
  "CallStatus": "alerting",
  "PartnerNumber": "+19059227700",
  "Partner": "POUYA SHAHRDAMI",
  "Queue": "",
  "CallVersion": 1,
  "DidRing": true,
  "PartitionKey": "HookCalls#Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
  "DateCreated": "2025-08-05T17:47:22.678Z"
}
```

## Flow

1.  Call enters the queue.
2.  No agent becomes available within the timeout period.
3.  The call is terminated.
4.  The `unanswered_call` hook is triggered.
