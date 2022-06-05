# Website Disaster Recovery

1. Audit the website for single points if failure eg at AZ and Region level. Check you have resilience. Include:
    1. The website
    2. Monitoring / alerting
2. Create a DR account for production:
    1. Deploy a static website to it
    2. Use failover routing in R53 to send traffic here if the primary is down
    3. Perform a DR test
3. Testing failures
    1. Simulate an az failure - check the apps and your cicd, monitoring, SSO, etc tools keep running
    2. Simulate a region failure (not including the AD)
