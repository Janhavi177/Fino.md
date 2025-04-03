# MSA Monitoring - UPI SOP

## 1. UPI Kibana - Monitoring Metrics

| S.No | Server IP     | Tool        | Service Name          | Monitoring Metrics |
|------|-------------|------------|----------------------|--------------------|
| 1    | 10.71.89.154 | UPI Kibana  | UPI-Switch-Count     | reqpay-debits, reqpay-credits, reqpay-reversal, bal-enq, reg-mob, reqpay-debit-fails, reqpay-credit-fails, reversal-fails, pin-errors, npci-call-failed-errors |
| 2    | 10.71.89.154 | UPI Kibana  | UPI Switch Errors-Logs | gateway-technical-declines, cbs-call-timeout-logs, cbs-esb-error-logs, npci-call-failed-errors |

## 2. UPI Kiali - Gateway & Connector Monitoring

| S.No | Server IP     | Tool       | Service Name              | Components Monitored |
|------|-------------|-----------|--------------------------|----------------------|
| 1    | 10.71.89.154 | UPI Kiali | UPI-Gateway              | upi-pathfinder, upi-janitor, upi-gateway, npci-ext |
| 2    | 10.71.89.154 | UPI Kiali | UPI-CBS-Connector        | upi-cbs-connector-fino2, upi-frm-connector, upi-hsm-connector-fino2 |
| 3    | 10.71.89.154 | UPI Kiali | UPI-Cache & Rate Control | upi-velolimits, upi-cache-walki-primary, upi-rate-limiter |
| 4    | 10.71.89.154 | UPI Kiali | UPI-Notification & Passthrough | upi-notify-connector-fino, passthrough-cluster, upi-notify-connector |

## 3. UPI Server - Monitoring Using Grafana

| S.No | Server IP     | Monitoring Metrics      | Description |
|------|-------------|-----------------------|-------------|
| 1    | 10.71.89.168 | CPU Usage             | Monitors processor workload and usage percentage |
| 2    | 10.71.89.168 | Memory Usage          | Tracks RAM consumption and available memory |
| 3    | 10.71.89.168 | Disk Usage            | Measures storage utilization and free space |
| 4    | 10.71.89.168 | Network Traffic       | Analyzes data transfer rates and bandwidth consumption |
| 5    | 10.71.89.168 | System Load Average   | Checks system performance under varying loads |
| 6    | 10.71.89.168 | Uptime & Process Count | Monitors server uptime and running processes |
