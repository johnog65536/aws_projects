Create an initial, and basic website
1. Deploy an apache2 webserver & hello world page stored on the local EBS volume
2. Register a domain, put a DNS entry in r53 for the app with 1 minute TTL
3. Move the content off the webserver’s local disk, onto EFS
4. Snapshot the webserver. Terminate the webserver, then reprovision from the snapshot + update DNS
5. Terminate the webserver: replace with an AMI in an ASG behind an ALB with health checks and scaling policy & at least 2 instances in different AZs
6. Prove failing a health check causes a redeploy by taking down a webserver process, and by terminating an instance
7. Deploy a cert from ACM to the ALB and check you have HTTPs from the web browser
8. Setup CloudWatch +SNS to monitor/alarm & provide management info (eg number of requests) in a dashboard - check you get alarms on terminate an instance
9. Put the website’s content in code commit
10. Create a new AMI using NGINX, replace the one running in the ASG with this new AMI
11. Create a pipeline to deploy new content from code commit to EFS - make some changes, check the new content is served
