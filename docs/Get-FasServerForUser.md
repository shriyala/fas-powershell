# Get-FasServerForUser

## Synopsis
Identify the primary and failover Federated Authentication Server addresses for a UPN.

## Syntax

```
Get-FasServerForUser -UserPrincipalNames <String[]> [<CommonParameters>]
```

## Description
This cmdlet identifies the addresses of the primary and failover Federated Authentication Server to use for a specified UPN. 
A deterministic algorithm based on a SHA512 hash of the UPN is used to identify the addresses of two Federated Authentication Service servers, based on configuration in Group Policy. 
As long as the same Group Policy configuration is applied to all computers, the same addresses will be generated for each user. 
      
It's important to note that the explicit UPN should be used.
In the cases where an explicit UPN is not set, the implicit UPN should be used.
      
When a user logs in to Storefront the primary FAS server identified by this commandlet will be contacted, followed by the failover FAS server if the primary server is unavailable. 
If the failover server is also unavailable Storefront will continue to try other FAS servers. 
This algorithm allows user certificates to be cached in an efficient manner.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> Get-FasServerForUser -UserPrincipalNames @("user1@mycompany.com", "user2@mycompany.com")
```

Description

-----------

This looks up the addresses of the FAS servers that will hold cached certificates for each UPN.

### Example 2
PS C:\\\>

```
C:\PS> Import-Module ActiveDirectory
C:\PS> $users = foreach ( $user in Get-ADGroupMember "MyGroup" ) { echo ($user.name + "@mycompany.com"); }
C:\PS> Get-FasServerForUser -UserPrincipalNames $users
```

Description

-----------

This enumerates the UPN addresses of users in "MyGroup" and looks up the FAS servers that will hold cached certificates for each.

## Parameters

### -UserPrincipalNames
Array of UPNs (e.g.
user@domain.com) for which to determine FAS addresses. 
Note that the user accounts do not need to exist in the domain.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: (required)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### Variable, based on property name.
This cmdlet does accept input from the pipeline but only by property name.

## Outputs

### void
This cmdlet returns the UPNs and associated FAS primary and failover servers

## Notes

## Related Links

