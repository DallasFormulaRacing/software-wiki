# Onboard CAN Streaming

## Basic information

---

### PM info

* Name - Andrew K.
* GitHub - @aklundt
* Discord - [Andrew Klundt](https://discord.com/users/837135039917457436)

### Contributors

* Andrew
* TBD

### Description

Onboard CAN Streaming is a telemetry pipeline designed to run on a vehicle-mounted embedded system (Raspberry Pi). It continuously reads CAN bus data from the car, buffers messages in a local store with persistence enabled, detects idling events (through RPM), and publishes time-series and event batches to Kafka with delivery acknowledgments. Its primary objective is to deliver CAN bus data into our cloud infrastructure. The architecture ensures zero data loss through connectivity interruptions.  

Note: The project's architecture and technology stack are not finalized and may evolve during development.

## Features

* Continuous CAN bus ingestion via a CAN hat.
* Local storage of CAN messages with persistence to survive power cycles and network outages.
* RPM-based idle detection with configurable overrides.
* Automated start and stop event generation tied to idle detection logic.
* Guaranteed delivery to Kafka with acknowledgment-driven queue draining.
* Configurable buffer management (queue trimming, size limits, retention policies).

## Possible Technology Used

The technology stack is tentative and may evolve. Possible tools include:

* C++
* Python
* Docker
* Linux development tools
* SQLite or Redis
* Kafka 
* Other tools and frameworks as needed
