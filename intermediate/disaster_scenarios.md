# Website Disaster Recovery
1. Audit everything for single points if failure eg at AZ and Region level. Check you have resilience. Include:
    1. The website
    2. Monitoring / alerting
    3. DNS
    4. Code Commit, Pipelines and AMIs
    5. Certificates, keys, parameters
2. Create a DR account for production:
    1. Deploy a static website to it
    2. Use failover routing in R53 to send traffic here if the primary is down
    3. Perform a DR test
3. Operational DR
    1. Ensure monitoring is available cross-regions (ie that you know the static website is up if region 1 fails)
    2. Ensure code commit is backed up to the second region
    3. Ensure content can deployed in the second region if region 1 is down
    4. Ensure the AD is resilient to region failure & you can login if region 1 is down 
4. Testing failures
    1. Simulate an az failure - check the apps and your cicd, monitoring, SSO, etc tools keep running
    2. Simulate a region failure - check apps keep running (check AD will go multi region first)
5. Testing an attack (likely to require several iterations)
    1. Give dev, test and admin creds to a friend. Give them 30 minutes to do stuff in the way an attacker would. (Change things, cover tracks, create their own users, create accounts)
    2. Prevent the compromised creds from being used again
    3. Use your audit tools (eg CloudTrail) to figure out what they did and prevent them getting back in (eg via users they created)
