## Ingest and Alert

Goal: Retrieve data from an external system and ingest it as a metric.  If the value crosses a configured threshold, then generate an event/alert.

- Credential Vault
    * Access an API token from the Credential Vault using the Dynatrace SDK
- Metric Ingest
    * Retrieve data from an external system using HTTP GET
    * Ingest retrieved data point using the Dynatrace API with API token (not optimal)
    * Ingest retrieved data point using the Dynatrace SDK (optimal)
- Event Ingest
    * Query ingested metric data point using DQL
    * Evaluate metric value against a threshold
    * If the threshold is breached, generate an event using the Dynatrace SDK