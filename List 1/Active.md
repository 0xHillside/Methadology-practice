# Review

## Mistakes

**TLDR**;
- Focused too much on shell access. didnt think outside the box
   - Think about what I have, Think outside the box. I know I have credentials, I know I have access to LDAP now. I should have gone for enumerating using bloodhound-python rather than rule it out without trying
- After getting credentials I was tunnel visioned and didnt check what the user had access
  - Always check what you have access to after new credentials, check EVERYTHING
  - In a real pentest this would have been DEVESTATING. In this case;

       - Read access to the SMB share which led to the flag
   - there could have been MORE important things in those directories like passwords, configurations, or even clues on admin and I would have completely disregarded it
 

I did pretty well on my own and everything went well, I was able to decrypt the GPP password and I already did this box before to be honest but forgot everything which is good. I got the creds and I knew I needed to get the user flag but I got stuck, why did I get stuck? 
I dont fucking know to be honest I know I could have used bloodhound-python but my brain didnt think it would be worth it.
I kept thinking "I need to get shell access". I tried SMBexec, Checked for winRM, RDP, nothing. I was lost and the issue was that i didnt was tunnel visioned on the shell access rather than the credentials. 
Credentials are as important as Getting a Shell. So I need to remember a shell is NOT ALWAYS the way forward. I was also ofcourse very fast, when doing psexec and I knew it needed a writeable share
so I gived up on it which is very WRONG. I need to check everything after I get new credentials, literally. EVERYTHING. Any and EVERY endpoint


## Notes from watching Ippsec

- To poke at DNS
 - Might get something you never know 
- ldap + dns + kerberos = 99% is a DC
- With new credentials always check all of the protocols
- When bloodhound runs
 - Mark the user you have as owned
 - Use the funny little road feature and have the end destination be Domain Admins, then the domain itself (active.htb) just to see the results
 - check for kerbroastable users always
