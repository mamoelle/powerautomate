# Remove user from Team

## Description
Users with a specific domain are not allowed yet to use Teams collaboration but want to leverage already meetings. Currently all users with a Teams license can be added to a Team.
To meet the requirements we have to remove users from a the Team once they join the team.

Objective:
* Remove a user with a specific domain from a Teams team and notify the owner as well as the user via email.
* Track how many users join teams

### Solution and dependencies

Key of the solution is the Azure Audit log where all group membership events are logged. The Power Automate flow queries the Audit log via Graph API to filter users which have been added to a team recently. The flow runs every 30min per default to find user with a matching domain. If removed from the team via Graph API

Components:
* Power Automate license
* Graph API - App Registration
    * AuditLog.Read.All , Directory.ReadWrite.All , Group.ReadWrite.All , GroupMember.ReadWrite.All

### Installing

Import the Power Automate flow, add email connector and adjust the variables with edit: in the comment line.

Variables: 
Runcycle
GraphTenanid
GraphClientSecret
GraphClientID

### Executing program

Adjust the runcycle variable to match with the Power Automate schedule. 
Default is 30min (runcycle variable)

## Help

Contact the authors

## Authors

Contributors names and contact info

ex. Mario Möller


## Version History

* 1
    * First release

## Acknowledgments

Inspiration, code snippets, etc.
* [Send Email on School Data Sync Errors](https://emea.flow.microsoft.com/en-us/galleries/public/templates/ffec9fa3101e4a8281a2b2f7425ef0f1/send-email-on-school-data-sync-errors/)
