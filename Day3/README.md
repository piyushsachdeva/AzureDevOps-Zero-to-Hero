# Azure Repos ( Work in Progress)

## What is Azure repos?

**Azure Repos is a set of version control tools that you can use to manage your code, just like GitHub**. Whether your software project is large or small, using version control as soon as possible is a good idea.

Version control systems are software that help you track changes you make in your code over time. As you edit your code, you tell the version control system to take a snapshot of your files. The version control system saves that snapshot permanently, so you can recall it later if you need it. Use version control to save your work and coordinate code changes across your team.

Even if you are working on a personal project, version control helps you stay organized as you fix bugs and develop new features. Version control keeps your development history so you can quickly review and even roll back to any code version.

- Helps you track changes in the codebase
- Maintains the history of your codebase, who made the changes, what changes were made, why the changes were made, etc
- Helps you stay organized
- Gives you the ability to rollback the changes as needed

## Git vs. TFVC

Azure Repos supports two types of Version Control:
- Git
- TFVC ( Team Foundation Version Control)

### Git
Git is the most popular distributed version control system, which allows developers to download the entire code repository locally with all the versions and make the changes remotely/offline. Changes can be synced to the remote server afterward.

To interact with Git, you can make use of Git clients such as Git for Windows, VSCode, etc
Git provides a version control system, but you need a hosting service to host your codebase(repositories). You can use git hosting services such as GitHub, Azure Repos, Bitbucket, Gitlab, etc.

### TFVC
Another type of version control system is TFVC, a centralized version control. In TFVC, only a single codebase version is downloaded locally, historical data is maintained on the central server. You can host TFVC on hosting services such as Perforce, SVC, Azure Repos, etc.

Configure Visual Code
Git Flows and Branching Strategies (To be included in the later videos)
Cloning the repo
Commit changes
Reviewing history
Working with branches
Tagging a release
Managing repository
Managing Pull requests
Sample application code
