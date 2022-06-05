# Make the account more production like:
## Externalise users
1. Setup an AD (1 hour)
2. Setup a windows instance to manage the AD / its users and join it to the domain (30 mins)
3. Create dev, test, prod, and admin groups & put some users into each (15 mins)
4. Use LDAP search to prove you can pull back users and group membership (10 mins)

## AWS Organisation
1. Setup an AWS Organisation (10 mins)
2. Create dev, test and prod OUs each with at least one AWS account in each (10 mins)
3. Setup AWS SSO for the users in the AD via command line and web console, using the dev/tesdt/prod groups to control what accounts they cn access (30 mins) 
4. Prove a user in the Dev group can access the Dev OU accounts & not Test accounts (20 mins)
5. Prove a user in the admin group can access all accounts (10 mins)
6. Prove admin users get more permissions than dev/test users - e.g can see billing console (10 mins)
7. Use SCPs to control what regions each OU can provision into & test (15 mins)

## Account management
1. Create 2 further accunts in the organisation (10 mins)
2. Close an account (5 mins)
3. Kick an account out of the org (5 mins)
4. Tidy up (5 mins)
