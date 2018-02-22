# Get-FasAuthorizationCertificate

List the currently available Authorization certificates in use by the Federated Authentication Service server.

## Syntax

`Get-FasAuthorizationCertificate [-CertificateAuthority <String>] [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]`

## Detailed Description

List the currently available Authorization certificates in use by the Federated Authentication Service server. The Federated Authentication Service works by dynamically issuing user logon certificates from a Microsoft Certificate Authority. To do this it must first be granted an "Authorization Certificate" (often called an RA or Enrollement Agent certificate) to authenticate to the Certificate Authority. This command lists all of the Pending, Ok, MaintenanceRequired and Expired Authorization certificates available to the FAS server. The certificate and private key are stored in a container based on the "TrustArea" GUID.

## Related Commands



 -  [Get-FasAuthorizationCertificate](Get-FasAuthorizationCertificate.md) 

 -  [Remove-FasAuthorizationCertificate](Remove-FasAuthorizationCertificate.md)

## Parameters

| Name                 | Description                                                                                                                     | Required? | Pipeline Input        | Default Value |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------|-----------|-----------------------|---------------|
| CertificateAuthority | Filter by Address of the Certificate Authority used to issue the Authorization Certificate (\$NULL to return all certificates). | false     | true (ByPropertyName) | \$NULL        |
| UserName             | User name to use for authentication to FAS server (\$NULL for current user account)                                             | false     | true (ByPropertyName) | \$NULL        |
| Password             | Password for authentication to FAS server (\$NULL for current user account)                                                     | false     | true (ByPropertyName) | \$NULL        |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### FasAuthorizationCertificate

This cmdlet returns a list of FasAuthorizationCertificate objects

## Examples

### EXAMPLE 1

    C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
    C:\PS> Get-FasAuthorizationCertificate

This code lists the Authorization certificate on a FAS server. This includes its unique ID, the CA used to issue the certificate, an indication of whether the certificate is currently usable (as opposed to expiring or pending), and the storage container name (TrustArea)
