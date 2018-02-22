# Set-FasCertificateDefinition

Modify an existing Certificate Definition object (recipe for issuing a certificate).

## Syntax

`Set-FasCertificateDefinition -Name <String> [-CertificateTemplate <String>] [-AuthorizationCertificate <String>] [-CertificateAuthorities <String[]>] [-PolicyOids <String>] [-InSession [<Boolean>]] [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]`

## Detailed Description

Change the confiration of an existing Certificate Definition object that the FAS is using to generate certificates. When generating a certificate, the FAS requires various pieces of information. Including:
-  The CertificateTemplate to request (see Get-FasMsTemplate)
-  A list of loadbalanced/failover Certificate Authority Addresses (see Get-FasMsCertificateAuthority)
-  A reference to the AuthorizationCertificate to use to Authorize the request (see Get-FasAuthorizationCertificate)
-  A list of additional Issuance Policy OIDs to add to the certificate request (see Get-FasPolicyOid)
-  A flag indicating if the certificate can be used as an in-session Virtual Smart Card, or only for the logon process. Note that Certificate Definition objects can only be created and managed by the FAS Server administrator, although they can be referenced by "Rule" administrators.

## Related Commands

-  [New-FasCertificateDefinition](New-FasCertificateDefinition.md) 

-  [Get-FasCertificateDefinition](Get-FasCertificateDefinition.md) 

-  [Remove-FasCertificateDefinition](Remove-FasCertificateDefinition.md)

## Parameters

| Name                     | Description                                                                               | Required? | Pipeline Input        | Default Value      |
|--------------------------|-------------------------------------------------------------------------------------------|-----------|-----------------------|--------------------|
| Name                     | Specify the name of the certificate definition to modify                                  | true      | true (ByPropertyName) | (default)          |
| CertificateTemplate      | Change the name of Certificate Template to use to issue this certificate                  | false     | true (ByPropertyName) | (default)          |
| AuthorizationCertificate | Change a the Guid Id of an AuthorizationCertificate object                                | false     | true (ByPropertyName) | (default)          |
| CertificateAuthorities   | Change the list of Addresses of Certificate Authorities that can issue these certificates | false     | true (ByPropertyName) | (default)          |
| PolicyOids               | Change the list of Issuance Policy OIDs to request in the certificate                     | false     | true (ByPropertyName) | (empty)            |
| InSession                | Set to \$FALSE to only allow this certificate to be used for authentication               | false     | true (ByPropertyName) | (default)          |
| Address                  | Address of FAS Server (or \$NULL to use \$CitrixFasAddress)                               | false     | true (ByPropertyName) | \$CitrixFasAddress |
| UserName                 | User name to use for authentication to FAS server (\$NULL for current user account)       | false     | true (ByPropertyName) | \$NULL             |
| Password                 | Password for authentication to FAS server (\$NULL for current user account)               | false     | true (ByPropertyName) | \$NULL             |

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
    C:\PS> Set-FasCertificateDefinition -Name MyCertificateDefinition -CertificateAuthorities $DefaultCA -MsTemplate "Citrix_SmartcardLogon" -AuthorizationCertificate $AuthorizationCertificate

Updates an existing certificate definition to use the first authorization certificate to issue Citrix\_SmartcardLogon certificates from the default CA
