# Get-FasAuthorizationCertificate

## Synopsis
List the currently available Authorization certificates in use by the Federated Authentication Service server.

## Syntax

```
Get-FasAuthorizationCertificate [-CertificateAuthority <String>] [-FullCertInfo] [-Address <String>]
 [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
List the currently available Authorization certificates in use by the Federated Authentication Service server.

The Federated Authentication Service works by dynamically issuing user logon certificates from a Microsoft Certificate Authority. 
To do this it must first be granted an "Authorization Certificate" (often called an RA or Enrollement Agent certificate) to authenticate to the Certificate Authority.

This command lists all the Authorization certificates on the FAS server.

The status of each certificate may be one of the following:
  Ok - the certificate is OK
  WaitingForApproval - the certificate request is pending approval by the CA administrator
  Expired - the certificate is expired
  NotYetValid - the certificate is not yet valid
  Denied - the certificate request was denied (a reason string is provided)

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> Get-FasAuthorizationCertificate
```

Description

-----------

This code lists the Authorization certificate on a FAS server. 
This includes its unique ID, the CA used to issue the certificate, an indication of whether the certificate is currently usable (as opposed to expired or waiting for approval), and the storage container name (TrustArea)

### Example 2
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> Get-FasAuthorizationCertificate -FullCertInfo
```

Description

-----------

This code lists the Authorization certificate on a FAS server, including detail about the certificate itself

## Parameters

### -CertificateAuthority
Filter by Address of the Certificate Authority used to issue the Authorization Certificate ($NULL to return all certificates).

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

### -FullCertInfo
Switch specifying that details of the authorization certificate should be returned

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

### -Address
```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### Variable, based on property name.
This cmdlet does accept input from the pipeline but only by property name.

## Outputs

### FasAuthorizationCertificate
This cmdlet returns a list of FasAuthorizationCertificate objects

## Notes

## Related Links

[New-FasAuthorizationCertificate]()

[Remove-FasAuthorizationCertificate]()


