```sql
SELECT
    *
INTO
    [dummyOutput]
FROM
    [telemetry]
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
```
```sql
SELECT
    deviceId = telemetry.iothub.connectionDeviceId,
	AVG(temperature),
	MIN(temperature),
	MAX(temperature),    
	intervalElapsedTimestamp = (System.Timestamp)
INTO
	[dummyOutput]
FROM
	[telemetry]
	TIMESTAMP BY
	     telemetry.iothub.enqueuedTime
GROUP BY
	telemetry.iothub.connectionDeviceId,
	TumblingWindow(minute, 1)
```



