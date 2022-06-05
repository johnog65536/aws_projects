# Make the app more production like 
1. Delete the ASG/LB
2. Port the app, code commit and monitoring to the dev account (use a dev branch)
3. Deploy in dev account, vis a pipeline:
    1. Bake the AMI and deploy to an ASG being an ALB with health checks and scaling (ie as before)
    2. Update a dev.fqdn.com DNS entry to point to the ALB
    3. Deploy a cert from ACM to the ALB
    4. Separate pipeline to push content changes from code commit to EFS
4. Deploy in test:
    1. Create a test branch in code commit (in dev account)
    2. Create a test pipeline (in test account) that deploys the website under test.fqdn.com with separate monitoring
5. Deploy in production (as above)
6. Make some changes in code commit:
    1. Make some changes on dev branch
    2. Redeploy content in dev & validate it doesn’t appear in test/prod
    3. Merge to get branch & deploy to test / validate it doesn’t appear in prod
    4. Merge to prod & validate it now appears in prod
    5.  Validate dev users can’t manipulate the test account/website/pipelines & vice versa, but the admin users can
7. Encrypt the EFS storage and any AMIs/S3 buckets (recreate if needed)
8. Create a security account and forward all CloudTrail and CloudWatch logs to it + set up users and a log console
