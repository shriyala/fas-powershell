# Import-FasAuthorizationCertificateResponse

Import a PKCS7 certificate chain containing an RA certificate issued by a certificate authority.

## Syntax

`Import-FasAuthorizationCertificateResponse -Id <String> -Pkcs7CertificateFile <String> [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]`

## Detailed Description

Import a PKCS7 certificate chain containing the RA certificate issued by a certificate authority. Note that the format of the certificate file must be a DER encoded PKCS7 file including all certificates in the chain. This file format is an option from the "Copy to File..." feature of the Microsoft Certificate viewer.

## Related Commands

-  [New-FasAuthorizationCertificateRequest](New-FasAuthorizationCertificateRequest.md)

-  [Get-FasAuthorizationCertificate](Get-FasAuthorizationCertificate.md)

-  [Remove-FasAuthorizationCertificate](Remove-FasAuthorizationCertificate.md)

## Parameters

| Name                 | Description                                                                                            | Required? | Pipeline Input        | Default Value      |
|----------------------|--------------------------------------------------------------------------------------------------------|-----------|-----------------------|--------------------|
| Id                   | This is the GUID representing the FasAuthorizationCertificate Id. See Get-FasAuthorizationCertificate. | true      | true (ByPropertyName) | (Default)          |
| Pkcs7CertificateFile | Specify the location of the PKCS7 file (including root and intermediate certificates)                  | false     | true (ByPropertyName) | (default)          |
| Address              | Address of FAS Server (or \$NULL to use \$CitrixFasAddress)                                            | false     | true (ByPropertyName) | \$CitrixFasAddress |
| UserName             | User name to use for authentication to FAS server (\$NULL for current user account)                    | false     | true (ByPropertyName) | \$NULL             |
| Password             | Password for authentication to FAS server (\$NULL for current user account)                            | false     | true (ByPropertyName) | \$NULL             |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### void

This cmdlet does not return a value

## Examples

### EXAMPLE 1

    C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
    C:\PS> $Request = New-FasAuthorizationCertificateRequest
    C:\PS> Import-FasAuthorizationCertificateResponse -Id $Request.Id -Pkcs7CertificateFile .\ResponseFromCA.p7b

This code generates a certificate request in \$Request. Once issued it imports the PKCS7 response from a file.
