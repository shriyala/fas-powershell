# New-FasRule

## Synopsis
Create a Rule object (a named instance of the Federated Authentication Service running on a server).

## Syntax

```
New-FasRule -Name <String> -CertificateDefinitions <String[]> -StoreFrontAcl <String> [-UserAcl <String>]
 [-VdaAcl <String>] [-DelegatedAdministrationAcl <Boolean>] [-Address <String>] [-UserName <String>]
 [-Password <String>] [<CommonParameters>]
```

## Description
Create a named rule that controls which trusted StoreFront servers can assert logon identities.

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
C:\PS> $CertificateDefinition=(Get-FasCertificateDefinition)[0].name
C:\PS> New-FasRule -Name "default" -CertificateDefinitions @($CertificateDefinition) -StoreFrontAcl D:P(A;OICI;CC;;;DD)
```

Description

-----------

This code generates a rule named "default" allowing Domain Controllers to assert identities by issuing certificates based on the first installed Certificate Definition

## Parameters

### -Name
Specify the name of this rule. 
Usually a rule named "default" would be available.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: (default)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateDefinitions
Specify the a list of CertificateDefinition names for Virtual Smart Cards to create. 
The first in the list will be used for the log on process.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: (default)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StoreFrontAcl
Specify the SDDL Security Descriptor controlling which servers are trusted to assert user identities using this rule. 
E.g.
"D:P(A;OICI;CC;;;XXXX)" replacing xxxx with a SID string.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: (default)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserAcl
Specify the SDDL Security Descriptor controlling which user identities can be asserted by this rule. 
E.g.
"D:P(A;OICI;LC;;;XXXX)" replacing xxxx with a SID string. 
Defaults as "D:P(A;OICI;LC;;;DU)" for "Domain Users"

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: D:P(A;OICI;LC;;;DU)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VdaAcl
Specify the SDDL Security Descriptor controlling which VDAs can be logged into by this rule. 
E.g.
"D:P(A;OICI;DC;;;XXXX)" replacing xxxx with a SID string. 
Defaults as "D:P(A;OICI;DC;;;DC)" for "Domain Computers"

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: D:P(A;OICI;DC;;;DC)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DelegatedAdministrationAcl
Specify the SDDL Security Descriptor controlling which users can change the configuration of this rule. 
E.g.
"D:P(A;OICI;SW;;;XXXX)" replacing xxxx with a SID string. 
Defaults as "D:P(A;OICI;SW;;;BA)" for "Built-in Administrators" on the FAS Server.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: D:P(A;OICI;SW;;;BA)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### Variable, based on property name.
This cmdlet does accept input from the pipeline but only by property name.

## Outputs

### void
This cmdlet does not return a value

## Notes

## Related Links

[Get-FasRule]()

[Set-FasRule]()

[Remove-FasRule]()

[Get-FasCertificateDefinition]()


