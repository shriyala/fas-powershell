# Unpublish-FasMsTemplate

Stop publishing a Microsoft Certificate Template on a Microsoft Certificate Authority.

## Syntax

`Unpublish-FasMsTemplate -Name <String> -CertificateAuthority <String> [<CommonParameters>]`

## Detailed Description

This command instructs a Microsoft Certificate Authority to stop publishing a Microsoft Certificate Template. After running this command, the Certificate Authority will no longer issue certificates of this type. Note that this cmdlet must be run using a High Privilege user account. Equivalent configuration can be done manually using the Microsoft GUI tools.

## Related Commands

-  [Publish-FasMsTemplate](Publish-FasMsTemplate.md)

-  [Get-FasMsCertificateAuthority](Get-FasMsCertificateAuthority.md)

## Parameters

| Name                 | Description                                                                      | Required? | Pipeline Input        | Default Value |
|----------------------|----------------------------------------------------------------------------------|-----------|-----------------------|---------------|
| Name                 | Specifies the name of the Microsoft Certificate Template to stop publishing.     | true      | true (ByPropertyName) | (required)    |
| CertificateAuthority | Specifies the Certificate Authority that should no longer publish this template. | true      | true (ByPropertyName) | (required)    |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### void

This cmdlet does not return a value

## Examples

### EXAMPLE 1

    C:\PS> $ca = Get-FasMSCertificateAuthority -default
    C:\PS> Unpublish-FasMsTemplate -Name Citrix_SmartcardLogon -CertificateAuthority $ca.Address

This command instructs the certificate authority on dc.citrixtest.net to stop issuing certificates based on the Citrix\_SmartcardLogon template.
