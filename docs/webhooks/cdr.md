# CDR

This webhook provides the raw CDR feed from the Webex API. It will be sent every 5 minutes if anything exists; if not, no data will be passed.

## Sample Payload

```json
{
  "body": {
    "payload": "webex-cdr",
    "items": [
      {
        "Answer time": "",
        "Answered": "false",
        "Direction": "ORIGINATING",
        "Called line ID": "NA",
        "Call ID": "SSE164953585150825-1351543787@10.250.194.97",
        "Calling line ID": "NA",
        "Start time": "2025-08-15T16:49:53.576Z",
        "Call type": "SIP_NATIONAL",
        "Client type": "TEAMS_WXC_CLIENT",
        "Client version": "45.8.0.32875",
        "Correlation ID": "3e8d11ca-7965-4eba-b961-dd7a419649ab",
        "International country": "",
        "Device MAC": "",
        "Duration": 0,
        "Inbound trunk": "",
        "Org UUID": "171117d6-8b82-44ca-98e9-ac1157f2cd1d",
        "Original reason": "",
        "OS type": "windows",
        "Outbound trunk": "",
        "Redirect reason": "",
        "Related reason": "",
        "Report ID": "399a6e2c-169a-3262-93b3-49feb903d4fd",
        "Report time": "2025-08-15T16:50:01.772Z",
        "Route group": "",
        "Site main number": "+12895133484",
        "Site timezone": "-240",
        "Sub client type": "",
        "User UUID": "a808befa-9138-461c-b9af-392c784e0c1a",
        "User type": "User",
        "User": "Pouya Shahrdami",
        "Called number": "+19059227700",
        "Calling number": "+12895133483",
        "Location": "RSI",
        "Dialed digits": "+19059227700",
        "Releasing party": "Local",
        "Redirecting number": "",
        "Site UUID": "419f6d68-a080-47dc-99df-38fa40223406",
        "Department ID": "",
        "Transfer related call ID": "",
        "Authorization code": "",
        "Model": "",
        "Local SessionID": "9dea6285012050008000178cc521a001",
        "Remote SessionID": "",
        "Call transfer time": "",
        "Local call ID": "9850472912:0",
        "Remote call ID": "",
        "Network call ID": "BW1649536451508251171865576@10.71.220.6",
        "Related call ID": "",
        "User number": "+12895133483",
        "Call outcome": "Success",
        "Call outcome reason": "Normal",
        "Ring duration": "8",
        "Answer indicator": "No",
        "Release time": "2025-08-15T16:50:01.772Z",
        "Final local SessionID": "9dea6285012050008000178cc521a001",
        "Final remote SessionID": "",
        "PSTN legal entity": "Cisco Systems Canada Co",
        "PSTN vendor org ID": "0b43a1a8-2efd-4892-b301-e7a5a6d2c884",
        "PSTN vendor name": "Cisco Calling Plans",
        "PSTN provider ID": "00414f37-267d-40eb-9355-2c1876c202a1",
        "External customer ID": "",
        "Redirecting party UUID": "",
        "Public Calling IP Address": "NA",
        "Public Called IP Address": "NA",
        "Caller ID number": "+12895133483",
        "External caller ID number": "+12895133483",
        "Device owner UUID": "",
        "Call Recording Platform Name": "",
        "Call Recording Result": "",
        "Call Recording Trigger": ""
      }
    ]
  }
}
```
