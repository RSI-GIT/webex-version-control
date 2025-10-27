# User Disposition

This webhook provides user disposition information from Shadow Agent.

## Description

You will receive this request when a user clicks to add a disposition.
A user can change their disposition code for the same call as many times as they want.

Example 1 and 2: Same call, same person — only the disposition code and details are being changed.

Example 3: A different call with a new disposition code.

Example 4: A different call associated with a different tab (account code).

The message is a combination of the following fields: codeCallId, codeNumber, and codeDescription.
For additional context, the user ID and the current timestamp of the POST request are included.
The payload structure for disposition is stable.

## Sample Payloads

### Example 1

```json
{
  "body": {
    "payload": "user-disposition",
    "items": {
        "codeCallId": "NjBmMjQ5M2QtZWYwYi00MWRiLTg5MGYtYjFlMWRmNDllYjc1",
        "code": "disposition",
        "codeNumber": 1000,
        "codeDescription": "Remote Access Request",
        "message": "Disposition:NjBmMjQ5M2QtZWYwYi00MWRiLTg5MGYtYjFlMWRmNDllYjc1:1000:Remote Access Request",
        "userId": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE",
        "timestamp": "2025-10-27T14:14:32.963Z"
      },
    "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ"
  },
  "method": "POST",
  "url": "/webhook"
}
```

### Example 2

```json
{
  "body": {
    "payload": "user-disposition",
    "items": {
        "codeCallId": "NjBmMjQ5M2QtZWYwYi00MWRiLTg5MGYtYjFlMWRmNDllYjc1",
        "code": "disposition",
        "codeNumber": 1002,
        "codeDescription": "Appointment Scheduled",
        "message": "Disposition:NjBmMjQ5M2QtZWYwYi00MWRiLTg5MGYtYjFlMWRmNDllYjc1:1002:Appointment Scheduled",
        "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
        "userId": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE",
        "timestamp": "2025-10-27T14:16:15.005Z"
      },
    "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ"
  },
  "method": "POST",
}
```


### Example 3

```json
{
  "body": {
    "payload": "user-disposition",
    "items": {
        "codeCallId": "YjI4NWEzYmItODUzYS00MDNkLTlmNGMtYTcyY2Q2NmJhYjk0",
        "code": "disposition",
        "codeNumber": 2020,
        "codeDescription": "Callback Scheduled",
        "message": "Disposition:YjI4NWEzYmItODUzYS00MDNkLTlmNGMtYTcyY2Q2NmJhYjk0:2020:Callback Scheduled",
        "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
        "userId": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE",
        "timestamp": "2025-10-27T14:16:37.984Z"
      },
    "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ"
  },
  "method": "POST",
}
```

### Example 4

```json
{
  "body": {
    "payload": "user-disposition",
    "items": {
        "codeCallId": "NjBmMjQ5M2QtZWYwYi00MWRiLTg5MGYtYjFlMWRmNDllYjc1",
        "code": "Account",
        "codeNumber": 1000,
        "codeDescription": "Contract Signed",
        "message": "Account:NjBmMjQ5M2QtZWYwYi00MWRiLTg5MGYtYjFlMWRmNDllYjc1:1000:Contract Signed",
        "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ",
        "userId": "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE",
        "timestamp": "2025-10-27T14:28:45.035Z"
      },
    "orgId": "Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi8xNzExMTdkNi04YjgyLTQ0Y2EtOThlOS1hYzExNTdmMmNkMWQ"
  },
  "method": "POST",
}
```

