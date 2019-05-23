# Get-FasRule

## Synopsis
List the Rules configured on the FAS server.

## Syntax

```
Get-FasRule [-Name <String>] [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
Retrieve the configuration of existing rules configured on a FAS server.

Normally to log in to a Windows computer the Active Directory Domain Controllers require that "primary credentials" be present - that is a password, or a smartcard, etc. 
An instance of a Federated Authentication Service allows trusted servers to "assert" user identities without knowledge of primary credentials. 
The configuration options are:
    - The name of the Rule or Service instance. 
Usually there will be at least one service named "default", but further, independent services can be run.
    - A reference to the certificate definitions used to issue Virtual Smart Card certificates when user identities are asserted. 
Note that only Certificate Definitions marked "InSession" can be used after the logon stage.
    - A reference to the Virtual Smart Card to use for log on. 
By default this is the first in the list of Certificate Definitions.
    - A list of Windows Accounts that are trusted to assert identities for this Rule. 
For security reasons, this must be chosen very carefully - usually it will be the explicit machine accounts of your StoreFront servers.
    - A list of Windows User Accounts that can be asserted. 
Usually this will be restricted to a security group. 
For example "ExternalCitrixUserGroup"
    - A list of VDA Windows Accounts that can act as relying parties to log users in. 
For example, "CitrixVdaMachines"
    - A list of administrators who have can modify (but not create or delete) the rule.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> Get-FasRule
```

Description

-----------

This code lists the Rules configured on the Federated Authentication Service

## Parameters

### -Name
Specify the name of the rule to retrieve ($NULL to list all rules).

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $NULL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Address
Address of FAS Server (or $NULL to use $CitrixFasAddress)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $CitrixFasAddress
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserName
User name to use for authentication to FAS server ($NULL for current user account)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $NULL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Password
Password for authentication to FAS server ($NULL for current user account)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $NULL
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
This cmdlet does not return a value

## Notes

## Related Links

[New-FasRule]()

[Set-FasRule]()

[Remove-FasRule]()


