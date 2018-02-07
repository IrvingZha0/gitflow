# gitflow

# 1. Feature Git Flow 


Git flow workflow - Feature Branches
![alt text](https://wac-cdn.atlassian.com/dam/jcr:2bef0bef-22bc-4485-94b9-a9422f70f11c/02%20(2).svg?cdnVersion=jo)

## 1.1 What is Feature Branches
Branches created from the develop branch and are used to code a new feature for an upcoming or future release.

Feature branches are typically merged back into develop via a Merge Request, which needs approval
Before requesting Feature branch merge back to develop, refresh of Feature branch is needed to resolve any possible conflicts
Merge Request brings an opportunity to review the code and request modifications prior to accepting the request.
## 1.2 Feature Branches Life-cycle
Creation by branching off the mainline development branch

Local development with one or more commits against that branch

Refresh the feature branch from mainline development branch by rebasing

Creation of a pull request for merging the commits into the mainline development branch 

Approval of the merge request and merging of the commits into the mainline development branch 

Deletion of the feature branch

## 1.3 Naming of Feature Branch
When creating a new feature branch, it has proven easiest to use the ticket number for what is being implemented.
```
feature/{taskId}
```
This serves several purposes:

All work is tracked against committed stories 

Features and bug fixes are small in granularity to be sufficiently testable 

In GitLab, all branches can easily be identified and can be periodically cleaned

## 1.4 Refreshing a Feature Branch
To minimize merge conflicts when feature branch is merged back, the developer needs to refresh the local feature branch from mainline development branch before Merge Request:
```
$ git pull --rebase origin <branch_name>
```
The --rebase option will preserve the commit history of the incoming changes rather than creating one new commit of all changes.

After rebasing push with --force flag to the feature branch is required, as new commits on top of development branch are created:
```
$ git push --force origin <branch_name>
```
Otherwise, local and remote versions will diverge.

# 2. Contents of Commit Messages
Each commit message should begin with the Jira ticket number
The subsequent comment should give a brief overview of what was modified
Use the pattern “Doing something”: “Adding component for…”, “Removing script from…” etc.
Avoid useless phrases like “bug fix” or “new feature”
In the case of implementing a BR (global requirements), the developer must also include the BR number in their commit messages
Example: “JIRA-123 Implementing backend for feedback component”.

# 3. CI Flow
HKEX-CPFW > Git Workflow > image2018-2-6 12:4:11.png





