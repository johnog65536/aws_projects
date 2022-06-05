# Disaster Scenarios

## Audit
Audit EVERYTHING for single points if failure eg at AZ and Region level. Check you have resilience. Include **at least**:
1. The website (5 mins)
2. Monitoring / alerting (5 mins)
3. DNS (5 mins)
4. Code Commit, Pipelines and AMIs (5 mins)
5. Certificates, keys, parameters (5 mins)

## Create a DR account :
1. Deploy a second copy of the website rather than static website, via pipeline (30 mins)
2. Use failover routing in R53 to send traffic here if the primary is down (10 mins)
3. Perform a DR test (30 mins)

## Operational DR
1. Ensure monitoring is available cross-regions ie that you know the static website is up if region 1 fails (30 mins)
2. Ensure code commit is backed up to the second region (20 mins)
3. Ensure content can deployed in the second region if region 1 is down (20 mins)
4. Ensure the AD is resilient to region failure & you can login if region 1 is down (60 mins)

## Testing failures
1. Simulate an az failure - check the apps and your cicd, monitoring, SSO, etc tools keep running (60 mins)
2. Simulate a full region failure - check apps keep running **check AD will go multi region first** (60 mins)
