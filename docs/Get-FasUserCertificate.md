# Get-FasUserCertificate

List cached certificates on the Federated Authentication Service.

## Syntax

`Get-FasUserCertificate [-UserPrincipalName <String>] [-Rule <String[]>] [-CertificateDefinition <String>] [-MaximumRecordCount <Int>] [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]`

## Detailed Description

This command lists the certificates and private keys managed by the Federated Authentication Service.

## Related Commands

-  [New-FasUserCertificate](New-FasUserCertificate.md)

-  [Remove-FasUserCertificate](Remove-FasUserCertificate.md)

## Parameters

| Name                  | Description                                                                         | Required? | Pipeline Input        | Default Value      |
|-----------------------|-------------------------------------------------------------------------------------|-----------|-----------------------|--------------------|
| UserPrincipalName     | Filter by UPN on certificate.                                                       | false     | true (ByPropertyName) | \$NULL             |
| Rule                  | Filter by Rule name.                                                                | false     | true (ByPropertyName) | (default)          |
| CertificateDefinition | Filter by Certificate Type.                                                         | false     | true (ByPropertyName) | (default)          |
| SecurityContext       | Filter by Security Context.                                                         | false     | true (ByPropertyName) | (default)          |
| KeyInfo               | Include private key information in returned certificates.                           | false     | true (ByPropertyName) | (default)          |
| MaximumRecordCount    | Limit the number of certificates to return.                                         | false     | true (ByPropertyName) | 250                |
| Address               | Address of FAS Server (or \$NULL to use \$CitrixFasAddress)                         | false     | true (ByPropertyName) | \$CitrixFasAddress |
| UserName              | User name to use for authentication to FAS server (\$NULL for current user account) | false     | true (ByPropertyName) | \$NULL             |
| Password              | Password for authentication to FAS server (\$NULL for current user account)         | false     | true (ByPropertyName) | \$NULL             |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### void

This cmdlet returns a list of FasUserCertificate object

## Examples

### EXAMPLE 1

    C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
    C:\PS> Get-FasUserCertificate

This code lists all currently cached certificates on the Federated Authentication Service.
