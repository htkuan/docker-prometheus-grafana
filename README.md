# Using docker-compose to demo monitoring redis by using prometheus and grafana

## setting up
ref:

1. redis-exporter
https://github.com/oliver006/redis_exporter

2. grafana redis exporter dashboard
https://grafana.com/grafana/dashboards/763

step:

1. docker-compose pull
2. login grafana
3. add data sources in grafana
4. create dashboard(default and import redis exporter dashboard) in grafana
5. go to redis setting some data

## reload configuration

1. hot reload prometheus configuration
    ```bash
    curl -X POST http://127.0.0.1:9090/-/reload
    ```

2. hot reload alertmanager configuration
    ```bash
    curl -X POST http://127.0.0.1:9093/-/reload
    ```

## redis operations

```bash
docker exec redis redis-cli set <key> <value>
docker exec redis redis-cli del <key>
```