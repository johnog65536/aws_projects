# Website Disaster Recovery

## Audit
Audit the website for single points if failure eg at AZ and Region level. Check you have resilience. Include:
1. The website (5 mins)
2. Monitoring / alerting (5 mins)

## Create DR capability
1. Create a DR account for production (10 mins)
2. Deploy a static website to it, containing a "sorry we are down" page (20 mins)
3. Setup failover routing in R53 to send traffic to the static page, if the primary is down (10 mins)
4. Perform a DR test by deleting the ASG (20 mins)

## Further testing
1. Simulate an az failure - check the apps **and** your cicd, monitoring, SSO, etc tools keep running (15 mins)
2. Simulate a region failure - but not including the AD (30 mins)
