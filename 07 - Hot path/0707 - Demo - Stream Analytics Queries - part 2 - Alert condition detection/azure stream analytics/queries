```sql
SELECT
    deviceId = telemetry.iothub.connectionDeviceId,    
	temperature,
    humidity,
    enqueuedTime = telemetry.iothub.enqueuedTime
INTO
    [dummyOutput]
FROM
    [telemetry]
WHERE temperature > 30
```
```sql
SELECT
    deviceId = telemetry.iothub.connectionDeviceId,    
	temperature,
    humidity,
    enqueuedTime = telemetry.iothub.enqueuedTime    
INTO
    [dummyOutput]
FROM
    [telemetry]
WHERE
    ISFIRST(minute, 10) OVER (PARTITION BY deviceid WHEN temperature > 30) = 1
```


