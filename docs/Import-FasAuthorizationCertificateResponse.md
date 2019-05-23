# Import-FasAuthorizationCertificateResponse

## Synopsis
Import a PKCS7 certificate chain containing an RA certificate issued by a certificate authority.

## Syntax

```
Import-FasAuthorizationCertificateResponse -Id <String> -Pkcs7CertificateFile <String> [-Address <String>]
 [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
Import a PKCS7 certificate chain containing the RA certificate issued by a certificate authority. 
Note that the format of the certificate file must be a DER encoded PKCS7 file including all certificates in the chain. 
This file format is an option from the "Copy to File..." feature of the Microsoft Certificate viewer.

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

### -Id
This is the GUID representing the FasAuthorizationCertificate Id. 
See Get-FasAuthorizationCertificate.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: (Default)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pkcs7CertificateFile
Specify the location of the PKCS7 file (including root and intermediate certificates)

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


