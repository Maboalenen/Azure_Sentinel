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

