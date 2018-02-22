# New-FasAuthorizationCertificate

Request a Registration Authority (or Enrollment Agent) certificate for a Federated Authentication Service.

## Syntax

`New-FasAuthorizationCertificate -CertificateAuthority <String> -CertificateTemplate <String> [-AuthorizationTemplate <String>] [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]`

## Detailed Description

Request a Registration Authority (or Enrollment Agent) certificate for a Federated Authentication Service. The Federated Authentication Service works by dynamically issuing user logon certificates from a Microsoft Certificate Authority. To do this it must first be granted an "Authorization Certificate" (often called an RA or Enrollement Agent certificate) to authenticate to the Certificate Authority. This command generates a Certifiate Request and sends it to the specified Certificate Authority to request an Authorization certificate.

## Related Commands

-  [New-FasAuthorizationCertificateRequest](New-FasAuthorizationCertificateRequest.md) 

-  [Get-FasAuthorizationCertificate](Get-FasAuthorizationCertificate.md) 

-  [Remove-FasAuthorizationCertificate](Remove-FasAuthorizationCertificate.md) 

-  [Get-FasMsTemplate](Get-FasMsTemplate.md) 

-  [Get-FasMsCertificateAuthority](Get-FasMsCertificateAuthority.md)

## Parameters

| Name                  | Description                                                                                                                                    | Required? | Pipeline Input        | Default Value                                    |
|-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------|-----------|-----------------------|--------------------------------------------------|
| CertificateAuthority  | Specify the CertificateTemplate of the Registration Authority certificate (e.g. "Citrix\_RegistrationAuthority").                              | true      | true (ByPropertyName) | (default)                                        |
| AuthorizationTemplate | Specify the name of the "Requires CA Administrator Approval" Certificate Template (e.g. "Citrix\_RegistrationAuthority\_ManualAuthorization"). | false     | true (ByPropertyName) | &lt;CertificateTemplate&gt;\_ManualAuthorization |
| Address               | Address of FAS Server (or \$NULL to use \$CitrixFasAddress)                                                                                    | false     | true (ByPropertyName) | \$CitrixFasAddress                               |
| UserName              | User name to use for authentication to FAS server (\$NULL for current user account)                                                            | false     | true (ByPropertyName) | \$NULL                                           |
| Password              | Password for authentication to FAS server (\$NULL for current user account)                                                                    | false     | true (ByPropertyName) | \$NULL                                           |

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
    C:\PS> New-FasAuthorizationCertificate -CertificateAuthority $DefaultCA -CertificateTemplate "Citrix_RegistrationAuthority" -AuthorizationTemplate "Citrix_RegistrationAuthority_ManualAuthorization"

This code generates a certificate request for "Citrix\_RegistrationAuthority\_ManualAuthorization" and sends it to the default CA in the domain. Once access is approved by the CA Administrator, a second request for the actual "Citrix\_RegistrationAuthority" certificate will be issued.
