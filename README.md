# Docker Compose Script

This directory contains the `docker-compose.yml` file for orchestrating the Mikoshi platform's microservices using Docker Compose.

## Services

The following services are defined:

1. **club**: Handles club-related operations.
2. **personnel**: Manages personnel data and operations.
3. **personnel-assignment**: Handles assignments of personnel.
4. **Authentication**: Authentication service.
5. **meeting**: Manages meetings and related data.
6. **activity_log**: Logs activities and events.
7. **insights**: Provides insights and analytics.
8. **summary-cache**: Caches summaries for performance.
9. **manage-insights**: Composite service for managing insights.
10. **query-llm**: Handles LLM (Large Language Model) queries.
11. **prompt**: Manages prompts for LLMs.

## Prerequisites

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/)

## Usage

1. Copy or create required `.env` files for each service as needed.
2. Build and start all services:

	```sh
	docker compose up --build
	```

3. To stop the services:

	```sh
	docker compose down
	```

## Networks and Volumes

- All services are connected via the `mikoshi-net` Docker network.
- A named volume `esd_pgdata` is used for persistent Postgres data.

## Notes

- Some services require environment variables. Check each service's folder for a `.env` example.
- Health checks are configured for critical services.
- Resource limits are set for each container.
