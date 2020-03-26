# Remove-FasPolicyOid

## Synopsis
Remove a registered Issuance Policy Oid in the domain.

## Syntax

```
Remove-FasPolicyOid -Path <String> [<CommonParameters>]
```

## Description
This cmdlet removes an existing Issuance Policy Oid registered in the domain.

Note that this cmdlet must be run using a High Privilege user account. 
Equivalent configuration can be done manually using the Microsoft LDAP configuration tools.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $PolicyOid=Get-FasPolicyOid -Name "Finance User Assurance"
C:\PS> Remove-FasPolicyOid -Path $PolicyOid.Path
```

Description

-----------

This code looks up the LDAP Path of the "Finance User Assurance" OID and deletes it.

## Parameters

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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

[Set-FasPolicyOid]()


