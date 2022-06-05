# Production level account complexity
## Add a 2nd app
1. Create another account in each OU, and deploy a simple application via pipelines (also setup monitoring & alerting (2 hours)
2. Create vpc peering allowing the first application to talk to the second & get a response, check access via VPC flow logs (1 hour)
3. Replace vpc peering with transit gateway and deploy a traffic inspection VPC alongside that transit gateway (1 hour)

## Add multiple tenants
1. Modify OU structure to be multi-tenant, e.g /production/tenant1/account1 (15 mins)
2. Move the website and the 2nd app to tenant 1, set up another app in tenant 2 (1 hour)
3. Move to hub and spoke networking at tenant level with traffic inspection in the centre (2 hours)
    1. Meaning routing is now:
    2. Website -> tenant1 TGW -> 2nd app
    3. Website -> tenant1 TGW -> central TGW + traffic inspection -> tenant 2 TGW -> 3rd app

## Standardise enterprise controlls
1. using Control Tower, create an account / tenant vending scheme with CIDR allocation policies (3 hours)
2. Move to ASEA, but do it in a separate AWS account (2 days)
