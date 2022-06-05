# Making the apps production like 
Do these steps __in each of dev, test and prod__

1. Move from hello world static website to a little Java app with an AuroraDB back end, with connection strings in Parameter Store
    1. Make sure the DB is in a private subnet, with no access to/from internet
    2. Update the pipeline to compile, package and deploy the code + DB schema
    3. Update the pipelines to perform static analysis / CVE scanning
    4. Update the pipeline to perform unit tests
2. Operations
    1. Create a process to patch the AMI and software in it, and to update the database schema + software
    2. Patch/upgrade the AD
    3. Create a process to manually back up and restore the database 
    4. Make sure all the monitoring, alerting (etc) are provisioned using Infra as code
3. App Sophistication
    1. Add sign in for the app using Cognito 
    2. Add a load testing capability
    3. Repackage the app as a container & deploy to EKS via ECR (using the pipeline)
    4. Ensure the code is signed during build/package and that the signature is validated at deploy
    5. Implement role separation so 1 user can commit code, another merges and another can trigger deploy
