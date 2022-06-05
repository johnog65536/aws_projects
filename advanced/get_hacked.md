# Testing an attack 
Note: This is likely to require several iterations

1. Give dev, test and admin creds to a friend. Give them 30 minutes to do stuff in the way an attacker would. (Change things, cover tracks, create their own users, create accounts)
2. Prevent the compromised creds from being used again
3. Use your audit tools (eg CloudTrail) to figure out what they did and prevent them getting back in (eg via users they created)
