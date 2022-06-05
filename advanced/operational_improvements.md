# Operational Improvements
**Note:** this assumes a hub and spoke network archtiecture has already been implemented

1. Add an ops vpn to central TGW, and require its use for any SSH access to EC2 instances, and any connectivity to databases (1 hour)
2. Create a centralised operational dashboard, aggregating the monitoring from each account accross dev, test, production (1 hour)
3. Simulate an on prem connection off the central transit gateway & validate routing from each tenant (1 hour)
4. Add a centrally managed internet connection (ie for downloading patches) to the central TGW with traffic inspection, and test downloads (1 hour)
