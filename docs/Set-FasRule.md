# Set-FasRule

## Synopsis
Modify a rule (i.e.
a named configuration of the Federated Authentication Service).

## Syntax

```
Set-FasRule -Name <String> [-CertificateDefinitions <String[]>] [-StoreFrontAcl <String>] [-UserAcl <String>]
 [-VdaAcl <String>] [-DelegatedAdministrationAcl <String>] [-Address <String>] [-UserName <String>]
 [-Password <String>] [<CommonParameters>]
```

## Description
Set the configuration of an existing named rule controlling which trusted StoreFront servers can assert logon identities. 
The caller must be a member of the Rule's administration groups.

Normally to log in to a Windows computer the Active Directory Domain Controllers require that "primary credentials" be present - that is a password, or a smartcard, etc. 
A rule configuration on the Federated Authentication Service allows trusted servers to "assert" user identities without knowledge of primary credentials. 
The configuration options are:
    - The name of the Rule. 
Usually there will be at least one rule named "default", but further, independent rules can be configured.
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
C:\PS> $CertificateDefinition=(Get-FasCertificateDefinition)[0].name
C:\PS> Set-FasRule -Name "default" -CertificateDefinitions @($CertificateDefinition)
```

Description

-----------

This code changes the CertificateDefinitions used by the rule named "default".

## Parameters

### -Name
Specify the name of the rule to update. 
The caller must be an administrator of the rule.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: (required)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateDefinitions
Change the a list of CertificateDefinition names for Virtual Smart Cards to create. 
The first in the list will be used for the log on process.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (no change)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StoreFrontAcl
Change the SDDL Security Descriptor controlling which servers are trusted to assert user identities using this rule. 
E.g.
"O:BAG:DUD:P(A;OICI;CC;;;XXXX)" replacing xxxx with a SID string.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (no change)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserAcl
Change the SDDL Security Descriptor controlling which user identities can be asserted by this rule. 
E.g.
"O:BAG:DUD:P(A;OICI;LC;;;XXXX)" replacing xxxx with a SID string.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (no change)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VdaAcl
Change the SDDL Security Descriptor controlling which VDAs can be logged into by this rule. 
E.g.
"O:BAG:DUD:P(A;OICI;DC;;;XXXX)" replacing xxxx with a SID string.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (no change)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DelegatedAdministrationAcl
Change the SDDL Security Descriptor controlling which users can change the configuration of this rule. 
E.g.
"O:BAG:DUD:P(A;OICI;SW;;;XXXX)" replacing xxxx with a SID string.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (no change)
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

[Get-FasRule]()

[Remove-FasRule]()


