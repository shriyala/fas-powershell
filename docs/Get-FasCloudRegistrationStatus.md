# Get-FasCloudRegistrationStatus

## Synopsis
Gets the current status of the cloud registration process.

## Syntax

```
Get-FasCloudRegistrationStatus [-Address <String>] [-Password <String>] [-UserName <String>]
 [<CommonParameters>]
```

## Description
The cloud registration process is a 3-step process involving requesting a registration code, approving that code in Citrix Cloud, and finally completing the registration process once the code is approved.
This command displays the current status, such as pending approval, registration complete etc.

## Examples

### Example 1
```
PS C:\> Get-FasCloudRegistrationStatus -Address localhost
```

Gets the status of the current cloud registration process.

### Example 2
```
PS C:\> (Get-FasCloudRegistrationStatus -Address localhost).ResourceLocations
```

Show how to get the list of available resource locations.
This requires that the registration code has been approved in Citrix cloud.

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
Username to connect to the FAS server, which if not specified, will use the current Windows identity

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

### Citrix.Authentication.FederatedAuthenticationService.ToggledPowerShell.Registration.Models.GetCloudRegistrationStatusUserResponse
## Notes

## Related Links

[Get-FasCloudRegistrationCloudInfo]()

[Request-FasCloudRegistration]()

[Complete-FasCloudRegistration]()

[New-FasCloudRegistration]()


