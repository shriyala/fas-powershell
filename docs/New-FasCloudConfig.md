# New-FasCloudConfig

## Synopsis
Create the Federated Authentication Service (FAS) Cloud configuration.

## Syntax

```
New-FasCloudConfig [-RuleName <String>] [-Address <String>] [-UserName <String>] [-Password <String>]
 [<CommonParameters>]
```

## Description
This cmdlet create the Federated Authentication Service (FAS) Cloud configuration by opening a browser and getting the cloud administrator to authenticate.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> New-FasCloudConfig
```

Description

-----------

This code sets creates the FAS cloud configuration.

## Parameters

### -RuleName
Specify the FAS rule to use

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### Variable, based on property name.
This cmdlet does accept input from the pipeline but only by property name.

## Outputs

### void
This cmdlet returns nothing

## Notes

## Related Links

[Get-FasCloudConfig]()

[Set-FasCloudConfig]()

[Remove-FasCloudConfig]()


