### kusto query language (KQL)
- Is a read-only request to process data and return results
- KQL functions are a quick and simple way to make repetitive actions simpler and quicker. They are one of the many ways that Azure Sentinel. 

Sample KQL (Queries)
----
---
successfully logged on
```bash
union SecurityEvent, Event   | where EventID == 4624
 ``` 
 ```bash
 union SecurityEvent, Event   | where EventID == 4624  | count  
 ```
> union SecurityEvent, Event, SecurityIncident  | where EventID == 4624  | summarize count() by AccountName, Computer  
> union SecurityEvent, Event, SecurityIncident  | where EventID == 4624  | summarize arg_max(TimeGenerated, *) by Account. 
> union SecurityEvent, Event, SecurityIncident  | where  EventID == 4624 |extend mahmoud = Account  
> union SecurityEvent, Event, SecurityIncident  | where  EventID == 4624 |extend mahmoud = Account | project Computer , mahmoud      (project means stats count by coumputer)
> union SecurityEvent, Event, SecurityIncident  | where  EventID == 4624 or EventID == 4625  |project  EventID , Process ,  ProcessName , SubjectAccount


union SecurityEvent, Event, SecurityIncident  | where  EventID == 4624 |order by  TimeGenerated desc  | limit 10

union SecurityEvent, Event, SecurityIncident  | where  EventID == 4624 | top  10  by TimeGenerated desc   
