# Make the app more production like 

**Note:** This assumes the AWS Organisation structure is in place

## Prep
1. Delete the ASG/LB (5 mins)
2. Port the app, code commit and monitoring to the dev account, use a dev or the main branch in code commit (30 mins)

## Deploy in dev account, vis a pipeline:
1. Bake the AMI via a pipeline (15 mins)
2. Create a pipeline to deploy the AMI/ASG/ALB as before with healthchecks and monitoring (30 mins)
3. Ensure the pipeline updates R53 using dev.whatever.com (10 mins)
4. Ensure the pipeline deploys a cert from ACM to the ALB (10 mins)

## Deploy in test:
1. Create a test branch in code commit in the dev account (5 mins)
2. Create a test pipeline (in test account) that deploys the website under test.whatever.com with separate monitoring (20 mins)

##Deploy in production 
per test approach, using production.whatever.com

## Make some changes in code commit
1. Create a separate pipeline to push content changes from code commit to EFS, in each account (30 mins)
2. Make some changes on dev branch (5 mins)
3. Redeploy content in dev & validate it doesn’t appear in test/prod (10 mins)
4. Merge to get branch & deploy to test / validate it doesn’t appear in prod (10 mins)
5. Regress a change out of test (simulating a failed release) and update teh branch (20 mins)
6. Make a replacement change & push to test (10 mins)
7. Merge to prod & validate it now appears in prod (10 mins)
8. Validate dev users can’t manipulate the test account/website/pipelines & vice versa, but the admin users can see both (15 mins)
