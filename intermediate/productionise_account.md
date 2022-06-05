Make the account more production like:
1. Set up an AD, and a windows instance to manage the AD / its users
    1. Create dev, test, prod, and admin groups & put some users into each
    2. Use LDAP search to prove you can pull back users and group membership
2. Set up an AWS Organisation with dev, test and prod OUs each with at least one AWS account
    1. Get SSO working for the users in the AD via command line and web console 
    2. Prove a user in the Dev group can access the Dev OU accounts & not Test accounts. 
    3. Prove a user in the admin group can access all accounts
    4. Prove admin users get more permissions than dev/test users - e.g can see billing console
    5. Use SCPs to control what regions each OU can provision into
3. Account management
    1. Create 2 further accunts in the organisation
    2. Close an account
    3. Kick an account out of the org

