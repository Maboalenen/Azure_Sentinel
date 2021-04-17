### kusto query language (KQL)
- Is a read-only request to process data and return results
- KQL functions are a quick and simple way to make repetitive actions simpler and quicker. They are one of the many ways that Azure Sentinel. 

Sample Query
----

|Query|Exp|
| :---| ---:|
| [union SecurityEvent, Event, SecurityIncident | where EventID == 4624]   uccessfully logged on 
