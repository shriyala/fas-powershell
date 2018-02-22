# New-FasAuthorizationCertificateRequest

Generate an offline certificate request for a Registration Authority certificate for a Federated Authentication Service. Once the request is signed import the PKCS7 chain using Import-FasAuthorizationCertificateResponse.

## Syntax

`New-FasAuthorizationCertificateRequest [-DistinguishedName <String>] [-UseTPM <Boolean>] [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]`

## Detailed Description

Generate an offline certificate request a Registration Authority (or Enrollment Agent) certificate for a Federated Authentication Service. Once the request is signed import the PKCS7 chain using Import-FasAuthorizationCertificateResponse. The Federated Authentication Service works by dynamically issuing user logon certificates from a Microsoft Certificate Authority. To do this it must first be granted an "Authorization Certificate" (often called an RA or Enrollement Agent certificate) to authenticate to the Certificate Authority. This command generates a Certifiate Request associated it with an FasAuthorizationCertificate and returns a Base64 CSR.

## Related Commands

-  [Import-FasAuthorizationCertificateResponse](Import-FasAuthorizationCertificateResponse.md) 

-  [Get-FasAuthorizationCertificate](Get-FasAuthorizationCertificate.md) 

-  [Remove-FasAuthorizationCertificate](Remove-FasAuthorizationCertificate.md)

## Parameters

| Name              | Description                                                                                                      | Required? | Pipeline Input        | Default Value        |
|-------------------|------------------------------------------------------------------------------------------------------------------|-----------|-----------------------|----------------------|
| DistinguishedName | Specify the Distinguished Name to include in the Certificate Request.                                            | true      | true (ByPropertyName) | DC=CitrixTrustFabric |
| UseTPM            | Specify true to generate a private key in the Federated Authentication Service server's Trusted Platform Module. | false     | true (ByPropertyName) | \$false              |
| Address           | Address of FAS Server (or \$NULL to use \$CitrixFasAddress)                                                      | false     | true (ByPropertyName) | \$CitrixFasAddress   |
| UserName          | User name to use for authentication to FAS server (\$NULL for current user account)                              | false     | true (ByPropertyName) | \$NULL               |
| Password          | Password for authentication to FAS server (\$NULL for current user account)                                      | false     | true (ByPropertyName) | \$NULL               |

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
