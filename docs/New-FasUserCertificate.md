# New-FasUserCertificate

Generate and cache a certificate for a user on the Federated Authentication Service.

## Syntax

`New-FasUserCertificate -UserPrincipalName <String> -Rule <String[]> -CertificateDefinition <String> [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]`

## Detailed Description

This command creates a certificate for a user on the Federated Authentication Service. This can be used for testing purposes, or run at "off-peak" times to spread the load of certificate generation that would otherwise happen at user logon.

## Related Commands

-  [Get-FasUserCertificate](Get-FasUserCertificate.md)

-  [Remove-FasUserCertificate](Remove-FasUserCertificate.md)

## Parameters

| Name                  | Description                                                                                            | Required? | Pipeline Input        | Default Value      |
|-----------------------|--------------------------------------------------------------------------------------------------------|-----------|-----------------------|--------------------|
| UserPrincipalName     | Specify the UPN of the user for whom this certificate is being generated.                              | true      | true (ByPropertyName) | (default)          |
| Rule                  | Specify the Rule name (Federated Authentication Service instance) this certificate is associated with. | true      | true (ByPropertyName) | (default)          |
| CertificateDefinition | Specify the Certificate Definition to use when generating the certificate.                             | true      | true (ByPropertyName) | (default)          |
| SecurityContext       | Specify the Security Context to use when generating the certificate.                                   | false     | true (ByPropertyName) | \$NULL             |
| Address               | Address of FAS Server (or \$NULL to use \$CitrixFasAddress)                                            | false     | true (ByPropertyName) | \$CitrixFasAddress |
| UserName              | User name to use for authentication to FAS server (\$NULL for current user account)                    | false     | true (ByPropertyName) | \$NULL             |
| Password              | Password for authentication to FAS server (\$NULL for current user account)                            | false     | true (ByPropertyName) | \$NULL             |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### void

This cmdlet does not return a value

## Examples

### EXAMPLE 1

    C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
    C:\PS> New-FasUserCertificate -UserPrincipalName "fred@citrixtest.net" -Rule "default" -CertificateDefinition "default_Definition"

This code generates and caches a certificate for fred@citrixtest.net.
