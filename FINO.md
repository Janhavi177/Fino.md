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

# MSA Monitoring - P2M_Pay SOP

## 1. P2M_Pay Kibana

| S.No | Server IP      | Tool           | Service Name                 | Monitoring Task                        |
|------|--------------|---------------|-----------------------------|----------------------------------------|
| 1    | 10.181.0.249 | P2M_Pay Kibana | P2M Pay Transaction Details | 1. Transaction Success  <br> 2. Settlement Success Count |

## 2. P2M_Pay Kiali

| S.No | Server IP      | Tool          | Service Name               | Commands | Monitoring Task                        |
|------|--------------|--------------|---------------------------|----------|----------------------------------------|
| 1    | 10.181.0.185 | P2M_Pay Kiali | Transactionrequest-jvm    | -        | 1. Monitor Transaction Requests  <br> 2. Monitor Transaction Status |

## 3. P2M_Pay Recon Report

| S.No | Server IP      | Tool                     | Service Name                    | Commands                                           | Monitoring Task                                       |
|------|--------------|-------------------------|--------------------------------|-------------------------------------------------|-------------------------------------------------|
| 1    | 10.71.89.153 | Cycle-wise Recon Report | -                              | `$cd /tmp/p2mpay-recon-logs/cycle-wise`         | 1. Cycle Timings and Report Generation Schedule  <br> 2. Full-Day Recon |
| 2    | 10.81.0.73   | P2M_Pay Recon Report    | -                              | `$sftpusr_p2mpay@prodsftp.finopaymentbank.in`  | Ensure timely recon file upload & report errors to MSA Admin & Bank Teams |

## 4. P2M_Pay Grafana Dashboard

| S.No | Server IP      | Tool                     | Service Name                 | Commands | Monitoring Metrics                                 |
|------|--------------|-------------------------|-----------------------------|----------|-------------------------------------------------|
| 1    | 10.181.0.37  | P2M_Pay Grafana Dashboard | Server Health Monitoring     | -        | 1. CPU Usage  <br> 2. Memory Usage  <br> 3. Disk Usage  <br> 4. Network Traffic  <br> 5. System Load Average  <br> 6. Uptime & Process Count |
| 2    | 10.181.0.249 | P2M_Pay Grafana Dashboard | PostgreSQL Database Monitoring | -        | 1. Database Health (Uptime, Active Connections)  <br> 2. Performance Metrics (Queries/sec, Transaction Rate)  <br> 3. Resource Utilization (CPU, Memory, Disk I/O)  <br> 4. Replication Status (Replication Lag, Standby Sync)  <br> 5. Storage & Indexes (Table Size Growth, Index Efficiency) |

# MSA Monitoring - PTA SOP

## DBeaver-ce Monitoring Table

| S.No | Server IP     | Tool         | Service Name                    | SQL Queries | Monitoring Metrics |
|------|-------------|-------------|--------------------------------|-------------|--------------------|
| 1    | 10.71.86.102 | DBeaver-ce  | GL_Balance Table              | `SELECT gl_number, balance_amount, updated_at FROM gl_balance gb ORDER BY balance_amount;` | 1. Gateway-technical-declines  <br> 2. cbs-call-timeout-logs  <br> 3. cbs-esb-error-logs  <br> 4. npci-call-failed-errors |
| 2    | 10.71.86.102 | DBeaver-ce  | Verify last txn in PTA        | `SELECT is_partner_account, account_number, balance_amount FROM partner_account_detail pad2 JOIN account_balance ab ON pad2.pta_account_number = ab.account_number WHERE pad2.is_partner_account = false;` | 1. Morning Report  <br> 2. Form Local system |





