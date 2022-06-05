# Making the apps production like 
Do these steps __in each of dev, test and prod__

## Use a dynamic app
1. Move from hello world static website to a little Java app with an AuroraDB back end, with connection strings in Parameter Store (3 hours)
1. Make sure the DB is in a private subnet, with no access to/from internet (10 mins)
2. Update the pipeline to compile, package and deploy the code + DB schema (1 hour)
3. Update the pipelines to perform static analysis / CVE scanning (1 hour)
4. Update the pipeline to perform unit tests (2 hours)

## More App Sophistication
1. Add sign in for the app using Cognito (4 hours)
2. Add a load testing capability (1 hour)
3. Repackage the app as a container & deploy to a new EKS cluster via ECR using a new pipeline (4 hours)
5. Ensure the code is signed during build/package and that the signature is validated at deploy (1 hour)
6. Implement role separation so 1 user can commit code, another merges and another can trigger deploy (2 hours)
