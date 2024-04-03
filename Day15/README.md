Day 15/16 Azure DevOps Security Best Practices | What are Azure DevOps Best Practices
## Check out the video below for Day15 👇

[![Day 15/16 Azure DevOps Security Best Practices | What are Azure DevOps Best Practices](https://img.youtube.com/vi/l5hSkcSRiVI/sddefault.jpg)](https://youtu.be/l5hSkcSRiVI)

## Below best practices were discussed in detail in the video:

1. **Access Control with Microsoft Entra, formerly known as Azure Active Directory**
    - Enable Microsoft Entra directory, invite external users to the directory, entra settings
    - Integrate Azure DevOps with Microsoft Entra ID to have a single identity plane. It reduces risk, and you do not have to manage users from multiple places.
    - Users, groups, and roles are synced between Azure and Azure DevOps

2. **Organization level permissions**
    - e.g., security --> policy: Should not allow the creation of public projects
    - External users disabled
    - Additional org admin to the group project collection admins

3. **Agent pools**
   - --> default --> auto update/update agents
   - maintenance schedule
   - Use self-hosted agents if you want full control over your build servers
   - Use a separate agent pool to build artifacts shipped or deployed to production.
  
4. **Pipeline settings**
   -  --> Disabling the creation of a classic build pipeline as yaml is the preferred way as it provides traceability for changes and can be maintained in a git repo.

5. **Project-level permissions**
    - Add Groups and teams instead of individual users
    - pipeline settings --> retentions policy for cost optimization and storage

6. **Pipeline security:**
    - Ensure users/groups have the least privileged access to the pipeline
    - Add checks and default approvers to the pipeline

7. **Repo settings:**
    - settings --> branch policy
    - Ensure that the original pull requester can’t approve the change
    - automatic reviewer
    - Set the “Require a minimum number of reviewers” policy to ON, so that every pull request gets reviewed by at least two approvers.
    - Enable advanced security automatically: watch the video
    - branch policy

8. **Authentication and Authorization**
    - Use service principles and managed identities wherever possible
    - Create separate service principles for separate teams, developers, ops, and so on
    - Scope service connections only to the RG to which they need access. It Should not have permissions for the entire sub.
    -  Use workload identity service connection as it is more secure than other methods.
    - Don’t use Azure Classic service connections, as there’s no way to scope the permissions.
  
9. **Personal Access tokens**:
    - A lot of things to be kept in mind while using PAT, it should have restrictive permissions, it should be renewed after a few days, revoked when compromised, and so on.

10. **Secrets and credentials access**
    - Secrets should never be hardcoded within the pipeline or Git Repo.
    - You should either pass it as runtime variable during pipeline execution and use the tokenize step within Pipeline
    - Or, You Azure Key Vault to store and access the secrets
    - You can also use a third-party secret management service like Hashicorp Vault.
    - Dont store secrets in pipeline variables, use key vault or use pipeline tokenization or third paty such as hashicorp key vault
