# New-FasAuthorizationCertificateRequest

## Synopsis
Generate an offline certificate request for a Registration Authority certificate for a Federated Authentication Service. 
Once the request is signed import the PKCS7 chain using Import-FasAuthorizationCertificateResponse.

## Syntax

```
New-FasAuthorizationCertificateRequest [-DistinguishedName <String>] [-UseTPM <Boolean>] [-Address <String>]
 [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
Generate an offline certificate request a Registration Authority (or Enrollment Agent) certificate for a Federated Authentication Service. 
Once the request is signed import the PKCS7 chain using Import-FasAuthorizationCertificateResponse.

The Federated Authentication Service works by dynamically issuing user logon certificates from a Microsoft Certificate Authority. 
To do this it must first be granted an "Authorization Certificate" (often called an RA or Enrollement Agent certificate) to authenticate to the Certificate Authority.

This command generates a Certifiate Request associated it with an FasAuthorizationCertificate and returns a Base64 CSR.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> $Request = New-FasAuthorizationCertificateRequest
C:\PS> Import-FasAuthorizationCertificateResponse -Id $Request.Id -Pkcs7CertificateFile .\ResponseFromCA.p7b
```

Description

-----------

This code generates a certificate request in $Request. 
Once issued it imports the PKCS7 response from a file.

## Parameters

### -DistinguishedName
Specify the Distinguished Name to include in the Certificate Request.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: DC=CitrixTrustFabric
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseTPM
Specify true to generate a private key in the Federated Authentication Service server's Trusted Platform Module.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $false
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### Variable, based on property name.
This cmdlet does accept input from the pipeline but only by property name.

## Outputs

### void
This cmdlet does not return a value

## Notes

## Related Links

[Import-FasAuthorizationCertificateResponse]()

[Get-FasAuthorizationCertificate]()

[Remove-FasAuthorizationCertificate]()


