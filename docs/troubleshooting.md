# Troubleshooting

## Check Prometheus

sudo systemctl status prometheus

sudo journalctl -u prometheus -n 50 --no-pager

sudo promtool check config /etc/prometheus/prometheus.yml

sudo promtool check rules /etc/prometheus/alert_rules.yml

## Check Node Exporter

sudo systemctl status node_exporter

sudo journalctl -u node_exporter -n 50 --no-pager

curl http://localhost:9100/metrics

## Check Blackbox Exporter

sudo systemctl status blackbox_exporter

sudo journalctl -u blackbox_exporter -n 50 --no-pager

curl http://localhost:9115/metrics

## Check Backend

sudo ss -lntp | grep 3000

curl -i http://localhost:3000

curl -i http://localhost:3000/health

## Check Prometheus Targets

Open the Prometheus Targets page and verify:

- prometheus - UP
- node_exporter - UP
- backend - UP

## Check Alerts

Open the Prometheus Alerts page and verify:

- HighCPUUsage
- HighMemoryUsage
- HighDiskUsage
- BackendApplicationDown
- BackendResponseTimeHigh
