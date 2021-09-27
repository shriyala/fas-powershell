# Set-FasCloudConfig

## Synopsis
Change the Federated Authentication Service (FAS) Cloud configuration.

## Syntax

```
Set-FasCloudConfig [-Rule <String>] [-Address <String>] [-UserName <String>] [-Password <String>]
 [<CommonParameters>]
```

## Description
FAS can be configured to accept identity assertions from Citrix Cloud Workspace.

This cmdlet changes the Federated Authentication Service (FAS) Cloud configuration.

## Examples

### ========================== EXAMPLE 1 ==========================
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> $RuleName=(Get-FasRule)[0].Name
C:\PS> Set-FasCloudConfig -Rule $RuleName
```

Description

===========

This code sets the FAS cloud rule to first configured FAS rule.

## Parameters

### -Rule
Change the rule applied to identity assertions made by Citrix Cloud Workspace

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (no change)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### Variable, based on property name.
This cmdlet does accept input from the pipeline but only by property name.

## Outputs

### void
This cmdlet returns nothing

## Notes

## Related Links

[Get-FasCloudConfig]()

[Remove-FasCloudConfig]()

[New-FasCloudConfig]()


