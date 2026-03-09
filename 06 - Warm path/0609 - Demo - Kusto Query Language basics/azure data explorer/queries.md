```kql
Telemetry
```
```kql
Telemetry | where DeviceId == 'RaspberryPiSimulator'
```
```kql
Telemetry | where DeviceId == 'RaspberryPiSimulator' | count
```
```kql
Telemetry 
| where DeviceId == 'RaspberryPiSimulator'
| count
```
```kql
Telemetry 
| where DeviceId == 'RaspberryPiSimulator'
| sort by EnqueuedTime
```
```kql
Telemetry 
| where DeviceId == 'RaspberryPiSimulator'
| sort by EnqueuedTime
| project MessageId, Temperature, Humidity, EnqueuedTime
```
```kql
Telemetry 
| summarize NumberOfMessages = count() by DeviceId
```
```kql
Telemetry 
| summarize NumberOfTemperatureAlerts = countif(Temperature > 30) by DeviceId
```
```kql
Telemetry 
| summarize MaxTemperature = max(Temperature)
```
```kql
Telemetry 
| summarize 
    MaxTemperature = max(Temperature),
    MinTemperature = min(Temperature),
    AvgTemperature = avg(Temperature)
```


