Adding app to app and tenant complexity
1. 2nd app
    1. Create another account in each OU, and deploy a simple application via pipelines (also setup monitoring & alerting )
    2. Create vpc peering allowing the first application to talk to the second & get a response, check access via VPC flow logs
    3. Replace vpc peering with transit gateway and deploy a traffic inspection VPC alongside that transit gateway
2. Tenants
    1. Modify OU structure to be multi-tenant (e.g /production/tenant1/account1) 
    2. Move the website and the 2nd app to tenant 1, set up another app in tenant 2
    3. Move to hub and spoke networking at tenant level with traffic inspection in the centre, meaning routing is now:
        1. Website -> tenant1 TGW -> 2nd app
        2. Website -> tenant1 TGW -> central TGW + traffic inspection -> tenant 2 TGW -> 3rd app
    4. Create an account / tenant vending scheme with CIDR allocation policies
3. More sophisticated networking
    1. Simulate an on prem connection off the central transit gateway & validate routing from each tenant
    2. Add an ops vpn to central TGW required to access each database
    3. Add a centrally managed internet connection (ie for downloading patches) to the central TGW with traffic inspection, and test downloads
4. Move to ASEA (start in a separate AWS account)
