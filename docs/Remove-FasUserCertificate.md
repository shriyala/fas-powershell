# Remove-FasUserCertificate

Remove cached certificates on the Federated Authentication Service.

## Syntax

`Remove-FasUserCertificate [-UserPrincipalName <String>] [-Rule <String[]>] [-CertificateDefinition <String>] [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]`

## Detailed Description

This command deletes certificates and private keys managed by the Federated Authentication Service. This may affect users who are currently using Virtual Smart Cards as the private key will be immediately unavailable. The Federated Authentication Service will automatically remove certificates when they have expire, so it is unusually not necessary to explicitly delete them. Note that this command does not itself prevent equivalent certificates being regenerated when the user next logs in, nor does it revoke certificates that are currently in use.

## Related Commands

-  [New-FasUserCertificate](New-FasUserCertificate.md)

-  [Get-FasUserCertificate](Get-FasUserCertificate.md)

## Parameters

| Name                  | Description                                                                         | Required? | Pipeline Input        | Default Value      |
|-----------------------|-------------------------------------------------------------------------------------|-----------|-----------------------|--------------------|
| UserPrincipalName     | Filter by UPN on certificate.                                                       | false     | true (ByPropertyName) | \$NULL             |
| Rule                  | Filter by Rule name.                                                                | false     | true (ByPropertyName) | (default)          |
| CertificateDefinition | Filter by Certificate Type.                                                         | false     | true (ByPropertyName) | (default)          |
| SecurityContext       | Filter by Security Context.                                                         | false     | true (ByPropertyName) | (default)          |
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
    C:\PS> Remove-FasUserCertificate -UserPrincipalName "fred@citrixtest.net"

This code immediately deletes all certificates and private keys associated with certificates issued to fred@citrixtest.net.
