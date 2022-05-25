# Complete-FasCloudRegistration

## Synopsis
Finishes the cloud registration process.

## Syntax

```
Complete-FasCloudRegistration -ResourceLocationId <String> -Rule <String> [-Address <String>]
 [-Password <String>] [-UserName <String>] [<CommonParameters>]
```

## Description
The cloud registration process is a 3-step process involving requesting a registration code, approving that code in Citrix Cloud, and finally completing the registration process once the code is approved.
This command completes the cloud registration process, effectivly connecting FAS to the Citrix Cloud.

The specified resource location associates this FAS server with a specific resource location, such that when desktops and apps (resources) are launched in this location, this FAS server will be used to SSO into those resources.
The rule name identifies which FAS rule to use when performing SSO, and is usually specified as "Default"

## Examples

### Example 1
```
PS C:\> Complete-FasCloudRegistration -ResourceLocationId xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -Rule Default -Address localhost
```

This command completes the cloud registration process by associating the FAS server located at localhost with the specified resource location and the default FAS rule.
The registration code needs to have been approved by a Citrix cloud administrator prior to running this command, otherwise an error will occur.
Get-FasCloudRegistrationStatus can be used to the list the available resource locations that can be used.

## Parameters

### -ResourceLocationId
The resource location Id, such that when desktops and apps (resources) are launched in this location, this FAS server  will be used to SSO into those resources. 
The resource location id can be found in resource locations page in Citrix Cloud or using Get-FasCloudRegistrationStatus once the registration code is approved in Citrix Cloud.

```yaml
Type: String
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Password
Password for authentication to FAS server ($NULL for current user account)

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

### -UserName
The username to use to connect to FAS server, which if unspecified, will use the current Windows network identity

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### None
## Outputs

### Citrix.Authentication.FederatedAuthenticationService.ToggledPowerShell.Registration.Models.CompleteCloudRegistrationUserResponse
## Notes

## Related Links

[Get-FasCloudRegistrationCloudInfo]()

[Request-FasCloudRegistration]()

[Get-FasCloudRegistrationStatus]()

[New-FasCloudRegistration]()


