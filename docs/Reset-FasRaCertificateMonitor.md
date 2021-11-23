# Reset-FasRaCertificateMonitor

## Synopsis
Reset the FAS RA Certificate Monitor configuration.

## Syntax

```
Reset-FasRaCertificateMonitor [-Address <String>] [-UserName <String>] [-Password <String>]
 [<CommonParameters>]
```

## Description
This command resets the configuration of the FAS RA Certificate Monitor to its defaults.

The Health Monitor is turned on by default.

See Set-FasRaCertificateMonitor for information about the FAS RA Certificate Monitor and its default configuration.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress="localhost"
C:\PS> Reset-FasRaCertificateMonitor
C:\PS> Get-FasRaCertificateMonitor
```

Description

-----------

This code resets the Health Monitor configuration then displays its settings.

## Parameters

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
This cmdlet does not have a return value.

## Notes

## Related Links

[Set-FasRaCertificateMonitor]()

[Get-FasRaCertificateMonitor]()


