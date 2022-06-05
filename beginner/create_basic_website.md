# Create an initial / basic website
1. Manually deploy an apache2 webserver to EC2 & setup a hello world index page stored on the local EBS volume (20 mins)
2. Register a domain via R53 - cost is appprox $10 (15 mins)
3. Setup a DNS entry in r53 pointing at the website, with a 1 minute TTL (10 mins)
4. Move the content off the webserver’s local disk, onto EFS, check it is still served (20 mins)

# Move to an AMI
1. Snapshot the webserver (5 mins)
2. Terminate the webserver (5 mins)
3. Reprovision the webserver from the snapshot (10 mins)
4. Update DNS (10 mins)

# Move to an ALB
1. Terminate the webserver (5 mins)
2. Create an ASG behind an ALB using the AMI (15 mins)
3. Setup health checks for the ASG (10 mins)
4. Setup a scaling policy ensuring at least 2 instances in different AZs run at all times (10 mins)

# Test the ALB - Prove failing a health check causes a new healthy instance to be deployed by:
1. SSH onto one of the webservers and kill the httpd process (10 mins)
2. Terminate one of the webservers (10 mins)

# Improve security
1. Create a TLS certificate in ACM (15 mins)
2. Deploy the cert from ACM to the ALB (10 mins)
3. Check you have HTTPs from the web browser (5 mins)

# Improve repeatability
1. Put the website’s content in code commit (5 mins)
2. Create a pipeline to deploy new content from code commit to EFS (15 mins)
3. Make some changes, check the new content is served (15 mins)

# Experiments
1. Create a new AMI using NGINX, replace the one running in the ASG with this new AMI (20 mins)
2. Patch the webserver using systems manager (15 mins)
