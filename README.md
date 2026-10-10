# river-infra

Local dev stack for River: LocalStack (S3), ClickHouse, VictoriaMetrics, Grafana, the River services and the .NET demo app.

Service images are built from sibling checkouts:

```
projects/
  river-infra/    <- this repo, run compose here
  river-ingest/   <- river-sidecar, river-ingestion
  river-query/    <- river-query-api
```

```bash
docker compose up --build
```

Override locations with `RIVER_INGEST_DIR` and `RIVER_QUERY_DIR`.

ClickHouse migrations live in `river-ingest/river-ingestion/migrations` (applied by river-ingestion at startup).
Specs, plans and agent context live in [river-spec](https://github.com/bsterligov/river-spec), not here.
