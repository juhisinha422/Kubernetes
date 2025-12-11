#Day-64

Securing Argo CD with RBAC + Project Isolation (A Must-Know for GitOps Engineers)
Most teams focus on deploying apps with Argo CD… but security and access control are where real GitOps maturity starts.

Today I built a full RBAC + Project-based setup with Dev, Test, Prod isolation and here’s the key takeaway:

1)Argo CD Projects enforce hard boundaries: Dev stays in Dev, Test stays in Test, Prod stays protected.

2)Default Project Locked Down: It’s too permissive  so I removed all access.

3)Least Privilege in Action: Users created for demo
    
developer → Dev
   
tester → Test
    
devops → Dev,Test,Prod

4)Each sees only their environment. That’s real RBAC.

5)Production Tip:

For Prod, skip local users.
 Use SSO like #Okta, #AzureAD, #GoogleIAM, #Keycloak, #GitHub #GitLab #OAuth.

Brings: MFA, group RBAC, central identity, zero password headaches.


![Image](https://github.com/user-attachments/assets/209a1cda-8828-4bb4-8d12-70cec656022b)
