# Get-FasPolicyOid

## Synopsis
Retrieve information about the Issuance Policy Oids registered in the domain.

## Syntax

```
Get-FasPolicyOid [-Name <String>] [-Path <String>] [<CommonParameters>]
```

## Description
This commandlet retrieves information about the Issuance Policy Oids registered in the domain, including their human readable name and associated security groups.

Certificate Issuance Policy Oids are attributes that can optionally be included in certificates issued by the Microsoft Certificate Authority. 
By default, these include Low/Medium/High Assurance levels and provide an indication of the level or type of approval to which a certificate holder has been authorized. 
When logging in, Windows will dynamically add the user to additional Universal Security Groups that have been associated with these Oids.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> Get-FasPolicyOid
```

Description

-----------

This command retrieves the address Policy Oids registered in this forest.

## Parameters

### -Name
Specifies the name of a policy oid to retrieve (or $NULL to list them all).

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

### -Path
```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
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
This cmdlet returns a list of Microsoft Policy Oid objects

## Notes

## Related Links

[New-FasPolicyOid]()

[Set-FasPolicyOid]()

[Remove-FasPolicyOid]()


