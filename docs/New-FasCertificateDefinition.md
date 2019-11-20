# New-FasCertificateDefinition

Create a Certificate Definition object (recipe for issuing a certificate).

## Syntax

`New-FasCertificateDefinition [-Name <String>] -CertificateTemplate <String> -AuthorizationCertificate <String> -CertificateAuthorities <String[]> [-PolicyOids <String>] [-InSession [<Boolean>]] [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]`

## Detailed Description

Create a Certificate Definition object that the FAS will use to generate types of certificate. When generating a certificate, the FAS requires various pieces of information. Including:

-  The CertificateTemplate to request (see Get-FasMsTemplate)
-  A list of loadbalanced/failover Certificate Authority Addresses (see Get-FasMsCertificateAuthority)
-  A reference to the AuthorizationCertificate to use to Authorize the request (see Get-FasAuthorizationCertificate)
-  A list of additional Issuance Policy OIDs to add to the certificate request (see Get-FasPolicyOid)
-  A flag indicating if the certificate can be used as an in-session Virtual Smart Card, or only for the logon process. Note that Certificate Definition objects can only be created and managed by the FAS Server administrator, although they can be referenced by "Rule" administrators.

## Related Commands

-  [Get-FasCertificateDefinition](Get-FasCertificateDefinition.md)

-  [Set-FasCertificateDefinition](Set-FasCertificateDefinition.md)

-  [Remove-FasCertificateDefinition](Remove-FasCertificateDefinition.md)

-  [Get-FasAuthorizationCertificate](Get-FasAuthorizationCertificate.md)

-  [Get-FasPolicy](Get-FasPolicy.md)

-  [Get-FasMsTemplate](Get-FasMsTemplate.md)

-  [Get-FasMsCertificateAuthority](Get-FasMsCertificateAuthority.md)

## Parameters

| Name                     | Description                                                                                                  | Required? | Pipeline Input        | Default Value                |
|--------------------------|--------------------------------------------------------------------------------------------------------------|-----------|-----------------------|------------------------------|
| Name                     | Specify the name of this Certificate Definition (if not specified, defaults to the CertificateTemplate name) | false     | true (ByPropertyName) | \[CertificateTemplate name\] |
| CertificateTemplate      | Specify the name of Certificate Template to use to issue this certificate                                    | true      | true (ByPropertyName) | (default)                    |
| AuthorizationCertificate | Specify a the Guid Id of an AuthorizationCertificate object                                                  | true      | true (ByPropertyName) | (default)                    |
| CertificateAuthorities   | Specify a list of Addresses of Certificate Authorities that can issue these certificates                     | true      | true (ByPropertyName) | (default)                    |
| PolicyOids               | Specify a list of Issuance Policy OIDs to request in the certificate                                         | false     | true (ByPropertyName) | (empty)                      |
| InSession                | Set to \$FALSE to only allow this certificate to be used for authentication                                  | false     | true (ByPropertyName) | \$FALSE                      |
| Address                  | Address of FAS Server (or \$NULL to use \$CitrixFasAddress)                                                  | false     | true (ByPropertyName) | \$CitrixFasAddress           |
| UserName                 | User name to use for authentication to FAS server (\$NULL for current user account)                          | false     | true (ByPropertyName) | \$NULL                       |
| Password                 | Password for authentication to FAS server (\$NULL for current user account)                                  | false     | true (ByPropertyName) | \$NULL                       |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### void

This cmdlet does not return a value

## Examples

### EXAMPLE 1

    C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
    C:\PS> $DefaultCA=(Get-FasMsCertificateAuthority -Default).Address
    C:\PS> $AuthorizationCertificate=(Get-FasAuthorizationCertificate)[0].Id
    C:\PS> New-FasCertificateDefinition -CertificateAuthorities $DefaultCA -MsTemplate "Citrix_SmartcardLogon" -AuthorizationCertificate $AuthorizationCertificate

This code generates a certificate definition that uses the first authorization certificate to issue Citrix\_SmartcardLogon certificates from the default CA
