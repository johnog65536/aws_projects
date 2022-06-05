# Testing an attack 
Note: This is likely to require several iterations

1. Give dev, test and admin creds to a friend. Give them 1 hour to do stuff in the way an attacker would: change things, cover tracks, create their own users, create accounts (1 hour)
2. Prevent the compromised creds from being used again (20 mins)
3. Use your audit tools (eg CloudTrail) to figure out what they did with each user, and prevent them getting back in, eg via users they created (1 to 4 hours)
