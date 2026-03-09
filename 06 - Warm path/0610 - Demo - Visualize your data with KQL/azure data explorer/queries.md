```kql
Telemetry 
| project EnqueuedTime, Temperature
```
```kql
Telemetry 
| project EnqueuedTime, Temperature
| where EnqueuedTime > ago(5m)
```
```kql
Telemetry 
| project EnqueuedTime, Temperature
| where EnqueuedTime > ago(5m)
| render linechart
```
```kql
Telemetry 
| project EnqueuedTime, Humidity
| where EnqueuedTime > ago(5m)
| render linechart 
```


