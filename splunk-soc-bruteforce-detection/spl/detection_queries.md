
# SPL Detection Queries

## 1. View simulated authentication events

```spl
index=security source="bruteForce_simulation.csv"

This query displays the authentication events ingested into Splunk.

2. Identify failed login attempts
index=security source="bruteForce_simulation.csv" status=failed

This filters the dataset to identify failed authentication attempts.

3. Count failed attempts by source IP
index=security source="bruteForce_simulation.csv" status=failed
| stats count by src_ip
| sort -count

This query aggregates failed login attempts by source IP.

4. Detect potentially suspicious activity
index=security source="bruteForce_simulation.csv" status=failed
| stats count by src_ip
| where count >= 5
| sort -count

A threshold of five or more failed attempts is used to identify potentially suspicious authentication activity.

5. Investigate the targeted user
index=security source="bruteForce_simulation.csv" src_ip="KALI_IP"
| stats count by user
| sort -count

This query identifies the user targeted by the suspicious source IP.

Replace KALI_IP with the anonymized IP used in the published dataset.

6. Analyze authentication status
index=security source="bruteForce_simulation.csv" src_ip="KALI_IP"
| stats count by status

This query compares failed and successful authentication events.

7. Analyze the authentication timeline
index=security source="bruteForce_simulation.csv" src_ip="KALI_IP"
| table _time user src_ip action status
| sort _time

This query provides a chronological view of the authentication activity.
