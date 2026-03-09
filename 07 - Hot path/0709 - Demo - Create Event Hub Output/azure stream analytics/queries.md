```sql
SELECT
    deviceId = telemetry.iothub.connectionDeviceId,    
	temperature,
    humidity,
    enqueuedTime = telemetry.iothub.enqueuedTime    
INTO
    [eventhuboutput]
FROM
    [telemetry]
WHERE
    ISFIRST(minute, 10) OVER (PARTITION BY deviceid WHEN temperature > 30) = 1
```


