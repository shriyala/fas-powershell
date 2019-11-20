# Get-FasMsCertificateAuthority

## Synopsis
Retrieve information about the Microsoft Certificate Authorities installed in the domain.

## Syntax

```
Get-FasMsCertificateAuthority [-Address <String>] [-Default <Boolean>] [<CommonParameters>]
```

## Description
This commandlet retrieves information about the Microsoft Certificate Authorities installed in the domain, including their unique identifying addresses.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> Get-FasMsCertificateAuthority -Default
```

Description

-----------

This command retrieves the address of the default Microsoft Certificate Authority in this domain.

## Parameters

### -Address
Specifies the address of the Microsoft Certificate Authority to retrieve information about (or list them all)

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

### -Default
Return the default or primary Microsoft Certificate Authority in the current domain.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $FALSE
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
This cmdlet returns a list of Microsoft Certificate Authority objects

## Notes

## Related Links

[Publish-FasMsTemplate]()

[Unpublish-FasMsTemplate]()


