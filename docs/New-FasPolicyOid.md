# New-FasPolicyOid

## Synopsis
Create and register a new Issuance Policy Oid in the domain.

## Syntax

```
New-FasPolicyOid -Name <String> [-Group <String>] [<CommonParameters>]
```

## Description
This cmdlet registers a new Issuance Policy Oid with the domain by name, optionally specifying associated LDAP security group DN.

Certificate Issuance Policy Oids are attributes that can optionally be included in certificates issued by the Microsoft Certificate Authority. 
By default, these include Low/Medium/High Assurance levels and provide an indication of the level or type of approval to which a certificate holder has been authorized. 
When logging in, Windows will dynamically add the user to additional Universal Security Groups that have been associated with these Oids.

Note that this cmdlet must be run using a High Privilege user account. 
Equivalent configuration can be done manually using the Microsoft LDAP configuration tools.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> New-FasPolicyOid -Name "Finance User Assurance" -Group "CN=FinanceGroup,CN=Users,DC=citrixtest,DC=net"
```

Description

-----------

This command creates an OID that when included in a logon certificate will dynamically assign the user to the "FinanceGroup" Universal Security Group

## Parameters

### -Name
Specifies the name of the new policy oid to register

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

### -Group
Specifies the DN of a Universal Security Group to associate with this Policy OID (or leave $NULL)

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

[Get-FasPolicyOid]()

[Set-FasPolicyOid]()

[Remove-FasPolicyOid]()


