# Get-FasRaCertificateMonitor

## Synopsis
Get the FAS RA Certificate Monitor configuration.

## Syntax

```
Get-FasRaCertificateMonitor [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
This command gets the configuration of the FAS RA Certificate Monitor.

See Set-FasRaCertificateMonitor for information about the FAS RA Certificate Monitor and its configuration.

Time intervals are returned as TimeSpan objects i.e.
"D.HH:MM:SS" format.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress="localhost"
C:\PS> Get-FasRaCertificateMonitor
```

Description

-----------

This code gets the RA Certificate Monitor configuration.

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
This cmdlet returns the FAS RA Certificate Monitor configuration.

## Notes

## Related Links

[Set-FasRaCertificateMonitor]()

[Reset-FasRaCertificateMonitor]()


