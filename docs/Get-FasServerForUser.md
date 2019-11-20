# Get-FasServerForUser

Identify the primary and failover Federated Authentication Server addresses for a UPN.

## Syntax

`Get-FasServerForUser [-UserPrincipalNames <String[]>] [<CommonParameters>]`

## Detailed Description

This cmdlet identifies the addresses of the primary and failover Federated Authentication Server to use for a specified UPN. A deterministic algorithm based on a SHA512 hash of the UPN is used to identify the addresses of two Federated Authentication Service servers, based on configuration in Group Policy. As long as the same Group Policy configuration is applied to all computers, the same addresses will be generated for each user. When a user logs in to Storefront the primary FAS server identified by this commandlet will be contacted, followed by the failover FAS server if the primary server is unavailable. If the failover server is also unavailable Storefront will continue to try other FAS servers. This algorithm allows user certificates to be cached in an efficient manner.

## Related Commands

## Parameters

| Name               | Description                                                                                                                               | Required? | Pipeline Input        | Default Value |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-----------|-----------------------|---------------|
| UserPrincipalNames | Array of UPNs (e.g. user@domain.com) for which to determine FAS addresses. Note that the user accounts do not need to exist in the domain | false     | true (ByPropertyName) | \$NULL        |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### void

This cmdlet returns the UPNs and associated FAS primary and failover servers

## Examples

### EXAMPLE 1

    C:\PS> Get-FasServerForUser -UserPrincipalNames @("user1@mycompany.com", "user2@mycompany.com")

This looks up the addresses of the FAS servers that will hold cached certificates for each UPN.

### EXAMPLE 2

    C:\PS> Import-Module ActiveDirectory
    C:\PS> $users = foreach ( $user in Get-ADGroupMember "MyGroup" ) { echo ($user.name + "@mycompany.com"); }
    C:\PS> Get-FasServerForUser -UserPrincipalNames $users

This enumerates the UPN addresses of users in "MyGroup" and looks up the FAS servers that will hold cached certificates for each.
