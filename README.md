# Home Server Postgres

Deploys the Postgres database to the cluster.

## Pre-Requisites

1. 1Password
2. CertManager

## Fixing "Panic"

If a transaction fails, there can be a panic in the pod. Unsure of what causes this 100%, requires manual repairs.

1. Uncomment the postgres-panic-fix container, and comment out the postgres container
2. Run the helm upgrade
3. The pod will appear to fail to start, however if you check the logs it'll have fixed the logs
4. Restore original deployment config.