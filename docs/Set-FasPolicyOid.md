# Set-FasPolicyOid

## Synopsis
Change the Universal Security Group associated with an Issuance Policy Oid registered in the domain.

## Syntax

```
Set-FasPolicyOid -Path <String> -Group <String> [<CommonParameters>]
```

## Description
This cmdlet modifies the security group associated with a new Issuance Policy Oid registered in the domain by name.

Certificate Issuance Policy Oids are attributes that can optionally be included in certificates issued by the Microsoft Certificate Authority. 
By default, these include Low/Medium/High Assurance levels and provide an indication of the level or type of approval to which a certificate holder has been authorized. 
When logging in, Windows will dynamically add the user to additional Universal Security Groups that have been associated with these Oids.

Note that this cmdlet must be run using a High Privilege user account. 
Equivalent configuration can be done manually using the Microsoft LDAP configuration tools.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $PolicyOid=Get-FasPolicyOid -Name "Finance User Assurance"
C:\PS> Set-FasPolicyOid -Path $PolicyOid.Path -Group "CN=FinanceGroup,CN=Users,DC=citrixtest,DC=net"
```

Description

-----------

This code looks up the LDAP Path of the "Finance User Assurance" OID and sets the associated group as the "FinanceGroup" Universal Security Group

## Parameters

### -Group
Specifies the DN of a Universal Security Group to associate with this Policy OID (or leave $NULL)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: $NULL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
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

[New-FasPolicyOid]()

[Get-FasPolicyOid]()

[Remove-FasPolicyOid]()


