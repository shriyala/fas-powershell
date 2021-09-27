# Get-FasCloudInfo

## Synopsis
Gets information about the clouds FAS can connect to.

## Syntax

```
Get-FasCloudInfo [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
This cmdlet lists information about all the clouds the Federated Authentication Service (FAS) can connect to.

## Examples

### ========================== EXAMPLE 1 ==========================
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> Get-FasCloudInfo
```

Description

===========

This code lists all the clouds FAS can connect to.

## Parameters

### -Address
Specify a particular FAS server to contact (or $NULL to use $CitrixFasAddress)

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
This cmdlet returns information about all the clouds FAS can connect to.

## Notes

## Related Links

[New-FasCloudConfig]()


