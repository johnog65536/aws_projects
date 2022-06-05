# Operational Improvements

## Operstional Improvements 
1. Create a process to patch the AMI and software in it, and to update the database schema + software (2 hours)
2. Patch/upgrade and backup/recover the AD via automation (2 hours)
3. Create a process to manually back up and restore each database + test (2 hours)
4. Make sure all the monitoring, alerting (etc) are provisioned using Infra as code (1 hour)

## Futher Improvements
**Note:** these activities assume a hub and spoke network archtiecture has already been implemented
1. Add an ops vpn to central TGW, and require its use for any SSH access to EC2 instances, and any connectivity to databases (1 hour)
2. Create a centralised operational dashboard, aggregating the monitoring from each account accross dev, test, production (1 hour)
3. Simulate an on prem connection off the central transit gateway & validate routing from each tenant (1 hour)
4. Add a centrally managed internet connection (ie for downloading patches) to the central TGW with traffic inspection, and test downloads (1 hour)
