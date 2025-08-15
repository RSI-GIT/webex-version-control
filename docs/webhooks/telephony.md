# Telephony

This webhook provides real-time telephony details. It's raw data coming from Webex, and a normal call contains 3 stages: `created`, `updated`, and `deleted` by their events.

## Sample Payload

```json
[
  {
    "body": {
      "Payload": "telephony",
      "timestamp": "2025-08-14T18:53:03.419Z",
      "items": {
        "id": "Y2lzY29zcGFyazovL3VzL1dFQkhPT0svN2QyMTBjMjUtYWJmZi00MjAxLWE0OGMtMjI3ZDRkNWY3OTI1",
        "name": "WebexSAPROD",
        "targetUrl": "https://f8c2wc8446.execute-api.us-east-1.amazonaws.com/telephony",
        "resource": "telephony_calls",
        "event": "updated",
        "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
        "createdBy": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS84OWYwOGUyYi02MDM4LTQ3MmMtYjcyYy0zNjQyNjIwMThjNjE",
        "appId": "Y2lzY29zcGFyazovL3VzL0FQUExJQ0FUSU9OL0MzZjU0MjYwYTQyMjhjY2NlNWY4YjM3NDVlYjYzMDA0MDYzYjVlZTgzOWRlNDE4YjMyOGFkMGMxZTA5MjAzYzgx",
        "ownedBy": "creator",
        "status": "active",
        "created": "2025-06-30T20:13:25.614Z",
        "actorId": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS84OWYwOGUyYi02MDM4LTQ3MmMtYjcyYy0zNjQyNjIwMThjNjE",
        "data": {
          "eventType": "updated",
          "eventTimestamp": "2025-08-14T18:52:41.730Z",
          "callId": "Y2lzY29zcGFyazovL3VzL0NBTEwvY2FsbGhhbGYtOTgyNzEzMjM3MDow",
          "callSessionId": "MWFmMDFjNTQtOTdlMS00ODA3LWEzZjgtMTY2ODNiNjFhNjQw",
          "personality": "terminator",
          "state": "alerting",
          "muteCapable": false,
          "muted": false,
          "remoteParty": {
            "name": "CQX Q1  -  POUYA SHAHRDAMI",
            "number": "+19059227700",
            "privacyEnabled": false,
            "callType": "external"
          },
          "appearance": 1,
          "created": "2025-08-14T18:52:41.728Z",
          "redirections": [
            {
              "reason": "callQueue",
              "redirectingParty": {
                "name": "CQX Q1",
                "number": "+12895133479",
                "privacyEnabled": false,
                "callType": "location"
              }
            }
          ],
          "completedElsewhere": false
        }
      },
      "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ"
    },
    "method": "POST",
    "url": "/webhook"
  },
  {
    "body": {
      "Payload": "telephony",
      "timestamp": "2025-08-14T18:53:02.738Z",
      "items": {
        "id": "Y2lzY29zcGFyazovL3VzL1dFQkhPT0svN2QyMTBjMjUtYWJmZi00MjAxLWE0OGMtMjI3ZDRkNWY3OTI1",
        "name": "WebexSAPROD",
        "targetUrl": "https://f8c2wc8446.execute-api.us-east-1.amazonaws.com/telephony",
        "resource": "telephony_calls",
        "event": "created",
        "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
        "createdBy": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS84OWYwOGUyYi02MDM4LTQ3MmMtYjcyYy0zNjQyNjIwMThjNjE",
        "appId": "Y2lzY29zcGFyazovL3VzL0FQUExJQ0FUSU9OL0MzZjU0MjYwYTQyMjhjY2NlNWY4YjM3NDVlYjYzMDA0MDYzYjVlZTgzOWRlNDE4YjMyOGFkMGMxZTA5MjAzYzgx",
        "ownedBy": "creator",
        "status": "active",
        "created": "2025-06-30T20:13:25.614Z",
        "actorId": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS84OWYwOGUyYi02MDM4LTQ3MmMtYjcyYy0zNjQyNjIwMThjNjE",
        "data": {
          "eventType": "received",
          "eventTimestamp": "2025-08-14T18:52:41.729Z",
          "callId": "Y2lzY29zcGFyazovL3VzL0NBTEwvY2FsbGhhbGYtOTgyNzEzMjM3MDow",
          "callSessionId": "MWFmMDFjNTQtOTdlMS00ODA3LWEzZjgtMTY2ODNiNjFhNjQw",
          "personality": "terminator",
          "state": "alerting",
          "muteCapable": false,
          "muted": false,
          "remoteParty": {
            "name": "CQX Q1  -  POUYA SHAHRDAMI",
            "number": "+19059227700",
            "privacyEnabled": false,
            "callType": "external"
          },
          "appearance": 1,
          "created": "2025-08-14T18:52:41.728Z",
          "redirections": [
            {
              "reason": "callQueue",
              "redirectingParty": {
                "name": "CQX Q1",
                "number": "+12895133479",
                "privacyEnabled": false,
                "callType": "location"
              }
            }
          ],
          "completedElsewhere": false
        }
      },
      "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ"
    },
    "method": "POST",
    "url": "/webhook"
  }
  {
    "body": {
      "Payload": "telephony",
      "timestamp": "2025-08-14T18:53:04.091Z",
      "items": {
        "id": "Y2lzY29zcGFyazovL3VzL1dFQkhPT0svN2QyMTBjMjUtYWJmZi00MjAxLWE0OGMtMjI3ZDRkNWY3OTI1",
        "name": "WebexSAPROD",
        "targetUrl": "https://f8c2wc8446.execute-api.us-east-1.amazonaws.com/telephony",
        "resource": "telephony_calls",
        "event": "deleted",
        "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
        "createdBy": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS84OWYwOGUyYi02MDM4LTQ3MmMtYjcyYy0zNjQyNjIwMThjNjE",
        "appId": "Y2lzY29zcGFyazovL3VzL0FQUExJQ0FUSU9OL0MzZjU0MjYwYTQyMjhjY2NlNWY4YjM3NDVlYjYzMDA0MDYzYjVlZTgzOWRlNDE4YjMyOGFkMGMxZTA5MjAzYzgx",
        "ownedBy": "creator",
        "status": "active",
        "created": "2025-06-30T20:13:25.614Z",
        "actorId": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS84OWYwOGUyYi02MDM4LTQ3MmMtYjcyYy0zNjQyNjIwMThjNjE",
        "data": {
          "eventType": "disconnected",
          "eventTimestamp": "2025-08-14T18:52:43.357Z",
          "callId": "Y2lzY29zcGFyazovL3VzL0NBTEwvY2FsbGhhbGYtOTgyNzEzMjM3MDow",
          "callSessionId": "MWFmMDFjNTQtOTdlMS00ODA3LWEzZjgtMTY2ODNiNjFhNjQw",
          "personality": "terminator",
          "state": "disconnected",
          "muteCapable": false,
          "muted": false,
          "remoteParty": {
            "name": "POUYA SHAHRDAMI",
            "number": "+19059227700",
            "privacyEnabled": false,
            "callType": "external"
          },
          "created": "2025-08-14T18:52:41.728Z",
          "disconnected": "2025-08-14T18:52:43.357Z",
          "completedElsewhere": true
        }
      },
      "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ"
    },
    "method": "POST",
    "url": "/webhook"
  }
]
```
