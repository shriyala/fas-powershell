# Request-FasCloudRegistration

## Synopsis
Requests a new cloud registration code

## Syntax

```
Request-FasCloudRegistration [-Address <String>] [-CloudId <String>] [-Password <String>] [-UserName <String>]
 [<CommonParameters>]
```

## Description
The cloud registration process is a 3-step process involving requesting a registration code, approving that code in Citrix Cloud, and finally completing the registration process once the code is approved.
This command requests a new cloud registration code, which needs to be approved by the Citrix Cloud administrator in Citrix Cloud.

## Examples

### Example 1
```
PS C:\> Request-FasCloudRegistration -CloudId com -Address localhost
```

Requests a new registration code to register with the 'commercial' Citrix Cloud.

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

### -CloudId
The Citrix cloud identifier represents the Citrix cloud which FAS will be registered with

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
Username to use to connect to FAS, which if not specified, will use the current Windows network identity

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

### Citrix.Authentication.FederatedAuthenticationService.ToggledPowerShell.Registration.Models.RequestCloudRegistrationUserResponse
## Notes

## Related Links

[Get-FasCloudRegistrationCloudInfo]()

[Get-FasCloudRegistrationStatus]()

[Complete-FasCloudRegistration]()

[New-FasCloudRegistration]()


