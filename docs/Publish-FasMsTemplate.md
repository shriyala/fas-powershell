# Publish-FasMsTemplate

Publish an installed Microsoft Certificate Template on a Microsoft Certificate Authority.

## Syntax

`Publish-FasMsTemplate -Name <String> -CertificateAuthority <String> [<CommonParameters>]`

## Detailed Description

This commandlet authorizes a Microsoft Certificate Authority to issue certificates based on a Microsoft Certificate Template. Microsoft Certificate Authority uses Certificate Templates to describe the types of certificates that it can issue. This includes information such as the validity period and how the certificate should be authorized. Not all Certificate Authorities issue certificates of all types. This commandlet instructs a Certificate Authority to add an installed Certificate Template as a type of certificate that can be issued. Note that this cmdlet must be run using a High Privilege user account. Equivalent configuration can be done manually using the Microsoft GUI tools.

## Related Commands

-  [Unpublish-FasMsTemplate](Unpublish-FasMsTemplate.md)

-  [Get-FasMsCertificateAuthority](Get-FasMsCertificateAuthority.md)

## Parameters

| Name                 | Description                                                            | Required? | Pipeline Input        | Default Value |
|----------------------|------------------------------------------------------------------------|-----------|-----------------------|---------------|
| Name                 | Specifies the name of the Microsoft Certificate Template to publish.   | true      | true (ByPropertyName) | (required)    |
| CertificateAuthority | Specifies the Certificate Authority that should publish this template. | true      | true (ByPropertyName) | (required)    |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### void

This cmdlet does not return a value

## Examples

### EXAMPLE 1

    C:\PS> $ca = Get-FasMSCertificateAuthority -default
    C:\PS> Publish-FasMsTemplate -Name Citrix_SmartcardLogon -CertificateAuthority $ca.Address

Publishes the Citrix\_SmartcardLogon template on the certificate authority on dc.citrixtest.net
