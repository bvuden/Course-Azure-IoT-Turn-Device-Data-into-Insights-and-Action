```kql
.alter table Telemetry policy streamingingestion enable
```
```kql
.create table Telemetry ingestion json mapping "TelemetryMapping"
    '['
        '{"Column": "MessageId", "Properties": {"Path": "$.messageId"}},'
        '{"Column": "DeviceName", "Properties": {"Path": "$.deviceName"}},'
        '{"Column": "Temperature", "Properties": {"Path": "$.temperature"}},'
        '{"Column": "Humidity", "Properties": {"Path": "$.humidity"}},'
        '{"column": "DeviceId", "Properties":{"Path":"$.iothub-connection-device-id"}},'
        '{"Column": "EnqueuedTime", "Properties": {"Path": "$.iothub-enqueuedtime"}}'
    ']'
```

