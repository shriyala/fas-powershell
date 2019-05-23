# Set-FasAdministrationPolicy

## Synopsis
Sets the local administration policy for the Federated Authentication Service (FAS).

## Syntax

```
Set-FasAdministrationPolicy [-DefaultToLocalhost <Boolean>] [-CheckAddressAgainstGpo <Boolean>]
 [<CommonParameters>]
```

## Description
This cmdlet sets the local administration policy for the Federated Authentication Service (FAS).

## Examples

### Example 1
PS C:\\\>

```
C:\PS> Set-FasAdministrationPolicy -DefaultToLocalhost $true -CheckAddressAgainstGpo $false
```

Description

-----------

This code will cause FAS cmdlets which take an optional Address parameter to default to localhost if no address is supplied.
If an address is supplied, FAS cmdlets will not check the address is present in the GPO.

## Parameters

### -DefaultToLocalhost
Default to localhost.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $NULL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CheckAddressAgainstGpo
Check the address is present in the FAS GPO.

```yaml
Type: Boolean
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

## Notes

## Related Links

[Get-FasAdministrationPolicy]()


