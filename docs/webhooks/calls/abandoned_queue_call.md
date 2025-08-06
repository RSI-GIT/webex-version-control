# Abandoned Queue Call

This hook is triggered when a call is abandoned from the queue.

## Example Payload

```json
{
  "TalkTime": 0,
  "CallDir": "inbound",
  "TotalDuration": 2239,
  "RingTime": 2239,
  "Answered": false,
  "Events": [
    {
      "data": {
        "callId": "Y2lzY29zcGFyazovL3VzL0NBTEwvY2FsbGhhbGYtOTYwNjg4MjIxNjow",
        "created": "2025-08-05T17:44:52.284Z",
        "eventType": "received",
        "callSessionId": "ZWM1NmY0MDUtODU3My00MDkzLThkOTAtMjY2OWZmMjRjM2Iz",
        "completedElsewhere": false,
        "redirections": [
          {
            "reason": "callQueue",
            "redirectingParty": {
              "name": "CQX Q1",
              "privacyEnabled": false,
              "number": "+12895133479",
              "id": "Y2lzY29zcGFyazovL3VzL1VOS05PV04vNmRhZjY5MGQtYmMzNi00OTM3LWI4NWQtMmJmMGZjN2YzMWRi",
              "idType": "UNKNOWN",
              "callType": "location"
            }
          }
        ],
        "appearance": 1,
        "personality": "terminator",
        "remoteParty": {
          "name": "CQX Q1  -  POUYA SHAHRDAMI",
          "privacyEnabled": false,
          "number": "+19059227700",
          "callType": "external"
        },
        "muteCapable": false,
        "state": "alerting",
        "muted": false,
        "eventTimestamp": "2025-08-05T17:44:52.285Z"
      },
      "resource": "telephony_calls",
      "created": "2025-06-30T20:13:25.614Z",
      "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
      "actorId": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS84OWYwOGUyYi02MDM4LTQ3MmMtYjcyYy0zNjQyNjIwMThjNjE",
      "createdBy": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS84OWYwOGUyYi02MDM4LTQ3MmMtYjcyYy0zNjQyNjIwMThjNjE",
      "appId": "Y2lzY29zcGFyazovL3VzL0FQUExJQ0FUSU9OL0MzZjU0MjYwYTQyMjhjY2NlNWY4YjM3NDVlYjYzMDA0MDYzYjVlZTgzOWRlNDE4YjMyOGFkMGMxZTA5MjAzYzgx",
      "name": "WebexSAPROD",
      "id": "Y2lzY29zcGFyazovL3VzL1dFQkhPT0svN2QyMTBjMjUtYWJmZi00MjAxLWE0OGMtMjI3ZDRkNWY3OTI1",
      "event": "created",
      "targetUrl": "https://f8c2wc8446.execute-api.us-east-1.amazonaws.com/telephony",
      "ownedBy": "creator",
      "status": "active"
    },
    {
      "data": {
        "callId": "Y2lzY29zcGFyazovL3VzL0NBTEwvY2FsbGhhbGYtOTYwNjg4MjIxNjow",
        "endpointType": "APPLICATION",
        "created": "2025-08-05T17:44:52.284Z",
        "endpointId": "Y2lzY29zcGFyazovL3VzL0FQUExJQ0FUSU9OL2QyZmM1NDZkLTYxYzMtNDkwNC04YzFmLWY2ZTIzNTlhYzU3Yg",
        "eventType": "updated",
        "callSessionId": "ZWM1NmY0MDUtODU3My00MDkzLThkOTAtMjY2OWZmMjRjM2Iz",
        "completedElsewhere": false,
        "redirections": [
          {
            "reason": "callQueue",
            "redirectingParty": {
              "name": "CQX Q1",
              "privacyEnabled": false,
              "number": "+12895133479",
              "id": "Y2lzY29zcGFyazovL3VzL1VOS05PV04vNmRhZjY5MGQtYmMzNi00OTM3LWI4NWQtMmJmMGZjN2YzMWRi",
              "idType": "UNKNOWN",
              "callType": "location"
            }
          }
        ],
        "appearance": 1,
        "personality": "terminator",
        "remoteParty": {
          "name": "CQX Q1  -  POUYA SHAHRDAMI",
          "privacyEnabled": false,
          "number": "+19059227700",
          "callType": "external"
        },
        "muteCapable": false,
        "state": "alerting",
        "muted": false,
        "eventTimestamp": "2025-08-05T17:44:52.286Z"
      },
      "resource": "telephony_calls",
      "created": "2025-06-30T20:13:25.614Z",
      "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
      "actorId": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS84OWYwOGUyYi02MDM4LTQ3MmMtYjcyYy0zNjQyNjIwMThjNjE",
      "createdBy": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS84OWYwOGUyYi02MDM4LTQ3MmMtYjcyYy0zNjQyNjIwMThjNjE",
      "appId": "Y2lzY29zcGFyazovL3VzL0FQUExJQ0FUSU9OL0MzZjU0MjYwYTQyMjhjY2NlNWY4YjM3NDVlYjYzMDA0MDYzYjVlZTgzOWRlNDE4YjMyOGFkMGMxZTA5MjAzYzgx",
      "name": "WebexSAPROD",
      "id": "Y2lzY29zcGFyazovL3VzL1dFQkhPT0svN2QyMTBjMjUtYWJmZi00MjAxLWE0OGMtMjI3ZDRkNWY3OTI1",
      "event": "updated",
      "targetUrl": "https://f8c2wc8446.execute-api.us-east-1.amazonaws.com/telephony",
      "ownedBy": "creator",
      "status": "active"
    },
    {
      "data": {
        "callId": "Y2lzY29zcGFyazovL3VzL0NBTEwvY2FsbGhhbGYtOTYwNjg4MjIxNjow",
        "disconnected": "2025-08-05T17:44:54.524Z",
        "personality": "terminator",
        "created": "2025-08-05T17:44:52.284Z",
        "remoteParty": {
          "name": "POUYA SHAHRDAMI",
          "privacyEnabled": false,
          "number": "+19059227700",
          "callType": "external"
        },
        "muteCapable": false,
        "eventType": "disconnected",
        "state": "disconnected",
        "callSessionId": "ZWM1NmY0MDUtODU3My00MDkzLThkOTAtMjY2OWZmMjRjM2Iz",
        "muted": false,
        "eventTimestamp": "2025-08-05T17:44:54.524Z",
        "completedElsewhere": true
      },
      "resource": "telephony_calls",
      "created": "2025-06-30T20:13:25.614Z",
      "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
      "actorId": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS84OWYwOGUyYi02MDM4LTQ3MmMtYjcyYy0zNjQyNjIwMThjNjE",
      "createdBy": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS84OWYwOGUyYi02MDM4LTQ3MmMtYjcyYy0zNjQyNjIwMThjNjE",
      "appId": "Y2lzY29zcGFyazovL3VzL0FQUExJQ0FUSU9OL0MzZjU0MjYwYTQyMjhjY2NlNWY4YjM3NDVlYjYzMDA0MDYzYjVlZTgzOWRlNDE4YjMyOGFkMGMxZTA5MjAzYzgx",
      "name": "WebexSAPROD",
      "id": "Y2lzY29zcGFyazovL3VzL1dFQkhPT0svN2QyMTBjMjUtYWJmZi00MjAxLWE0OGMtMjI3ZDRkNWY3OTI1",
      "event": "deleted",
      "targetUrl": "https://f8c2wc8446.execute-api.us-east-1.amazonaws.com/telephony",
      "ownedBy": "creator",
      "status": "active"
    }
  ],
  "Dead": true,
  "QueueCall": true,
  "SortKey": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS84OWYwOGUyYi02MDM4LTQ3MmMtYjcyYy0zNjQyNjIwMThjNjE#ZWM1NmY0MDUtODU3My00MDkzLThkOTAtMjY2OWZmMjRjM2Iz",
  "CallType": "external",
  "CallStatus": "disconnected",
  "PartnerNumber": "+19059227700",
  "Partner": "POUYA SHAHRDAMI",
  "Queue": "CQX Q1",
  "CallVersion": 2,
  "DidRing": true,
  "PartitionKey": "HookCalls#Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
  "DateCreated": "2025-08-05T17:44:54.524Z"
}
```

## Flow

1.  Call enters the queue.
2.  Caller hangs up before being connected to an agent.
3.  The `abandoned_queue_call` hook is triggered.