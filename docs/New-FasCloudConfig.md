# New-FasCloudConfig

## Synopsis
Create the Federated Authentication Service (FAS) Cloud configuration.

## Syntax

```
New-FasCloudConfig [-Rule <String>] [-CloudId <String>] [-SilentAuth] [-ClientId <String>]
 [-ClientSecret <String>] [-Customer <String>] [-ResourceLocationId <String>] [-Address <String>]
 [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
FAS can be configured to accept identity assertions from Citrix Cloud Workspace.

This cmdlet creates the Federated Authentication Service (FAS) Cloud configuration by opening a browser for the cloud administrator to authenticate and choose customer and resource location.
It is also possible to authenticate silently (i.e.
without a browser) using the -SilentAuth flag.

The rule parameter specifies which rule is applied to identity assertions made by Citrix Cloud Workspace.

Once configured with this cmdlet, FAS will attempt to register itself with Citrix Cloud.
Use Get-FasCloudConfig to see the status.

## Examples

### ========================== EXAMPLE 1 ==========================
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> New-FasCloudConfig
```

Description

===========

This code creates the FAS cloud configuration.

## Parameters

### -Rule
Specify the rule applied to identity assertions made by Citrix Cloud Workspace

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

### -CloudId
Specify the id of the cloud to connect to.
Use Get-FasCloudInfo to find supported cloud ids.
If not specified, connects to Citrix Cloud.

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

### -SilentAuth
Use silent authentication

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientId
Specify the secure client id for silent authentication

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

### -ClientSecret
Specify the secure client secret for silent authentication

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

### -Customer
Specify the cloud customer when using silent authentication

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

### -ResourceLocationId
Specify the resource location id when using silent authentication

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

[Set-FasCloudConfig]()

[Remove-FasCloudConfig]()

[Get-FasCloudInfo]()


