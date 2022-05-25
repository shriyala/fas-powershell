# Get-FasCloudRegistrationCloudInfo

## Synopsis
Gets the list of available Citrix clouds

## Syntax

```
Get-FasCloudRegistrationCloudInfo [-Address <String>] [-Password <String>] [-UserName <String>]
 [<CommonParameters>]
```

## Description
A Citrix cloud has Citrix Virtual Apps and Desktop service hosted in it.
Each cloud is identified by a cloud identifier which can be used when refering to a Citrix cloud in other commands.

## Examples

### Example 1
```
PS C:\> Get-FasCloudRegistrationCloudInfo -Address localhost
```

Gets the list of Citrix clouds supported by the FAS server located at localhost.
The output including the cloud identifier which can be used to refer to specific clouds within other commands.

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
Username to use to connect to the FAS server, which if not specified, will use the current Windows network identity

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

### Citrix.Authentication.FederatedAuthenticationService.PowerShell.FasCloudInfo[]
## Notes

## Related Links

[Request-FasCloudRegistration]()

[Get-FasCloudRegistrationStatus]()

[Complete-FasCloudRegistration]()

[New-FasCloudRegistration]()


