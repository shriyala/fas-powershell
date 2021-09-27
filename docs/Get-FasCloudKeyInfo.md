# Get-FasCloudKeyInfo

## Synopsis
Retrieve information about the key the Federated Authentication Service (FAS) uses to access Citrix Cloud.

## Syntax

```
Get-FasCloudKeyInfo [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
FAS can be configured to accept identity assertions from Citrix Cloud Workspace.

This cmdlet returns information about the key the Federated Authentication Service (FAS) uses to access Citrix Cloud.

## Examples

### ========================== EXAMPLE 1 ==========================
PS C:\\\>

```
C:\PS> Get-FasCloudKeyInfo -Address localhost
```

Description

===========

This code gets information about the key FAS uses to access the cloud.

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
This cmdlet returns information about the key FAS uses to access the cloud.

## Notes

## Related Links

[Get-FasCloudConfig]()

[Set-FasCloudConfig]()

[Remove-FasCloudConfig]()

[New-FasCloudConfig]()


