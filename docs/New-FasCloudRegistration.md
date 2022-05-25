# New-FasCloudRegistration

## Synopsis
Registers FAS with the Citrix Cloud without requiring a registration code.

## Syntax

### UNNAMED_PARAMETER_SET_1
```
New-FasCloudRegistration [-Address <String>] -ClientSecret <String> -ClientId <String> -CloudId <String>
 -Customer <String> -ResourceLocationId <String> -Rule <String> [<CommonParameters>]
```

### UNNAMED_PARAMETER_SET_2
```
New-FasCloudRegistration [-Address <String>] -ClientSecret <String> -ClientId <String> -GeoServiceUri <String>
 -CwsServiceUri <String> -Customer <String> -ResourceLocationId <String> -Rule <String> [<CommonParameters>]
```

### UNNAMED_PARAMETER_SET_3
```
New-FasCloudRegistration [-Address <String>] [-Password <String>] [-UserName <String>] [<CommonParameters>]
```

## Description
Registers FAS with a Citrix Cloud without requiring a registration code. 
This command is used to register with a Citrix Cloud that does not support registration codes.
This requires using a secure client to authenticate with Citrix Cloud. 
A secure client can be generated in the Citrix Cloud Admin Console.

## Examples

### Example 1
```
PS C:\> New-FasCloudRegistration -CloudId com -Rule Default -ClientId xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -ClientSecret xxxxxxxxxxxxxxxxxxxxxxxxxxxxx -Customer xxxxxxxxxxxx -ResourceLocationId xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -Address localhost
```

Registers FAS with Citrix cloud using an existing Citrix cloud, as identified by 'com', which represents the default Citrix commercial cloud. 
See Get-FasCloudRegistrationCloudInfo for list of supported clouds and their associated cloud identifiers.

### Example 2
```
PS C:\> New-FasCloudRegistration -CwsServiceUri "https://service.example.net/" -GeoServiceUri "https://service-geo.ctxwsstgapi.net/" -Rule Default -ClientId xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -ClientSecret xxxxxxxxxxxxxxxxxxxxxxxxxxxxx -Customer xxxxxxxxxxxx -ResourceLocationId xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -Address localhost
```

Registers FAS with Citrix Cloud using an explicit cloud referenced by https://service.example.net

## Parameters

### -Address
Address of FAS Server (or $NULL to use $CitrixFasAddress)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientSecret
Specified the secure client secret to use to authenticate with citrix cloud.
This is the secret of the secure client, which can be generated in Citrix Cloud.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientId
The secure client secret identifier to use to authenticate with citrix cloud.
This is the identifier of the secure client generated in Citrix Cloud.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GeoServiceUri
This is a specific geo-aware cloud endpoint

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CloudId
This is the identifier of the Citrix cloud to register FAS with

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CwsServiceUri
This is an explicit reference to a Citrix cloud endpoint to register FAS with

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Customer
This is the cloud customer that owns this FAS server

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Password for authentication to FAS server ($NULL for current user account)

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceLocationId
The resource location Id, such that when desktops and apps (resources) are launched in this location, this FAS server  will be used to SSO into those resources. 
The resource location id can be found in resource locations page in Citrix Cloud or using Get-FasCloudRegistrationStatus once the registration code is approved in Citrix Cloud

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Rule
The rule name parameter specifies which rule is applied to identity assertions made by Citrix Cloud Workspace

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
The username that will be used to connect to the FAS server, which if unspecified, will use the current Windows network identity

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### None
## Outputs

### Citrix.Authentication.FederatedAuthenticationService.ToggledPowerShell.Registration.Models.NewCloudRegistrationUserResponse
## Notes

## Related Links

[Get-FasCloudRegistrationCloudInfo]()

[Request-FasCloudRegistration]()

[Get-FasCloudRegistrationStatus]()

[Complete-FasCloudRegistration]()


