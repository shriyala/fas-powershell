# New-FasAuthorizationCertificate

## Synopsis
Request a Registration Authority (or Enrollment Agent) certificate for a Federated Authentication Service.

## Syntax

```
New-FasAuthorizationCertificate -CertificateAuthority <String> -CertificateTemplate <String>
 [-AuthorizationTemplate <String>] [-Address <String>] [-UserName <String>] [-Password <String>]
 [<CommonParameters>]
```

## Description
Request a Registration Authority (or Enrollment Agent) certificate for a Federated Authentication Service.

The Federated Authentication Service works by dynamically issuing user logon certificates from a Microsoft Certificate Authority. 
To do this it must first be granted an "Authorization Certificate" (often called an RA or Enrollement Agent certificate) to authenticate to the Certificate Authority.

This command generates a Certifiate Request and sends it to the specified Certificate Authority to request an Authorization certificate.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> $DefaultCA=(Get-FasMsCertificateAuthority -Default).Address
C:\PS> New-FasAuthorizationCertificate -CertificateAuthority $DefaultCA -CertificateTemplate "Citrix_RegistrationAuthority" -AuthorizationTemplate "Citrix_RegistrationAuthority_ManualAuthorization"
```

Description

-----------

This code generates a certificate request for "Citrix_RegistrationAuthority_ManualAuthorization" and sends it to the default CA in the domain. 
Once access is approved by the CA Administrator, a second request for the actual "Citrix_RegistrationAuthority" certificate will be issued.

## Parameters

### -CertificateAuthority
Specify the CertificateTemplate of the Registration Authority certificate (e.g.
"Citrix_RegistrationAuthority").

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: (default)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AuthorizationTemplate
Specify the name of the "Requires CA Administrator Approval" Certificate Template (e.g.
"Citrix_RegistrationAuthority_ManualAuthorization").

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: <CertificateTemplate>_ManualAuthorization
Accept pipeline input: True (ByPropertyName)
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
Default value: $CitrixFasAddress
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

### -CertificateTemplate
```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
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

### void
This cmdlet does not return a value

## Notes

## Related Links

[New-FasAuthorizationCertificateRequest]()

[Get-FasAuthorizationCertificate]()

[Remove-FasAuthorizationCertificate]()

[Get-FasMsTemplate]()

[Get-FasMsCertificateAuthority]()


