# Apache Kafka Multi-Node Setup (KRaft Mode)

This repository documents the setup for a **multi-node Kafka cluster** using **KRaft mode** (no ZooKeeper), including storage formatting and controller configuration.

---

## 🛠 Kafka Storage Formatting

Before starting your Kafka brokers, you **must format the storage directories** using the `kafka-storage.sh` tool. This initializes the metadata log directories with the correct cluster ID and controller quorum.

### 📌 Format Command

```cmd
kafka-storage.bat format \
  --cluster-id rT6wJ0pqQ-qfapcp5Q7Nyw \
  --initial-controllers "1@localhost:9092:e-0mCJpGQzKPWIJldaYuvw,2@localhost:9094:Alzn_rEVTl6HXvSbQlOMjA,3@localhost:9096:bTZQr6fTQICYrypoYr-eTA" \
  -c ../../muti-node-broker/server1.properties
```

## 🛠 Kafka Server Start

```cmd
kafka-server-start.bat ../../multi-node-broker/server1.properties
```

```cmd
kafka-server-start.bat ../../multi-node-broker/server2.properties
```


``cmd
kafka-server-start.bat ../../multi-node-broker/server3.properties
```
