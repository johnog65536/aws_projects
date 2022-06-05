# Disaster Scenarios

1. Audit EVERYTHING for single points if failure eg at AZ and Region level. Check you have resilience. Include:
    1. The website
    2. Monitoring / alerting
    3. DNS
    4. Code Commit, Pipelines and AMIs
    5. Certificates, keys, parameters
2. Revise the DR account for production:
    1. Deploy a second copy of the website rather than static website
    2. Use failover routing in R53 to send traffic here if the primary is down
    3. Perform a DR test
3. Operational DR
    1. Ensure monitoring is available cross-regions (ie that you know the static website is up if region 1 fails)
    2. Ensure code commit is backed up to the second region
    3. Ensure content can deployed in the second region if region 1 is down
    4. Ensure the AD is resilient to region failure & you can login if region 1 is down 
4. Testing failures
    1. Simulate an az failure - check the apps and your cicd, monitoring, SSO, etc tools keep running
    2. Simulate a full region failure - check apps keep running (check AD will go multi region first)