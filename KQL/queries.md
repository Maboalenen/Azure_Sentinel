### kusto query language (KQL)
- Is a read-only request to process data and return results
- KQL functions are a quick and simple way to make repetitive actions simpler and quicker. They are one of the many ways that Azure Sentinel. 

Basic KQL (Queries)
----
---
successfully logged on
```bash
union SecurityEvent, Event   | where EventID == 4624
 ``` 
 ```bash
 union SecurityEvent, Event   | where EventID == 4624  | count  
 ```
 ```bash
 union SecurityEvent, Event,  | where EventID == 4624  | summarize count() by AccountName, Computer 
 ```
 ```bash
 union SecurityEvent, Event | where  EventID == 4624 | project Computer , EventID 
 ```
 ```bash
 union SecurityEvent, Event | where EventID == 4624  | summarize arg_max(TimeGenerated, *) by Account. 
 ```
 ```bash
 union SecurityEvent, Event | where  EventID == 4624 | top  10  by TimeGenerated desc  
 ```
 failed logon
 ```bash
  union SecurityEvent, Event   | where EventID == 4625
 ```
 ```bash
 union SecurityEvent, Event  | where  EventID == 4625 |order by  TimeGenerated desc  | limit 10 
 ```
```bash
union SecurityEvent, Event, SecurityIncident  | where  EventID == 4625 |order by  TimeGenerated desc  | limit 10
````
successfully or failed logon
 ```bash
 union SecurityEvent, Event | where  EventID == 4624 or EventID == 4625  |project  EventID , Process ,  ProcessName , SubjectAccount
 ```
 IIS_logs 
 -----
 http code 200 success with specific fields
 ```bash
 union W3CIISLog  | where scStatus==200 |project  TimeGenerated , cIP , csMethod , csUriStem, csUriQuery , scStatus , TimeTaken , csUserAgent  
```
http code NOT 200 success with specific fields
```bash
 union W3CIISLog  | where scStatus!=200 |project  TimeGenerated , cIP , csMethod , csUriStem, csUriQuery , scStatus , TimeTaken , csUserAgent  
```
Only post Request
```bash 
union W3CIISLog  | where csMethod contains "POST"  |project  TimeGenerated , cIP , csMethod , csUriStem, csUriQuery , scStatus , TimeTaken , csUserAgent  
```
POST Request with 200 success
```bash
union W3CIISLog  | where csMethod contains "POST" and scStatus==200 |project  TimeGenerated , cIP , csMethod , csUriStem, csUriQuery , scStatus , TimeTaken , csUserAgent  
```
Show the Geolocation and remove the privete IPs with specific fields 
```bash
union W3CIISLog  | extend Country=RemoteIPCountry |where not(ipv4_is_private(cIP)) |project  TimeGenerated,Country ,cIP , sIP , csUriStem,csUserName,csUriQuery,TimeTaken, csUserAgent
```
for last three day
```bash
union W3CIISLog 
  | where TimeGenerated > ago(3d)
  | where not(ipv4_is_private(cIP))
  | project TimeGenerated, sSiteName, csMethod, csUriStem, sPort, sIP, cIP, RemoteIPCountry , csUserAgent
```
Powershell search for event_data contains .txt
```bash
union Event
  | where Computer contains "my_test_machine"
  | where Source contains "Powershell"
  | where EventData matches regex '.txt'
  | extend EventProduct = 'powershell'
  | extend EventData = split(EventData, '"')
  | extend RenderedDescription = split(EventData, '"')
  | extend DataItem_type = EventData[1]
  | extend sourceHealthServiceId = EventData[8]
  | project TimeGenerated,EventProduct , Computer, EventID, Source, RenderedDescription, UserName, ParameterXml, EventData, SourceSystem, sourceHealthServiceId , DataItem_type
```


